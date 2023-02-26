---
title: Writing a VS Code extension
date: 2023-02-26 19:35 +0200
categories: [learning, code, vscode, typescript]
---

## Motivation
As I'm writing these posts I want to improve on my language and writing skills which can be a tedious process. So I figured I'll make it way more difficult and quickly add a VScode extension that can get a list of synonyms for a specific word.

## Getting started
Following the guide from [Your First Extension](https://code.visualstudio.com/api/get-started/your-first-extension), I needed to install some libraries as always. This was simply 3 commands:

```bash
sudo apt-get install nodejs
sudo apt install npm
sudo npm install -g yo generator-code
```

Thereafter a simple `yo code` gets you started! After a few basic selections the minimal example extension is setup! All this does is allows a user to execute a named command which displays a message. Quite nifty after about 5 minutes.

## Making changes
After a few more minutes of doc diving I figured out how to rename commands, add keybindings and set up some more configs. The naming is simply set in the `package.json` file along with the keybinds as seen below.

```json
"contributes": {
    "commands": [
      {
        "command": "thesauraptor.synonyms",
        "title": "Obtain synonyms for the selected word."
      },
      {
        "command": "thesauraptor.antonyms",
        "title": "Obtain antonyms for the selected word."
      },
      {
        "command": "thesauraptor.definitions",
        "title": "Obtain definitions for the selected word."
      }
    ],
    "keybindings": [
      {
        "command": "thesauraptor.synonyms",
        "key": "Ctrl+Shift+Alt+S",
        "when": "editorTextFocus"
      },
      {
        "command": "thesauraptor.antonyms",
        "key": "Ctrl+Shift+Alt+A",
        "when": "editorTextFocus"
      },
      {
        "command": "thesauraptor.definitions",
        "key": "Ctrl+Shift+Alt+D",
        "when": "editorTextFocus"
      }
    ]
  },
```

After setup 2.0 it's time to dive into the actual functionality of the extension. I searched around on Google and the Hub[^1] for a few libraries that can find the synonym of a word. To my surprise there weren't many up to date libraries that has this functionality. I found [Wordpos](https://github.com/moos/wordpos). As defined on Github, _wordpos is a set of fast part-of-speech (POS) utilities for Node.js and browser using fast lookup in the WordNet database._. This library has a neat function called `lookup` which accepts a word and a callback function as the parameters.

```javascript
lookup(word, callback)
```

The word passed to the function is the selected word (or the word behind the cursor) when a user executes the "Find synonyms" function. The callback function simply returns the result. When the method is executed it returns a promise which is why there's an added `await` keyword when calling the function. This will _wait_ for the function to finish and then store the result. More on promises in a future post!

```typescript
const result = await wordpos.lookup(
    selectedWord,
    async function (result: any) {
        return result;
    }
);
```

Voila, we have a list of synonyms! Well, not quite. We have a result containing a lot of information about our word. Within this result is our synonyms. Thanks to a debug log output I could see the format of the object. The object is defined below:

![Console.log of result](/assets/img/posts/Result_of_objects.png)

Thus to obtain a list of synonyms we'd have to execute the below:

```typescript
result[0]["synonyms"]
```

This might not seem too bad, but the issue comes when I want to add the `lexName` and the definition of the synonym along with the synonym itself. This results in very ugly code because we don't have any types...

## Introducing types through magic
Clickbait heading -- although a part of me still believes all programming is a subset of magic. I decided to use [io-ts](https://github.com/gcanti/io-ts) to type out the resulting object. This would allow me to check if the object can parse correctly into my type and then access the data on the object via the dot operator. While this was quite neat, a colleague of mine mentioned to look into [Zod](https://github.com/colinhacks/zod). This is essentially a photo copy of io-ts[^2], but with more support! I implemented this design and infrastructure change trough hard work (about 3 minutes) and the code was working again! After these changes and a little bit of `programming magic` I ended with the code snippet shown below.

```typescript
const parsed = wordposSchema.parse(result);

const definitionArticles = parsed.flatMap((item: Result) => {
    return item.synonyms
        .filter(function (synonym: any) {
            return synonym !== selectedWord;
        })
        .map(function (synonym: any) {
            return {
                label: synonym,
                detail: item.def,
                description: item.lexName,
            };
    });
});
```

Most of the logic is explained above with the only additions being the flatMap, map and filter. Flat map takes an array of arrays and returns a single array. Map iterates through a list and maps it to the function and filter returns a subset of items that are true for the filter function. This piece of code allows me to build a list of objects in the form of:

```typescript
{
    label: string,
    detail: string
    description: string,
}
```

These items are used for the VS Code's `showQuickPick` function which will ultimately show the list of synonyms.

## Mistakes, additions, future work
After I implemented everything and officially released the extension (which can be found here: [Thesauraptor](https://marketplace.visualstudio.com/items?itemName=LiamL17.thesauraptor)), I realized it was quite shit... 
It gives a very small list of synonyms which are not very helpful in most cases. Quite sad, but still motivated I attempted to look for the next solution! After some more thought, I realized I could use an online API although this will need an API key. I originally went with the idea to use a free API, but those results were even worse. To resolve the issue of the API key without spending millions, I could simply prompt the user for their own API key. The implementation details for these changes will be described in a future post once I get to work!

Lastly, I want give the user a list of antonyms for a selected word. This will be combined with the change to switch to API based searching.

[^1]: [Github](https://github.com/)
[^2]: It is definitely not a photo copy, but from my miniscule understanding of io-ts it seemed like a photo copy. 
[^1]: [Github](https://github.com/)
[^2]: It is definitely not a photo copy, but from my miniscule understanding of io-ts it seemed like a photo copy. 
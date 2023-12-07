---
layout: post
title: TIWLI VIII
date: 2023-12-07 12:09 +0200
---

## A bit of everything
On today's TIWIL we have an exciting feature of some new words, a new command learned and then a short story of how a bug can kill a `cat`.

### New words
Yesterday I learned that the word _brassiere_ is the full form of the ever so popular bra. This paragraph might make it seem that my IQ has lowered, but rest assured I believe it's still in the high 70's!

Furthermore, I wondered which other words we use daily that aren't in their full form. Below are some more words that haven't revealed their final form until right now:

1. _Ping_ - Packet Internet Groper
1. _Phishing_ - Password Harvesting Involving Subversive Hijacking of Information and Negation of Genuine Systems
1. _Taxi_ - Taximeter
1. _Picnic_ - Originates from the French "pique-nique" which is a social gathering with a shared meal
1. _Taser_ - Thomas A. Swift's Electric Rifle

### Glossy makes you a better dev
A VS Code extension was discovered as I was watching a Youtube video. This extension is practically useless in terms of functionality, but all established devs know that prettiness and effectiveness have a direct correlation.

The extension is [Vibrancy Continued](https://marketplace.visualstudio.com/items?itemName=illixion.vscode-vibrancy-continued). Stealing from the description, it simply adds an Acrylic/Glass effect in VS Code. It doesn't seem to work too well with all themes, but hey it's pretty and thus can help with writing code!

### `script`'in
This nifty command simply takes **all** terminal output and saves it into a file. This is extremely useful when running multiple commands where you might need a history of output.

Here's the official description when using `man script`
```
script makes a typescript of everything on your terminal session. The terminal data are stored in raw form to the log file and information about timing to another (optional) structured log file. The timing log file is necessary to replay the session later by scriptreplay(1) and to store additional information about the session.

Since version 2.35, script supports multiple streams and allows the logging of input and output to separate files or all the one file. This version also supports new timing file which records additional information. The command scriptreplay --summary then provides all the information.

If the argument file or option --log-out file is given, script saves the dialogue in this file. If no filename is given, the dialogue is saved in the file typescript.

Note that logging input using --log-in or --log-io may record security-sensitive information as the log file contains all terminal session input (e.g., passwords) independently of the terminal echo flag setting.
```

### `cat` not landing on its feet
I have been busy with some gruesome admin work... I finished writing the code which lead to the tail-end of the project where I have to ensure that no current customers' code will break. (I won't go into detail otherwise my next post I might need to ask for job opportunities). In essence I ran some script 11 times combined with the `script` command to store output. Then I wanted to concatenate all these files into one. This was necessary as I needed to extract all xyz's[^1] that matched a certain regex. So as all great developers does, I opened up Google and asked how to achieve this difficult goal of mine. The first link lead me to StackOverflow with a wonderful solution!

```bash
cat ./* > merged.txt
```

Here's a quick breakdown of the above:
1. `cat` - prints all text to the terminal
1. `./*` - for every file (`*`)
1. `>` - pipe command which means take the left and _pipe_ it into the right
1. `merged.txt` - the output file

Now you might be thinking, why didn't this work? The explanation above makes sense! 
Let me teach you something young child. There's a little nuclear problem in programming and it has a name. The name being **recursion**.[^2] In essence, recursion is the repeated application of a recursive procedure. See [University of Utah's explanation](https://users.cs.utah.edu/~germain/PPS/Topics/recursion.html) for a bit more in depth on the topic.

So back to the issue. How did it break?

Since I executed the command in the same folder, it created the `merged.txt` file in the folder. And since `./*` was used, it `cat`'ed the outputs of the file and piped it back into the file. This went on forever aka until I saw that `merged.txt` was over 2GB in size.

The solution for this small bug is extremely simple. Instead of writing `merged.txt` into the same folder, use a different folder. Or grab the files from a different folder. Below are these solutions.

```bash
# Solution 1 (files are in different folder)
cat ./files/* > merged.txt

# Solution 2 (save merged.txt in different folder)
cat ./* > ./output/merged.txt
```

[^1]: I am using xyz here as I'm not allowed to use the real term. Something about a work contract...
[^2]: Just imagine heavy drums with lighting in the background for dramatic effect.
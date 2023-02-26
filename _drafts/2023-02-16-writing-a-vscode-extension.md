---
title: Writing a VS Code extension
date: 2023-02-16 19:35 +0200
categories: [learning, code, vscode, typescript]
---

## Motivation
As I'm writing these posts I want to improve on my language and writing skills which can be a tedious process. So I figured I'll make it way more difficult and quickly add a Vscode extension that can get a list of synonyms for a specific word using a free API.

## Design
After an intensive 82 second thinking period I decided to 

## Getting started
Following the guide from [Your First Extension](https://code.visualstudio.com/api/get-started/your-first-extension), I needed to install some libraries as always. This was simply 3 commands:

```bash
sudo apt-get install nodejs
sudo apt install npm
sudo npm install -g yo generator-code
```

Thereafter a simple `yo code` gets you started! After a few basic selections the minimal example extension is setup! All this does is allows a user to execute a named command which displays a message. Quite nifty after about 5 minutes.

---
title: A new beginning
date: 2023-02-12 23:53:31
categories: [code, introduction, jekyll]
tags: [new]
pin: true
---

# This post serves as a starting point for Liam's Life™

I always wanted to have a blog but never knew where to start. Each time I have tried starting in the past I get stuck on what web framework to use, how to design the blog, what content should the blogs contain and about a million other things... 

Then I came upon Jekyll. Not knowing what this odd word meant I quickly became a master by watching a 1 min youtube video! After this mastery I can confidently say that Jekyll is a tool used to "transform plain text into static website and blogs.". Jekyll uses themes or templates to populate websites, thus I had to find a theme I like. I considered a couple of themes which ultimately led to Chirpy, the theme you're currently seeing.

In this post I'll elaborate on how I set up my workspace for the blog.

## New PC; Same problems

Recently I bought new parts for my PC because my gaming experience was subpar. More about that in another post! With this __new__ PC, I had to reinstall a lot of programs and one of those was a developing workspace.

Previously I've always used virtual machines with a linux based distribution for my workspaces. These are tedious to setup and require a lot of resources. When I thought about my new setup I initially wanted to use docker, but instead saw an awesome VS Code extension. This extension is the [Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) extension. In essence this extension allows a person to remotely connect to WSL.

### Workspace setup
1. Download VS Code from https://code.visualstudio.com/. 
1. Install [Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) extension.
1. Download and install [WSL](https://learn.microsoft.com/en-us/windows/wsl/install)
1. Struggle trying to setup docker for over 35 minutes.
1. Restart PC and have docker issues magically resolved. (Ps. It wasn't magic, there were just some user properties not set and a restart helped...)
1. Connect to linux through Remote Development extension. This should be as easy as clicking on the Remote Development extension's icon, right click on linux distribution (most likely Ubuntu) and click connect.

After these steps are completed I had a neat and fresh Ubuntu workspace. Usually after I setup my ol' trusty virtual machines, I would follow a couple more steps before I start hacking away at the next project.

1. Set the superior text editor, Vim, as my default text editor. (For those wondering why I don't use Emacs -- because I used Vim in university and never got the time to learn Emacs so I just gaslighted myself into believing Vim is superior.)
1. Install Zsh as my default shell.
1. Install [Oh-my-zsh](https://ohmyz.sh/) framework.
1. Install [autocomplete](https://github.com/marlonrichert/zsh-autocomplete) plugin

Finally I am ready to start working on a project and the clock tells me it's past midnight... But the show must go on!


### Setting up what you're reading right now

To setup Liam's Life™ I followed 2 very simple guides. The first being the [Jekyll quickstart](https://jekyllrb.com/docs/) guide. This simply mentions a couple of requirements to install and executing one more install command and boom Jekyll is installed! Secondly, I followed the steps mentioned in [Option 1](https://chirpy.cotes.page/posts/getting-started/#option-1-using-the-chirpy-starter) on the Chirpy documentation. Lastly, I modified the `_config.yml` file and filled in properties and then started writing this exact post.

## What lies ahead
We never truly know what the future beholds, but for this project - a collection of guides, documentations, rants, exploratory mini projects and shitposts will be posted semi-regularly. No exact theme will be followed and requests are always welcome!
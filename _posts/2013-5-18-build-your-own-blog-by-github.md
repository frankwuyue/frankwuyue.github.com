---
layout: post
title: Build your own blog by github
categories:
  - Life
tags:
  - Blog
  - Jekyll
  - Github
---

# Build your own blog by github

What's github? Github is like facebook among programmers. GitHub offers both paid plans for private repositories, and free accounts for open source projects. Today, GitHub is the most popular open source code repository site.
Today I will show you the way to use GitHub to build your own blog. It's free and so easy to use. Compared to other blog websites like tumblr, you can build a site in whatever you like, not in a template, although you may spend more time on it.
So, let's start.

## About os

I strongly recommend you use GitHub on Linux. Here is a link for [Download for Linux, Mac, Windows and Solaris](http://git-scm.com/downloads). I don't know the exact difference between these OS, but I will use Ubuntu 12.04 to show you the process.
And of course, you should sign up on GitHub.

## SSH keys

#### 1. Check the SSH keys

we should check on the ssh key on PC.

        $ cd ~/.ssh

if the terminal shows "No such file or directory",then go to step 3, otherwise go on.

#### 2. Back-up and remove the former ssh key

        $ ls
        config  id_rsa  id_rsa.pub      known_hosts
        $ mkdir key_backup
        $ cp id_rsa* key_backup
        $ rm id_rsa*

#### 3. Creat new SSH key

enter the code below in terminal, the default one is enough, so just press ENTER.

        $ ssh-keygen -t rsa -C "username@youremail.com"
        Generating public/private rsa key pair.
        Enter file in which to save the key (/Users/your_user_directory/.ssh/id_rsa):	        (Just press enter)

Then you may have to set your passphrase:

        Enter passphrase (empty for no passphrase):
        Enter same passphrase again:

When you see this kind of thing, congrats!

![SSH key](http://img.readitlater.com/i/beiyuu.com/images/githubpages/ssh-key-set/RS/w680.png)

#### 4. Add SSH key to GitHub

Assume you have signed in GitHub and you can see _Accout settings_ on the right top. Click it and you can see _SSH Keys_ on the left. Click it and copy the ssh keys in the column. Like this.

![SSH key](http://img.readitlater.com/i/beiyuu.com/images/githubpages/bootcamp_1_ssh/RS/w680.jpg)

#### 5. Test it

enter this code to test whether it's good or not.

        $ ssh -T git@github.com

if this kind of thing shows, relax, just enter yes.

        The authenticity of host 'github.com (207.97.227.239)' can't be established.
        RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
        Are you sure you want to continue connecting (yes/no)?

and you may see

        Hi username! You've successfully authenticated, but GitHub does not provide shell access.

#### 6. Set your account information

When you push a post or change sth in repo, the Git will check your account name and it's very important for your authentication, you definitely don't want to use other random name.

        $ git config --global user.name "yourname"
        $ git config --global user.email "yourname@youremail.com"


Now you can connect to the github.

## Build a blog by GitHub Pages

There are two basic types of Pages available,**User/Organization Pages** and **Project Pages**. The two types of pages are nearly identical, except for a few details.

**User & Organization Pages** live in a special repository dedicated to only the Pages files. This repository uses the account name, [for example](atmos/atmos.github.io).

- This repository must use the `username/username.github.io` naming scheme.

- Content from the **master** branch will be used to build and publish the Pages.ojec

  **Project Pages** are kept in the same repository as the project they are for. These pages are almost exactly the same as User and Org Pages, with a few slight differences:

- The gh-pages branch is used to build and publish from.

- A custom domain on user/org pages will apply the same domain redirect to all project pages hosted under that account, unless the project pages use their own custom domain.

- If no custom domain is used, the project pages are served under a subpath of the user pages: `username.github.io/projectname`.

- Custom 404s will only work if a custom domain is used, otherwise the User Pages 404 is used.

You can see [GitHub Help on Pages](https://help.github.com/articles/user-organization-and-project-pages).

#####(to be continued)

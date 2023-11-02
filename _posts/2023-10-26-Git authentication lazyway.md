---
layout: post
title: "Git authentication lazyway"
date: 2023-10-26 
---

> Git authentication can be a pain if you have secured a bit ..but this guide will give 
a way to use ssh for your speedy workflow in a secure way.`linux` 

**Configuring with credential-helper**

``` term
~ $ git config --global credential.helper 'cache --timeout=86400'
```
yes, you can use the credential manager and set the `timeout=86400` its seconds here, 24hrs 
you can set days, hours anytime you want.

or, you can just store the passwords with 

```term
~ $ git config --global credential.helper store
```
but it saves your password to your ~/.gitconfig in plain text which is not cool,
so another much secure way is by using ssh.

**[Configuring to use SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#about-ssh-key-passphrases)**

First of we are going generate a ssh key for your device.
we can start with 

``` term
~ $ ssh-keygen -t rsa -b 4096 -C "youremail@xyz"
```
press enter for the default location of file & give a password

`This command will generate your key in ~/.ssh which is RSA encrypted in 4096 bit`

start the ssh agent with --

``` term
~ $ eval "$(ssh-agent -s)"
```
adding to keychain with --

``` term
~ $ ssh-add
```
copy the key that we just created to clipboard--

``` term
~ $ xclip -selection clipboard < ~/.ssh/rsa.pub
```

In Last step visit your git profile settings-> ssh & gpg keys
click create new ssh key and paste the keys copied and its done !

```
If you were working on a project and want to switch to SSH for authentication then you have edit that .git file manually or use this command mentioned below ..go to the project folder .[It just changes the https url to ssh url example : https://github.com/urname/nthng.git will be changed to git@github.com:urname/nthng.git]

```

``` term
~ $ git remote set-url origin git@github.com:urname/nthng.git
```

>Tip `whenever you are going for a clone just switch it to ssh [git@github.com:username/nothing.git] so no further tinkering is required for working on your projects`


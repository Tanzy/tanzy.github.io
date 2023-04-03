---
title: 'Securing Raspberry Pi'
date: 2019-01-14 22:38:24 +00:00
layout: post
permalink: /2019/01/securing-raspberry-pi/
categories:
    - Raspberry Pi
tags:
    - raspberry pi
---

Securing your Pi is a *must* especially if you are planning to have your Pi open to the outside world. (e.g. act as a web server). Below are details of some of what you should do.

## Add New User

One issue with the Raspberry Pi is that the default user will always be *pi*. You may want to create another user to make the Pi a more secure, you can then delete the default user.

```bash
sudo adduser jblogs
```

When creating the user you will be prompted to enter a password. The new users home directory will be located at */home/jblogs/*

Once the user has been added you need to add them to the sudo group with the following command.

```bash
sudo adduser jblogs sudo
```

## Delete User *pi*

Once a new user has been created you can delete the default user *pi*. Login as the new user, then run the following command to delete the user *pi* and also delete their home directory.

```bash
sudo deluser -remove-home pi
```

## *sudo* Should require a password   


When you are using the *sudo* command you are effectively running the command as a superuser. By default, you do not need to use a password for this. It’s advisable to make the use of *sudo* to require the users password. Run the following command

```bash
sudo nano /etc/sudoers.d/010_pi-nopasswd
```

Then change the user entry for the user that you created to

```
jblogs ALL=(ALL) PASSWD: ALL
```

Then make sure that you save the file.
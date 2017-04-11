---
layout: post
comments: true
title: Working more effectively with shell – basic commands
description: "Learn a few commands, which are required very often, such as man, echo, cat and similar"
published: true
tags: [linux]
---
- Enter the following command. It will show the various types of manual.
pages displayed by the man command:
```
$ man man
```
- We can enter the man command to display corresponding manual pages
as follows:
```
$ man 1 command $ man 5 command
```
- This will show information about the passwd command:
```html
$ man 5 passwd
```
The preceding command will give information about the file passwd, which is stored in /etc /passwd.

- We can get brief information about the command as follows:
```
$ whatis passwd
```
Output:
```
passwd (1ssl) - compute password hashes
passwd (1) - change user password
passwd (5) - the password file
```
- Every command we type in the terminal has an executable binary program
file associated with it. We can check the location of a binary file as follows:
```
$ which passwd
```
The preceding line tells us that the binary file of the passwd command is
```
located in the /usr/bin/passwd folder.
```
- We can get complete information about the binary file location as well as
manual page location of any command by following:
```
$ whereis passwd
```
The output will be as follows:
```
passwd: /usr/bin/passwd /etc/passwd /usr/bin/X11/passwd /usr/
share/man/man1/passwd.1.gz /usr/share/man/man1/passwd.1ssl.gz /
usr/share/man/man5/passwd.5.gz
```

- Change the user login and effective user name:
```
$ whoami
```
This command displays the user name of the logged in user:
```
$ su or $ sudo su
```
- The su command (switch user) will make the user as the administrator;
but, you should know the administrators, password. The sudo command
(superuser do) will run the command with administrator's privileges. It is
necessary that the user should have been added in the sudoers list.
```
# who am i
```
This command will show the effective user who is working at that moment.
```
exit
```

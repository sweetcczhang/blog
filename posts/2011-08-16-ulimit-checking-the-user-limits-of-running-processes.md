---
author: bencane
comments: true
date: 2011-08-16 20:32:06+00:00
popularity: None
slug: ulimit-checking-the-user-limits-of-running-processes
title: 'ulimit: Checking the user limits of running processes'
post_id: 35
categories:
- Administration
- All Articles
- Linux
- Security
- Troubleshooting
tags:
- linux
- tech
- troubleshooting
- ulimit
- unix
---

The `/proc` filesystem is a wealth of useful information. Found this one today looking for something unrelated.

You can read the limits file of a running process to find its currently defined limits, this is helpful for things like Max open files. You can use this to verify that the settings in `/etc/security/limits.conf` matches the running process.

**Example:**

    [bcane@bcane ~]$ cat /proc/5610/limits
    Limit Soft Limit Hard Limit Units
    Max cpu time unlimited unlimited seconds
    Max file size unlimited unlimited bytes
    Max data size unlimited unlimited bytes
    Max stack size 8388608 unlimited bytes
    Max core file size 0 unlimited bytes
    Max resident set unlimited unlimited bytes
    Max processes 3874 3874 processes
    Max open files 1024 1024 files
    Max locked memory 65536 65536 bytes
    Max address space unlimited unlimited bytes
    Max file locks unlimited unlimited locks
    Max pending signals 3874 3874 signals
    Max msgqueue size 819200 819200 bytes
    Max nice priority 0 0
    Max realtime priority 0 0
    Max realtime timeout unlimited unlimited us
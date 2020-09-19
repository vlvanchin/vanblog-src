+++
title = "Linux"
description = "This page show some of the most used commands in Linux"
tags = [
    "linux",
    "development",
]
date = "2020-06-09"
categories = [
    "Development",
    "Linux",
]
menu = "main"
author = "van"
+++

# Some commands that benifit you

## How to search text in folder and sub-folders

// to search "httpclient" text in current and subfolders
// -r is recursive and -l to list the file along with path.
```
$ grep -rl "httpclient" ./
```

## Commands for Vimdiff 

// to jump to the next/previous difference
```
]c :        - next difference
[c :        - previous difference
```

// to bringing difference from other file to current file
```
do          - diff obtain
```

// to put difference from current file to the other file
```
dp          - diff put
```

// to open/close the folded text
```
zo          - open folded text
zc          - close folded text
```

// to refresh the differenc
```
:diffupdate - re-scan the files for differences
```


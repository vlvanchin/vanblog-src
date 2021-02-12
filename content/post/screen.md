+++
title = "Screen cmd"
description = "This page shows some basic command of Screen"
tags = [
    "unix",
    "screen",
]
date = "2021-02-12"
categories = [
    "unix",
]
menu = "main"
author = "van"
+++

# Screen Examples
This page shows some useful commands of Screen tool in Unix

## To start  a screen session:
`$ screen`

## To list all the command 
Press `Ctrl+a ?`

## To start a named screen session:
`$ screen -S web`

## To terminate from a current screen session / window:
Press `Ctrl+d`

## To scroll up and down the screen
Press `Ctrl+a (escape)(enter) Up arrow or down arrow`

## You can have multiple windows within a Screen session.
Within a screen session following commands can be used:

### To create a new window with shell 
Press `Ctrl+a c`

### To list all windows in the current screen session
Press `Ctrl+a "`

### To switch to second window (from 0 …9)
Press `Ctrl+a 1 `

### To rename the current window
Press `Ctrl+a A`

### To split the current region horizontally into two regions
Press `Ctrl+a S`

### To split the current region vertically into two regions
Press `Ctrl+a |`

### To switch the input focus to the next region
Press `Ctrl+a tab`

### To toggle between the current and previous region
Press `Ctrl+a Ctrl+a`

### To close all regions by the current one
Press `Ctrl+a Q`

### To close the current region
Press `Ctrl+a X`

### To detach from the screen session
Press `Ctrl+a d`

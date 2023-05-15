# pywal-obsidianmd
A pywal script to create an obsidian.md theme.

## Installation:

`git clone https://github.com/poach3r/pywal-obsidianmd`

`cd pywal-obsidianmd`

`chmod +x pywal-obsidianmd.sh`


## Usage:

### Interactively

`./pywal-obsidianmd.sh`

Then simply enter your full vault directory, in my case it would be `"/home/stefan/OneDrive/Obsidian Vault"`

### via command line argument
`./pywal-obsidianmd.sh "/home/stefan/OneDrive/Obsidian Vault"`




You should then see pywal-obsidianmd as an available theme.

![theme](/20230328_08h27m48s_grim.png)

## Optional

### Change wallpaper alias

I use an alias to use it together with sxiv to choose a background. Just choose the background, mark 1 (just 1!) picture with M and quit with Q.

this uses a python venv:

        alias wp='~/venv/bin/python3 -m pywal -i "$(sxiv -tfbo /usr/share/backgrounds)"; ~/OneDrive/src/pywal-obsidianmd/pywal-obsidianmd.sh "/home/stefan/OneDrive/Obsidian Vault"'

this doesn't use a python venv:

        alias wp='wal -i "$(sxiv -tfbo /usr/share/backgrounds)"; ~/OneDrive/src/pywal-obsidianmd/pywal-obsidianmd.sh "/home/stefan/OneDrive/Obsidian Vault"'


### Change wallpaper script (example)

I use a script that I trigger with a click on an element in waybar. This also uses sxiv and restarts waybar afterwards.

        #!/bin/bash
        wal -i "$(sxiv -tfbo /usr/share/backgrounds)" && ~/OneDrive/src/pywal-obsidianmd/pywal-obsidianmd.sh "/home/stefan/OneDrive/Obsidian Vault" > /dev/null 2&>/dev/null
        killall waybar && /sbin/waybar

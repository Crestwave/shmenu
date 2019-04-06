# shmenu

A dynamic menu for the terminal written in pure Bash

[![asciicast](https://asciinema.org/a/232466.svg)](https://asciinema.org/a/232466)

## Usage

Simply direct the items to `shmenu`'s stdin, separated by newlines.

## Dependencies

- `bash 4.3+`
- A VT100-compatible terminal
	- Pretty much every virtual \*nix terminal should support this

## Q&A

### Why are there no command-line options?

In true suckless fashion, `shmenu` is configured through its source code. I usually don't prefer this philosophy, but `dmenu` was meant (as far as I know) to be used through shell scripts, after all; since `shmenu` itself is written in Bash, you can include the modified `shmenu` with it. I will still consider it, though.

### Why is there no support for text navigation?

The only time I used that with `dmenu` was when I was executing commands, and there isn't really a reason to do that with `shmenu` as it's run from a terminal.

### Why does it glitch out or flicker when I move the selection?

TL;DR: Run `git apply patches/stty.patch` within the cloned repository to fix it

Bash does not have a way to permanently turn off echoing input without external utilities. `shmenu` works around this by using `read`'s `-s` option, which turns it off while it's receiving input, and running fast enough that `read` usually catches all input.

However, if your autorepeat rate is very high and your environment isn't very fast, it can outpace it and cause input to occasionally flicker on the screen. You can fix this by applying the stty patch, which turns it off using the `stty` external utility.

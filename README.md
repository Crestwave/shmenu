# shmenu

A dynamic menu for the terminal written in pure Bash

[![asciicast](https://asciinema.org/a/232466.svg)](https://asciinema.org/a/232466)

## Usage

Simply direct the items to `shmenu`'s stdin, separated by newlines.

## Dependencies

- `bash 4.3+`

## Q&A

### Why are there no command-line options?

In true suckless fashion, `shmenu` is configured through its source code. I usually don't prefer this philosophy, but `dmenu` was meant (as far as I know) to be used through shell scripts, after all; since `shmenu` itself is written in Bash, you can include the modified `shmenu` with it. I will still consider it, though.

### Why is there no support for text navigation?

The only time I used that with `dmenu` was when I was executing commands, and there isn't really a reason to do that with `shmenu` as it's run from a terminal.

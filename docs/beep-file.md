# [beep-file](/bin/beep-file)
##  A simple utility for creating PC Speaker music

### Requirements

* python
* `pcspkr` kernel module must be loaded
* `/dev/input/by-path/platform-pcspkr-event-spkr` must be writable by the current user ([See Arch Wiki](https://wiki.archlinux.org/title/PC_speaker#Run_as_non-root_user))

### Installation

Install the requirements, if not already met.

Clone the repo & add it to the PATH, or download the file, put it in a directory on the PATH (such as `/usr/local/bin`, or `~/.local/bin`) and mark it executable.

### Usage

Use `beep-file <path to file with instructions>` to execute PC Speaker instructions contained in the given beep-file script.

### Syntax

The beep-file script contains lines of speaker tones to play and the time for which to play them.<br>
Here's an example beep-script:
```
#! /home/mini_bomba/mini_bomba-utils/bin/beep-file
500   200
1000  200
1500  200
x     500
2000  200
```
The interpreter understands comments (using # as the starting character) and allows for empty and comment lines.
This makes is possible to use a [shebang line](https://en.wikipedia.org/wiki/Shebang_%28Unix%29) at the start.
The location of the beep-file executable will obviously depend on where you cloned this repo to.

The lines that are not ignored by the interpreter due to being empty, must have 2 white-space separated columns of integers.
The left column controls the tone frequency, the right column controls the time the tone is being played for, in milliseconds.
You may use `x` as the frequency to create a silent segment. The frequency cannot be negative or higher than `65535`.
(though anything over 10000 can barely be heard)

#### Loops

Simple loops can be created by using `[ <iteration count>` to open the loop and `]` to close it.
Any code between those characters will be repeated `<iteration count>` times. Nested loops are supported.

Example script using nested loops:
```
#!/home/mini_bomba/mini_bomba-utils/bin/beep-file
150 100
[ 5
    200 100
    [ 3
        500 100
        x   500
    ]
]
350 100
```

#### Errors

If a syntax error is found, the segment may be skipped or silenced, depending on the error.
Issues with the frequency column produce a silent segment, issues with the time column or the count of columns skip the segment.<br>
In all cases of a syntax error, an error message is printed.

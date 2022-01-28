# [index-music](/bin/index-music)
## A simple script for creating an index of music files dowloaded using youtube-music

### Requirements

* bash
* yt-dlp (youtube-dl may still work but yt-dlp is preferred)
* grep
* jq
* xargs
* sort

### Installation

Install the requirements, if not already met.

Clone the repo & add it to the PATH, or download the file, put it in a directory on the PATH (such as `/usr/local/bin`, or `~/.local/bin`) and mark it executable.

### Usage

Navigate in the terminal to the folder containing your music files and run the file from the terminal (by typing `index-music`).
After a while, a list of your music files with the corresponding youtube video titles will be outputed to STDOUT.
It is recommended to use output redirection to save the index to a file (for example, using `index-music > ../music-index.txt`).

### Additional information

* The script uses your CPU core count as the maximum number of yt-dlp processess to use for title lookup, in order to speed the process up
* The list is always alphabetically sorted.

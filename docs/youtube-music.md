# [youtube-music](/bin/youtube-music)
## A simple script for downloading music using youtube-dl to mp3

### Requirements

* bash
* youtube-dl
* ffmpeg

### Installation

Install the requirements, if not already met.

Clone the repo & add it to the PATH, or download the file, put it in a directory on the PATH (such as `/usr/local/bin`, or `~/.local/bin`) and mark it executable.

### Usage

Run the file from the terminal (by typing `youtube-music`). A prompt for the video link will be shown, unless the url was given as an argument to this script. Any url compatible with youtube-dl can be used.
After the url is given, the script will start downloading the video or playlist to a temporary directory using youtube-dl.
After download finishes, all the files will be converted to .mp3 and put into your current working directory.

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
If a youtube playlist link is given, the download will be made in parallel to speed it up.

### Using environment variables to alter program's behaviour

youtube-music accepts advanced parameters through environment variables.
They and their meaning are listed below:

* `MBYTM_DOWNLOAD_PROCS`: Max count of concurrent youtube-dl processes used for downloading videos. Only used if given a youtube playlist link. Default: `10`
* `MBYTM_FFMPEG_PROCS`: Max count of concurrent ffmpeg processes used for converting videos to mp3. Make sure to adjust this value depending on amount of available CPU cores. Default: `4`


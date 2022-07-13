# [kclip](/bin/kclip)
## xclip, but for KDE's klipper

### Requirements

* python3
* klipper
* python-dbus

### Installation

Install the requirements, if not already met.

Clone the repo & add it to the PATH, or download the file, put it in a directory on the PATH (such as `/usr/local/bin`, or `~/.local/bin`) and mark it executable.

### Usage
The script aims to work in the same way as xclip

Help page:
```commandline
usage: kclip [-h] [-i] [-o] [-r] [files ...]

xclip, but for KDE's klipper

positional arguments:
  files           files to read from (uses stdin if not specified, only in --in mode)

options:
  -h, --help      show this help message and exit
  -i, --in        set clipboard contents from stdin or files (default)
  -o, --out       read clipboard contents to stdout
  -r, --rmlastnl  remove last newline character if present
```

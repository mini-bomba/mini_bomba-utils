# [sourcemap-extractor](/bin/sourcemap-extractor)
## a simple script from extracting source code from js sourcemaps

### Requirements

* python3

### Installation

Install the requirements, if not already met.

Clone the repo & add it to the PATH, or download the file, put it in a directory on the PATH (such as `/usr/local/bin`, or `~/.local/bin`) and mark it executable.

### Usage
Pipe the sourcemap into stdin of the script. (either as decoded json, or in base64 encoded form)

The script will automatically extract all contained source files into the current directory, recreating the original directory structure.

# [passwordgen](/bin/passwordgen)
## A simple CLI password generator (in python)

### Requirements

* python3
* tkinter (only if clipboard used)

### Installation

Install the requirements, if not already met.

Clone the repo & add it to the PATH, or download the file, put it in a directory on the PATH (such as `/usr/local/bin`, or `~/.local/bin`) and mark it executable.

### Usage

Run the file from the terminal (by typing `passwordgen`). A random, url-safe string of characters will be generated & displayed in the terminal (automatic copy soon™?). By default the string will be 64 characters long, but that can be changed by including a number after the command.

### Using environment variables to alter program's behaviour

passwordgen accepts advanced parameters through environment variables.
They and their meaning are listed below:

`MBPASS_MODE`: Specifies where the generated password will be displayed. Possible values:
* `both`: Default value. Prints the password on the terminal & copies it into the clipboard. Requires working `tkinter` module.
* `copy`/`clipboard`: Copies the password into the clipboard without printing it on the terminal. Requires working `tkinter` module.
* `print`/`terminal`: Prints the password on the terminal without copying it into the clipboard.

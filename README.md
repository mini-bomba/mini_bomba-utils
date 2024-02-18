# mini_bomba utils
## My personal CLI utilities

This repository contains some of my personal utilities, which may serve different purposes like: storing files in an encrypted format, or generating random passwords with a single command.

**I do not guarantee that any of the utilities/scripts are secure. Trust them at your own risk.** Also read the [license](/LICENSE).

All programs in this repository are designed to be used under linux, but some may also work on other OS'es. Note that linux-based OS'es are the only ones supported by me.

If you'd like to suggest a change to one of my scripts, feel free to create an issue or pull request.

## Installation, usage & other information

Most scripts can be installed simply by cloning the repo & adding the [`bin`](/bin) directory to your PATH, or downloading invidual files & putting them into a folder on the PATH (after applying the execute permission to them). And don't forget about their dependencies!

All files will have a corresponding .md file in the [`docs`](/docs) directory serving as their documentation, including more specific installation instructions, requirements for installation & usage instructions.

Most executable files in this repository will not include extensions specifying their type, to make it easier to execute from the linux terminal. The file type is instead specified using [shebang lines](https://en.wikipedia.org/wiki/Shebang_%28Unix%29). If you're using an OS that doesn't support them, you may need to add the appropiate extension and run the file using the correct interpreter. Note that OS'es that do not support shebang lines are not supported by me.

## List of scripts/programs included

| Script name/file                                | Documentation file                                           | Language |
|-------------------------------------------------|--------------------------------------------------------------|----------|
| [passwordgen](/bin/passwordgen)                 | [passwordgen.md](/docs/passwordgen.md)                       | python3  |  
| [mini_vault](/bin/mini_vault)                   | [mini_vault.md](/docs/mini_vault.md)                         | bash     |
| [youtube-music](/bin/youtube-music)             | [youtube-music.md](/docs/youtube-music.md)                   | bash     |     
| [youtube-audacity](/bin/youtube-audacity)       | [youtube-audacity.md](/docs/youtube-audacity.md)             | bash     |     
| [index-music](/bin/index-music)                 | [index-music.md](/docs/index-music.md)                       | bash     |
| [beep-file](/bin/beep-file)                     | [beep-file.md](/docs/beep-file.md)                           | python3  |
| [kclip](/bin/kclip)                             | [kclip.md](/docs/kclip.md)                                   | python3  |
| [sourcemap-extractor](/bin/sourcemap-extractor) | [sourcemap-extractor.md](/docs/sourcemap-extractor.md) | python3  |

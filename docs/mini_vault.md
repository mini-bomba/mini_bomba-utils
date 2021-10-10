# [mini_bomba vault](/bin/mini_vault)
## Encrypted file storage utility

### Requirements

* bash
* gpg
* tar
* gzip (and gunzip)
* pv
* du
* awk
* pkexec or sudo
* xdg-open (optional, one error will appear if missing, but the rest should work)

### Installation

Install the requirements, if not already met.

Generate a GPG key pair, if you do not have any or want to use a different one for encryption. (using `gpg --full-generate-key`)

Clone the repo & add it to the PATH, or download the file, put it in a directory on the PATH (such as `/usr/local/bin`, or `~/.local/bin`) and mark it executable.

### Usage

Run `mini_vault help` to see all available subcommands.

#### Creating a new vault

Run `mini_vault create <vault name>` to create a new, empty vault with the given name. If you want to use a specific GPG key pair for that vault, append the key ID at the end of the command.

#### Mounting the vault and editing it's contents

Run `mini_vault mount <vault name>` to begin the mounting progress. 

First, a prompt for password of the private key associated with the vault may appear, if specified during key generation. 
Then another prompt for your account password will appear, to create & mount a RAM disk for temporary decrypted file storage.
After authentication, the decryption process will begin. A progress bar will be displayed in the terminal.
When the files finish decrypting, the directory with the files will open in your file browser.

You may open, add, edit & delete files at this point.

When you finish using the files, press `return/enter` in the terminal to start saving and reencrypting the files & eventually unmount the vault.

If you did not edit the contents of the vault and want to just quickly unmount it, press `CTRL+C` in the terminal or send a `SIGINT` or `SIGTERM` signal to the process. 
The changes will not be saved.

When the files are saving, do not edit the contents of the vault. 
After files save, a prompt for your account password will appear, to unmount the RAM disk.

If gpg failed to encrypt files or the RAM disk could not be unmounted, the vault will return to a "mounted" state and you will have to press `return/enter` to try again.

This will not happen when the program fails if you pressed CTRL+C or if the process received `SIGINT` or `SIGTERM` signal. 
The program will exit without unmounting the RAM disk. 
To unmount the RAM disk manually, run `sudo umount mbv-$USER-<vault name>`

#### Deleting a vault

To delete a vault, you need to remove the associated `.mbv` file (which is just a `.tar.gz.gpg` file, but I decided to save them as `.mbv` ¯\\_(ツ)_/¯).
They are usually located in `~/.mini_bomba_vault` (the location can be changed using envirnoment variables)

#### Partially saved vault files

When the vault is being saved, it is first saved to a file with a `~` prefix.
If for any reason saving fails, the old vault state is preserved in it's old file.
For this reason, vault names cannot begin with `~`.

If a partially saved vault file of the vault you're trying to mount is detected (`~<vault name>`), the script will refuse to mount the vault.
If this happens, you should either remove it (if you know it has no important changes) or rename it and attempt to mount it.
Note that partially saved files may be... parially saved and corrupted, therefore mounting them directly is not permitted.

### Using environment variables to alter program's behaviour

mini_bomba vault accepts advanced parameters through environment variables.
They and their meaning are listed below:

* `MBV_RAMDISK_SIZE`: Alters the size of the RAM disk used for temporary decrypted file storage. Default value: `1G`. **WARNING: Specifying a value too small to fit all the files from your vault may result in data loss!**
* `MBV_FILE_LOCATION`: Specifies the location of encrypted `.mbv` files. Default value: `$HOME/.mini_bomba_vault`. May result in some vaults being unavailable, if stored in a different location than specified.
* `MBV_RAMDISK_LOCATION`: Specifies the location of RAM disk mount points for temporary decrypted file storage. Default value: `/tmp/mini_bomba_vault-$USER`. Make sure to use a directory you have access to.
* `MBV_USE_SUDO`: If set to any value, forces `sudo` (CLI auth) to be used instead of `pkexec` (GUI auth) for privilege elevation. 
* `MBV_SKIP_OPEN`: If set to any value, will not open the ramdisk location in the default file manager.

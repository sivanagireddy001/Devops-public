# rsync

* **rsync** is a widely used utility in Unix-based operating systems, for efficiently `copying` and `synchronizing` files between `directories`, `drives`, or across `networked computers`.

* **rsync** is designed to only copy the changes between files, making it a very efficient way to transfer large amounts of data or to keep files in sync across different locations.

* It uses a `delta-transfer algorithm` that only transfers the differences between files, rather than copying the entire file each time.

**Some common use cases for rsync**
* Creating backups of files or directories
* Syncing files between local and remote machines over a network
* Mirroring website or FTP content
* Copying files to external hard drives or USB drives
* Moving large files or directories between different locations

**basic syntax for rsync**
```
rsync [options] source destination
```
* In this command, `source` is the source directory or file, and `destination` is the target directory or file.

**Some commonly used options for rsync include**
* `-a` for archiving mode (which preserves file permissions, timestamps, and ownership).
* `-v` for verbose mode (which shows the progress of the transfer).
* `-z` for compressing data during the transfer.

For example, to copy the contents of the `/home/user/docs` directory to a remote server with IP address `192.168.1.100`, you can use the following command:
```
rsync -avz /home/user/docs/ user@192.168.1.100:/home/remoteuser/docs/
```
This will copy the contents of the `/home/user/docs` directory to the remote server at `/home/remoteuser/docs/`, using compression and preserving file permissions, timestamps, and ownership.
* `Note` that you will need to replace `user` and `remoteuser` with the appropriate usernames for your system.

<br></br>

# some useful rsync commands

* Copy files from one directory to another on the same system
```
rsync -av /path/to/source/directory/ /path/to/destination/directory/
```
* Copy files from a local system to a remote system
```
rsync -av /path/to/local/directory/ user@remote:/path/to/remote/directory/
```
* Copy files from a remote system to a local system
```
rsync -av user@remote:/path/to/remote/directory/ /path/to/local/directory/
```
* Copy files from a local system to a remote system with SSH key authentication
```
rsync -av -e "ssh -i /path/to/private/key" /path/to/local/directory/ user@remote:/path/to/remote/directory/
```
* Copy only the files that have changed
```
rsync -av --update /path/to/source/directory/ /path/to/destination/directory/
```
* Delete files from the destination directory that don't exist in the source directory
```
rsync -av --delete /path/to/source/directory/ /path/to/destination/directory/
```
* Dry-run `rsync` to see what changes would be made
```
rsync -av --dry-run /path/to/source/directory/ /path/to/destination/directory/
```


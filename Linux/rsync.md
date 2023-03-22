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













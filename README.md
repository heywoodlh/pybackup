# backutil
Python Backup Utility

## Description:
`backutil` is a wrapper for the python `tarfile` library. As `tarfile` is a standard Python library, using `backutil` will provide a cross-platform and simple backup utility.


## Installation:

Install using `pip`:

`sudo pip3 install backutil`


## Usage:

```
❯ backutil --help
usage: backutil [-h] --path PATH [PATH ...] --dest DEST [--webdav URL] [-z]
                [-v] [-q]

Python backup utility that supports uploading to Nextcloud/Owncloud.

optional arguments:
  -h, --help            show this help message and exit
  --path PATH [PATH ...]
                        path(s) to backup
  --dest DEST           destination of backup
  --webdav URL          WebDav URL to upload to
  -z, --zip             use gzip to compress the backup file
  -v, --verbose         enable verbose output
  -q, --quiet           suppress output
```

### Example commands:

Backup two files to a .tar archive:
`❯ backutil --path tmp.txt tmp2.txt --dest ~/Documents/file.tar`

Backup and compress to .tar.gz archive:
`❯ backutil --path tmp.txt tmp2.txt --dest ~/Documents/file.tar.gz -z`

Backup to a .tar archive verbosely:
`❯ backutil --path tmp.txt tmp2.txt --dest ~/Documents/file.tar -v`

Backup and compress to a .tar.gz archive, supressing output:
`❯ backutil --path tmp.txt tmp2.txt --dest ~/Documents/file.tar.gz -z -q`

Backup file and upload to Nextcloud Webdav (currently doesn't support uploading gzip files): 
`❯ backutil --path tmp.txt tmp2.txt --dest ~/file.tar --webdav 'https://cloud.example.com:8080/`


Currently WebDav functionality has only been tested on an instance of Nextcloud.

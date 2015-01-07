# Developer Cheat Sheet

## DNS

### Map IP Address
`nslookup example.com`

### Name Server Info
`host -t ns example.com`

### Flush DNS

#### Yosemite v10.10.x
`dscacheutil -flushcache`

#### Mavericks v10.9.x
`dscacheutil -flushcache; sudo killall -HUP mDNSResponder`

#### Mountian Lion v10.8.x or Lion v10.7.x
`sudo killall -HUP mDNSResponder`

#### Snow Leopard v10.6.x or v10.5.x Leopard
`dscacheutil -flushcache`

## Zip

### Compress

`zip -r archive_name.zip folder_to_compress`

### Compress without _MACOSX

`zip -r -X archive_name.zip folder_to_compress`

### Uncompress

`unzip archive_name.zip`

## Tar

### Creating a Tar.gz Archive

`tar -zcvf example.tar.gz folder_to_compress`

> z = Zip the archive <br>
> c = Create new archive <br>
> v = Verbose, meaning show me the processes <br>
> f = file name to be created <br>

### Un-tar to current directory

`tar -zxvf example.tar.gz`

### Un-tar to a different directory

`tar -C /folder -zxvf example.tar.gz`

### Uncompressing multiple tar.gz files from one directory to another

`for i in *.tar.gz; do tar xvzf $i -C ../folder; done`
> Destination folder must already exist

### Create Tar.gz of all folders within current directory

`for dir in */; do   base=$(basename "$dir");   tar -czf "${base}.tar.gz" "$dir"; done`

## Linux Disk Usage Info

### Get size of each folder in current directory

`du -sh */`

### Get size of specific folder

`du -sh example/`

### Get size of specific file

`du -sh example.mp4`

## Rename

### Renaming file extensions

`rename 's/.m4v$/.mp4/' *.m4v`
> Run to rename all `.m4v` extensions to `.mp4`

## Composer

### Clear Composer cache
`rm -rf ~/.composer/cache`

## Creating Symbolic Links
`ln -s /path/to/original /path/to/symlink`

## Git

### Clear Git Cache
- `git rm -r --cached .`
- `git add .`
- `git commit -m ".gitignore is now working"`

## MySQL Commands

### Export Database
`mysqldump -p -u username database_name > export_name.sql`

## Apache

### List Virtual Hosts
`httpd -S`


# Developer Cheat Sheet

## Flush DNS

### Mavericks v10.9.x
`dscacheutil -flushcache; sudo killall -HUP mDNSResponder`

### Mountian Lion v10.8.x or Lion v10.7.x
`sudo killall -HUP mDNSResponder`

### Snow Leopard v10.6.x or v10.5.x Leopard
`dscacheutil -flushcache`

## Stop .DS_Store

### Tiger v10.4.x and later
`defaults write com.apple.desktopservices DSDontWriteNetworkStores true`

## Tar

### Creating a Tar.gz Archive

`tar -zcvf file.tar.gz folder`

> z = Zip the archive <br>
> c = Create new archive <br>
> v = Verbose, meaning show me the processes <br>
> f = file name to be created <br>

### Uncompressing multiple tar.gz files from one directory to another

`for i in *.tar.gz; do tar xvzf $i -C ../folder; done`
> Destination folder must already exist

### Create Tar.gz of all folders within current directory

`for dir in */; do   base=$(basename "$dir");   tar -czf "${base}.tar.gz" "$dir"; done`

## Rename

### Renaming file extensions

`rename 's/.m4v$/.mp4/' *.m4v`
> Run to rename all `.m4v` extensions to `.mp4`

## Composer

### Clear Composer cache
`rm -rf ~/.composer/cache`

## Creating Symbolic Links
┌── ln(1) link, ln -- make links
│   ┌── Create a symbolic link.
│   │                         ┌── the path to the intended symlink
│   │                         │   can use . or ~ or other relative paths
│   │                   ┌─────┴────────┐
ln -s /path/to/original /path/to/symlink
      └───────┬───────┘
              └── the path to the original file/folder
                  can use . or ~ or other relative paths

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

### Creating a Tar Archive

ex. `tar -zcvf file.tar.gz folder`

- z = Zip the archive
- c = Create new archive
- v = Verbose, meaning show me the processes
- f = file name to be created


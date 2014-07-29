# Mac OS X

## Flush DNS

### Mavericks 10.9.x
`dscacheutil -flushcache; sudo killall -HUP mDNSResponder`

### Mountian Lion 10.8.x or Lion 10.7.x
`sudo killall -HUP mDNSResponder`

### Snow Leopard 10.6.x or 10.5.x Leopard
`dscacheutil -flushcache`

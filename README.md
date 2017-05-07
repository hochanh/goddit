## Golang chat server 🏓
### See it in action at [goddit.pro](http://goddit.pro)

============================

##### Try it out!

+ Install mongodb
+ Clone repo to `$GOPATH/src/github.com/octohedron/goddit`
+ Modify IP and domain in the html files and `main.go`, it can be localhost, a vagrant instance or a different server
+ Install dependencies
```Bash
$ go get
```
+ Build the binary
```Bash
$ go build
```
+ Set environment variables
```Bash
# from reddit.com/prefs/apps
$ export APPID=YOUR_APP_ID
$ export APPSECRET=YOUR_APP_SECRET
```
+ Run it
```Bash
$ nohup ./goddit &
```

## Features

+ Crawls popular subreddits (first 25) and adds them as chatrooms in a separate `goroutine` when you start the program
+ Loads previous chatroom history (up to 150 messages) when switching rooms
+ Authorizes via reddit and pairs a `cookie` with a user in the server, then adds the IP to a pool of allowed IPs to connect via `WebSockets`
+ Only broadcasts messages to those present in the room, not to others in different rooms
+ Autogenerated avatars from placeskull.com
+ Moderators have purple avatar
+ Others have red avatar 
+ Sender has blue avatar
+ Enforces a single WebSocket for each client, closing the connection when switching rooms
+ Each client runs on it's own `goroutine`

##### CONTRIBUTING: Yes

LICENSE: MIT
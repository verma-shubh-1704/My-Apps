# Chat App

This is the commands of the chat-app.

> We use npm to install all depedencies and devDepedencies.

> The libraries used to make this is socket.io and node.js express.

```
- npm install express.
- npm install node.js.
- npm install socket.io.
```
Brief details of project

```
const express = require('express')
const http = require('http')
const path = require('path')
const socketio = require('socket.io')
```
Create express APP, server and IO

```
const app = express()
const server = http.createServer(app)
const io = socketio(server)
```

```
io.on('connection', (socket) => {
...
...
...
})
```

###### sending message to client
> socket.emit('message', getMessage('Admin', 'Welcome!'))

###### client socket connection joining a room
> socket.join(message.room)

###### boradcasting a message to all users in room except the current client
> socket.broadcast.to(message.room).emit('message', getMessage('Admin', `${message.username} has joined!`))

###### boradcasting a message to all users in room
> io.to(message.room).emit('roomData', { room: message.room, users: usersInRooms })

> © Shubh-Soft

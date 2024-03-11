---
title: Lab 16 Notes
---

### Socket.io Documentation
The [socket.io documentation pages](https://socket.io/docs/v4/) offer a lot of helpful context and guidance for working with sockets. Note that we are using sockets *with our existing express servers*

------

### Task 1
In this task, you need to allow your chat users to set their usernames. While this could be a completely *client-side* operation (with input being saved as a HTML label, and prepended to the textarea message string), **Task 3** will require the server to know the usernames too. Try to create a solution that will report the user to the server too, and ensure the server is keeping track of users! 

<details>
  <summary> Hint: Socket Identifiers</summary>
  
  On the server-side, every socket connection (from each user) has a *unique id*. See the docs [here](https://socket.io/docs/v4/server-socket-instance/#socketid). 

</details>

### Task 2
In this task, you extend the functionality of your chat service to allow users to join chatrooms. To implement this, you will need some form of input that allows users to choose a room to chat in. Socket.io have helpful [room docs](https://socket.io/docs/v4/rooms/). 

### Task 3
In the lab, we have only shown you one functionality of the `emit` function. However, there are many things it can do. Check the [emit docs](https://socket.io/docs/v4/emit-cheatsheet/) for guidance on this task.


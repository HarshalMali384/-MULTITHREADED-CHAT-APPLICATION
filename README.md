# -MULTITHREADED-CHAT-APPLICATION

COMPANY: CODTECH IT SOLUTIONS

NAME: HARSHAL MALI

INTERN ID: CT08QVR

DOMAIN: JAVA PROGRAMMING

DURATION: 4 WEEEKS

MENTOR: NEELA SANTOSH


description  -- 
1. Server.java

Core Functionality:
This class sets up the server-side of the chat application. It listens for incoming client connections on a specified port (1234 in this case).
It utilizes a ServerSocket to accept client connections.
When a client connects, it creates a new ClientHandler thread to manage communication with that client.
The server runs in a continuous loop, accepting new connections until the ServerSocket is explicitly closed.
Multithreading:
Each connected client is handled by a separate ClientHandler thread. This allows the server to handle multiple clients concurrently without blocking.
Key Components:
ServerSocket: Listens for incoming client connections.
Socket: Represents the connection to a specific client.
ClientHandler: A separate class (described below) that handles communication with each client.
startServer(): Starts the server loop, accepting client connections.
closeServerSocket(): Closes the server socket.
main(): Creates a ServerSocket and starts the server.
Error Handling:
Basic try-catch blocks are used to handle IOException during socket operations.
Limitations:
The server's error handling is minimal. It simply catches and ignores IOExceptions in the main loop, which could hide potential issues.


2. Client.java

Core Functionality:
This class represents the client-side of the chat application.
It connects to the server using a Socket.
It allows the user to send messages to the server and receive messages from other clients.
The client creates two threads. One to send messages, and one to listen for messages.
Key Components:
Socket: Represents the connection to the server.
BufferedReader: Reads messages from the server.
BufferedWriter: Sends messages to the server.
sendMessage(): Sends messages entered by the user to the server.
ListenForMessage(): Listens for messages from the server and displays them.
closeEverything(): Closes the socket and I/O streams.
main(): Connects to the server, gets the users name, and starts the send and recieve threads.
Client-Server Interaction:
The client sends its username to the server upon connection.
Messages are sent and received using BufferedReader and BufferedWriter.
Error Handling:
The closeEverything() method ensures that resources are closed properly in case of errors.
Limitations:
The client relies on the server to broadcast messages.
There is no way to close the client except by closing the terminal.




3. ClientHandler.java

Core Functionality:
This class handles communication with a single client on the server side.
It reads messages from the client and broadcasts them to all other connected clients.
It maintains a list of all connected clients.
Multithreading:
Each ClientHandler runs in its own thread, allowing the server to handle multiple clients concurrently.
Key Components:
Socket: Represents the connection to the client.
BufferedReader: Reads messages from the client.
BufferedWriter: Sends messages to the client.
clientUsername: Stores the username of the client.
clientHandlers: A static ArrayList that stores all connected ClientHandler instances.
run(): Reads messages from the client and broadcasts them.
broadcastMessage(): Sends a message to all connected clients except the sender.
removeClientHandler(): Removes the client from the list of connected clients.
closeEverything(): Closes the socket and I/O streams.
Data Handling:
Messages are sent and received using BufferedReader and BufferedWriter.
The broadcastMessage() method iterates through the clientHandlers list and sends the message to each client.
Error Handling:
The closeEverything method closes all streams and the socket.
Limitations:
The application does not have a graceful shutdown, or a way to see a list of users.
Error handling is basic.
The server does not save chat logs.



This Java code provides a basic, functional chat application using sockets and multithreading. The server listens for client connections, and each connected client is managed by a separate thread. Clients can send and receive messages, which are broadcasted to all other connected clients. While functional, the application has limitations in terms of error handling, features, and robustness. Potential improvements include adding more robust error handling, implementing user authentication, adding chat history, and improving the user interface.



Output-- 

![Image](https://github.com/user-attachments/assets/7e64c395-0de0-4ec4-b488-1c4c22245de9)
![Image](https://github.com/user-attachments/assets/8cfe293e-70c8-41af-9462-f77a86f5d04c)
![Image](https://github.com/user-attachments/assets/828cb1a4-545d-42e6-80c4-c58935751132)


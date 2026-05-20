# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
## ECHO_SERVER:
```
import socket

# Create socket object
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Host and port
host = '127.0.0.1'
port = 5000

# Bind socket
server_socket.bind((host, port))

# Listen for incoming connections
server_socket.listen(1)
print("Echo Server is waiting for connection...")

# Accept client connection
client_socket, addr = server_socket.accept()
print("Connected to:", addr)

while True:
    # Receive message from client
    data = client_socket.recv(1024).decode()

    # If client disconnects
    if not data:
        break

    print("Client:", data)

    # Send same message back (Echo)
    client_socket.send(data.encode())

# Close connections
client_socket.close()
server_socket.close()
```
## ECHO_CLIENT:
```
import socket

# Create socket object
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Server details
host = '127.0.0.1'
port = 5000

# Connect to server
client_socket.connect((host, port))

while True:
    # Input message
    message = input("Enter message: ")

    # Send message to server
    client_socket.send(message.encode())

    # Exit condition
    if message.lower() == 'exit':
        break

    # Receive echoed message
    data = client_socket.recv(1024).decode()
    print("Server echoed:", data)

# Close socket
client_socket.close()
```
## OUPUT
## ECHO_SERVER:

<img width="1061" height="252" alt="image" src="https://github.com/user-attachments/assets/34006195-0f49-4673-9cdb-ea1e7ef4abd8" />

## ECHO_CLIENT:

<img width="1087" height="307" alt="image" src="https://github.com/user-attachments/assets/87620340-de67-4b49-b667-101d0a93769c" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.

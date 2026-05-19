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
echo_server.py
```
import socket
server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

server.bind(('localhost', 5000))


server.listen(1)

print("Server is waiting for connection...")

conn, addr = server.accept()

print("Connected by:", addr)

while True:
    # Receive data from client
    data = conn.recv(1024).decode()

    if not data:
        break

    print("Client:", data)

    conn.send(data.encode())

conn.close()
server.close()
```


echo_client.py
```
import socket
client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

client.connect(('localhost', 5000))

while True:
    
    msg = input("Enter message: ")

    client.send(msg.encode())

    data = client.recv(1024).decode()

    print("Server replied:", data)

    if msg.lower() == "exit":
        break

# Close connection
client.close()
developed by : R.Rachanaa
ref no:212225040322
```
## OUPUT
echo_server.py

<img width="437" height="220" alt="image" src="https://github.com/user-attachments/assets/bb2f1d0a-2f99-4d08-91d7-445bac121462" />

echo_client.py

<img width="428" height="252" alt="image" src="https://github.com/user-attachments/assets/35ac642e-a4d0-47ed-a6bf-7cbbdeb9b6d5" />


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.

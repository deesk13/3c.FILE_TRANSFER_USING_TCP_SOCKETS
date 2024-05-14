# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
# NAME: DEVA DHARSHINI

# REGISTER NO: 212223240026
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format. 
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
CLIENT
```
import socket

def receive_file(filename, server_socket):
    with open(filename, 'wb') as file:
        while True:
            data = server_socket.recv(1024)
            if not data:
                break
            file.write(data)

def start_client():
    client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    client_socket.connect(('127.0.0.1', 5555))

    filename = input("Enter filename to save: ")
    client_socket.sendall(filename.encode())

    receive_file(filename, client_socket)
    print(f"File '{filename}' received successfully")

    client_socket.close()

start_client()
```
SERVER
```
import socket

def receive_file(filename, server_socket):
    with open(filename, 'wb') as file:
        while True:
            data = server_socket.recv(1024)
            if not data:
                break
            file.write(data)

def start_client():
    client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    client_socket.connect(('127.0.0.1', 5555))

    filename = input("Enter filename to save: ")
    client_socket.sendall(filename.encode())

    receive_file(filename, client_socket)
    print(f"File '{filename}' received successfully")

    client_socket.close()

start_client()
```
## OUPUT
CLIENT
![Screenshot 2024-05-07 090248](https://github.com/deesk13/3c.FILE_TRANSFER_USING_TCP_SOCKETS/assets/150927063/2f39f9e3-5177-476b-a839-1783086f0fd4)
SERVER
![Screenshot 2024-05-07 090302](https://github.com/deesk13/3c.FILE_TRANSFER_USING_TCP_SOCKETS/assets/150927063/3e44388c-75d1-4ab9-a601-0f6676992f7f)

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.

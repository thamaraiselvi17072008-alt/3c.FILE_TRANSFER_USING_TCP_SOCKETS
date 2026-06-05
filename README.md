# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
SERVER
```
import socket
server = socket.socket()
server.bind(("127.0.0.1", 5555))
server.listen(1)
print("Server waiting for connection...")
client, addr = server.accept()
print("Connected to:", addr)
filename = input("Enter file name to send: ")
with open(filename, "rb") as file:
    data = file.read()
    client.send(data)
print("File sent successfully")
client.close()
server.close()
```
CLIENT
```
import socket
client = socket.socket()
client.connect(("127.0.0.1", 5555))
save_name = input("Enter name to save file: ")
data = client.recv(1000000)
with open(save_name, "wb") as file:
    file.write(data)
print("File received successfully")
client.close()
```
## OUPUT

SERVER OUTPUT :

<img width="351" height="136" alt="image" src="https://github.com/user-attachments/assets/32efaa0c-2755-4f58-b887-bdd74482b012" />

SAMPLE.TXT :

<img width="374" height="91" alt="image" src="https://github.com/user-attachments/assets/88b84ca3-dc50-4825-aae0-4cf44b0a9d3a" />

CLIENT OUTPUT :

<img width="391" height="103" alt="image" src="https://github.com/user-attachments/assets/1118fef0-61b6-418a-ba0d-604ab462d4a4" />

RECEIVED.TXT :

<img width="385" height="94" alt="image" src="https://github.com/user-attachments/assets/5dad99c7-4fe2-4a33-a3f2-2f30e71f8892" />

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.

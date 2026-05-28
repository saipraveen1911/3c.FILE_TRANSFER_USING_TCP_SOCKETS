# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS

## AIM:

To write a python program for creating File Transfer using TCP Sockets Links

## ALGORITHM:

1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
   
## PROGRAM:

Server3C_FTP.py:

```
import socket 
 
# Create socket 
server = socket.socket() 
 
# Bind IP and port 
server.bind(("127.0.0.1", 5555)) 
 
# Listen for client 
server.listen(1) 
 
print("Server waitng for connecton...") 
 
# Accept client 
client, addr = server.accept() 
 
print("Connected to:", addr) 
 
# Ask FileName 
flename = input("Enter fle name to send: ") 
 
# Open and send file 
with open(flename, "rb") as fle: 
 
    data = fle.read() 
 
    client.send(data) 
 
print("File sent successfully") 
 
# Close connectons 
client.close() 
server.close() 

```
Client3C_FTP.py:

```
import socket 
 
# Create socket 
client = socket.socket() 
 
# Connect to server 
client.connect(("127.0.0.1", 5555)) 
 
# Save fle name 
save_name = input("Enter name to save fle: ") 
 
# Receive data 
data = client.recv(1000000) 
 
# Save fle 
with open(save_name, "wb") as fle: 
 
    fle.write(data) 
 
print("File received successfully") 
 
# Close connecton 
client.close()

```

## OUPUT:

Server3C_FTP.py:

<img width="1915" height="970" alt="server3c" src="https://github.com/user-attachments/assets/aa8b23a8-4df6-40e2-8e45-c4dc7dced1c9" />

Client3C_FTP.py:

<img width="1915" height="961" alt="client3c" src="https://github.com/user-attachments/assets/13098a35-dbfd-447f-835f-d0f869d5571c" />

## RESULT:

Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.

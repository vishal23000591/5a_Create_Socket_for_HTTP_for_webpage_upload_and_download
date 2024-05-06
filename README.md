# 5a_Create_Socket_for_HTTP_for_webpage_upload_and_download
## NAME: Vishal S
## REGISTER NUMBER: 212223110063

## AIM :
To write a PYTHON program for socket for HTTP for web page upload and download
## Algorithm

1.Start the program.
<BR>
2.Get the frame size from the user
<BR>
3.To create the frame based on the user request.
<BR>
4.To send frames to server from the client side.
<BR>
5.If your frames reach the server it will send ACK signal to client otherwise it will send NACK signal to client.
<BR>
6.Stop the program
<BR>
## Program 
```
import socket

def handle_request(request):
    # Process the HTTP request and generate an appropriate response
    response = "HTTP/1.1 200 OK\nContent-Type: text/html\n\n<h1>Hello, World!</h1>"
    return response

def main():
    host = ''  # Listen on all available interfaces
    port = 8080  # Port number for HTTP server

    server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    server_socket.bind((host, port))
    server_socket.listen(5)  # Listen for incoming connections

    print("HTTP server listening on port", port)

    while True:
        client_socket, client_address = server_socket.accept()  # Accept a new connection
        print("Client connected:", client_address)

        request_data = client_socket.recv(1024).decode()  # Receive request data from the client
        print("Received request:\n", request_data)

        response = handle_request(request_data)  # Handle the request
        client_socket.sendall(response.encode())  # Send the response back to the client

        client_socket.close()  # Close the connection

if __name__ == "__main__":
    main()

# 
# copy and paste to any browser http://localhost:8080
```
## OUTPUT
![326661613-387f1cdf-dadc-4876-9a0d-de058d35c14b](https://github.com/vishal23000591/5a_Create_Socket_for_HTTP_for_webpage_upload_and_download/assets/147139719/3c1c775b-71cc-4eda-934c-6b7febf426d4)
![326661515-9d0014a6-8f67-48ba-b775-fb4b75ea30f9](https://github.com/vishal23000591/5a_Create_Socket_for_HTTP_for_webpage_upload_and_download/assets/147139719/a7123fe9-7264-4ce4-bf6e-fcc5616d530c)

## Result
Thus the socket for HTTP for web page upload and download created and Executed

# HttpServerInC
# Simple C HTTP Server

A lightweight HTTP/1.1 web server built from scratch in C using standard POSIX sockets. It binds to a custom port, prints browser requests, and runs continuously inside a loop to serve a static HTML page.

## Prerequisites

You need a POSIX-compliant system (Linux or macOS) and a C compiler like GCC.

## How to Compile and Run

1. Compile the code:
   ```bash
   gcc main.c -o server
   ```

2. Start the server by passing a port number:
   ```bash
   ./server 8080
   ```

3. Test it in your web browser or terminal:
   ```bash
   curl -i http://localhost:8080
   ```

## Running in the Background

To keep the server live even after closing your terminal window, run:
```bash
nohup ./server 8080 > server.log 2>&1 &
```

To stop the background server:
```bash
killall server
```

## How It Works

* `socket()`, `bind()`, and `listen()` setup the server port.
* A `while(1)` loop catches connections using `accept()`.
* It reads the request with `read()`, sends HTML with `write()`, and closes the client connection.

## License
MIT

# Simple http server running in C++

# requirements

I used boost 1.79.0, installed like this.

I installed it in my WSL. These are the commands I used

```
wget -O boost_1_79_0.tar.gz https://sourceforge.net/projects/boost/files/boost/1.79.0/boost_1_79_0.tar.gz/download
tar xzvf boost_1_79_0.tar.gz
cd boost_1_79_0

sudo apt-get update
sudo apt-get install build-essential g++ python-dev autotools-dev libicu-dev libbz2-dev libboost-all-dev

sudo ./bootstrap.sh --prefix=/usr/
sudo ./b2
sudo ./b2 install

```

This installs the c++ libraries into `/usr/include/boost`. All libraries used here are *header-only*, meaning no `g++` additional file included when compiling are needed.

The `server.cpp` is a simple HTTP server, that should have all the things needed for a functioning REST API. All responses are JSON data, indicated with header `Content-Type: application/json`.

Compile with:

```
g++ -pthread -o server server.cpp
```

Run with (in WSL):

```
sudo ./server 0.0.0.0 80
```

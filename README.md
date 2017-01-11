## sendosc
sendosc is a simple command-line tool for sending OSC packet.

## usage
```
sendosc
usage : sendosc dst_host dst_port path [[type] [param]] ...
 
   type
     i : int
     f : float
     b : boolean (true/false)
     s : string
 
   example
     ./sendosc 127.0.0.1 5678 /test1 i 123
     ./sendosc 127.0.0.1 5678 /test2 f 123.45
     ./sendosc 127.0.0.1 5678 /test3 s teststring
     ./sendosc 127.0.0.1 5678 /test4 b true
     ./sendosc 127.0.0.1 5678 /test5 s teststring i 123 f 123.4 b false
```

## how to install
### install oscpack dependencies
#### debian & ubuntu
```
sudo apt-get install liboscpack-dev
```
#### Mac OS X 
```
cd ~
curl -O https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/oscpack/oscpack_1_1_0.zip
unzip oscpack_1_1_0.zip
cd oscpack_1_1_0
make
sudo make install
```

#### Arch
##### get dependencies and prepare folder
````
sudo pacman -Sy
sudo pacman -S git curl unzip
cd ~
curl -O https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/oscpack/oscpack_1_1_0.zip
unzip oscpack_1_1_0.zip
cd oscpack_1_1_0
```

##### enable -fpic flag for shared library linking
```
nano Makefile 
```
change this line
```
COPTS = -Wall -O3
```
for this one
```
COPTS = -Wall -O3 -fPIC
```
##### compile and install 
```
make
sudo make install
```

### clone, compile and install sendosc 
#### OSX
```
cd ~
git clone https://github.com/yoggy/sendosc.git
cd sendosc
cmake .
make
sudo make install  
```

#### arch : 
```
cd ~
git clone https://github.com/gllmar/sendosc.git
cd sendosc
sudo pacman -S cmake
cmake .
make
sudo cp ./sendosc /usr/local/bin/sendosc
```


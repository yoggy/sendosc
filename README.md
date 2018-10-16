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

#### macOS 
```
cd ~
git clone https://github.com/arturoc/oscpack
cd oscpack 
make
sudo make install
```

Install cmake via [Homebrew](https://brew.sh/)
```
brew install cmake
```

#### Archlinux
##### get dependencies and prepare folder
````
cd ~
git clone https://github.com/arturoc/oscpack
cd oscpack 
````

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
#### debian, ubuntu , macOS
```
cd ~
git clone https://github.com/yoggy/sendosc.git
cd sendosc
cmake .
make
sudo make install  
```

#### arch 
```
cd ~
git clone https://github.com/yoggy/sendosc.git
cd sendosc
sudo pacman -S cmake
cmake .
make
sudo cp ./sendosc /usr/local/bin/sendosc
```


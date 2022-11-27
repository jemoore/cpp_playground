# Conan
This directory contains an example of using conan, specifically to download
and compile sfml.

The main.cpp file contains an example from the SFML web site which creates a
window containing a green circle.
See: https://www.sfml-dev.org/tutorials/2.5/start-linux.php


## Conan installation
This assumes that conan is already installed (pip install conan)
See: https://conan.io/downloads.html


## Modifications to conan profile
On my first attempt(s) I was getting a crash when running the example.  The
window would appear briefly then disappear and an error message was displayed
on the console.

The solution was to change a line in ~/.conan/profiles/default:
```compiler.libcxx=libstdc++```
to
```compiler.libcxx=libstdc++11```


# Building the example
```
mkdir -p build
cd build

conan install .. --build=missing
cmake ..
cmake --build . --config RELEASE
```

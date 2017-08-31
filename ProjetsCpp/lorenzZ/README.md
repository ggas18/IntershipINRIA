#For variable Z, this target is previous to lorenzY
# mecsycoCppWrapper
This project implements a wrapper library for a Java code using JNI with native code in C++

## Necessary tools to compile this project on ubuntu
1. install boost on your computer

2. install cmake by following this link:
https://askubuntu.com/questions/610291/how-to-install-cmake-3-2-on-ubuntu-14-04

3. install make: sudo apt-get install build-essential

## Compile this project
It's easy to compile this project
1. Create a new directory build and enter this directory
mkdir build && cd build

2. Enter in this directory
cmake .. && make

#cmake take as parameter the directory witch contents CMakeLists.txt file
#the library generated will be in the build directory with the so extension.
#you can change the library name by the name you want

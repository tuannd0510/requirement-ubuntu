# Tutorial 1 - Cross-compile toolchain

Install ARM-targeted cross-compilation toolchain on your Linux PC following the following step-by-step instruction.
https://www.acmesystems.it/arm9_toolchain

Afterwards, write simple programs (e.g. helloworld) in C and in C++, cross-compile and run them. You may use command #file to view the output binary. 
For a comprehensive overview of cross-compilation, watch tutorial  https://www.youtube.com/watch?v=Pbt330zuNPc&ab_channel=TheLinuxFoundation.

- Install the Cross Compilers, utilities, etc.:
```
sudo apt-get install gcc-arm-linux-gnueabi g++-arm-linux-gnueabi
```
- cross C compiler:
```
#include "stdio.h"
 
int main(void) {
  printf("Hello world !\n");
  return 0;
}
```
- Compile it by typing, if you are using an Arietta, Aria or FOX G20 board:
```
arm-linux-gnueabi-gcc hello.c -o hello
```
- Copy the executable file on the board via ssh:
```
scp hello root@[your_board_ip]:/root
```

# Tutorial 2 - Working with IDE and emulator

Create, build, download, run, and debug your first embedded project:

Install Eclipse and Eclipse Embedded CDT: https://projects.eclipse.org/projects/iot.embed-cdt	
Install Qemu plugin as device emulator: https://xpack.github.io/qemu-arm/install/
	
Create your first hello program;	
Run a simple debug session on an ARM target.

Follow the instructions to fulfil the steps above: https://eclipse-embed-cdt.github.io/debug/qemu/.
Post a screenshot here to show that you are successful in your first program.


# BTL

# Table of Contents
1. [Description](#Description)
2. [Install](#Install)
3. [Installation-with-yay](#Installation-with-yay)
4. [Installation-from-source](#Installation-from-source)
5. [Installation-from-AUR](#Installation-from-AUR)
6. [Getting-Started](#Getting-Started)
7. [Examples](#Examples)

# Description
Assertion module for gfortran, It is a simple module which adds an assertion function, It works by enabling `-cpp` the [c preprocesor](https://gcc.gnu.org/onlinedocs/gfortran/Preprocessing-Options.html) directives in the fortran compiler, many fotrans compilers have this functionality.
# Install
## Installation-with-yay
If you have yay installed, just run this command.
```
yay -S assert-fortran-git
```
## Installation-from-AUR
This is the [link](https://aur.archlinux.org/assert-fortran-git.git) of the repo in AUR, then with git you can install the module, just run these two commands.
```
git clone https://aur.archlinux.org/assert-fortran-git.git
cd assert-fortran-git
makepkg -si
```
## Installation-from-source
Before installing make sure that you have these dependencies to be able to compile the project.
1. [ar](https://man.archlinux.org/man/ar.1.en)
2. [make](https://man.archlinux.org/man/make.1)
3. [ranlib](https://man.archlinux.org/man/ranlib.1)
4. [gfortran](https://man.archlinux.org/man/gfortran.1)

You can download the latest [realese](https://github.com/alecksandr26/Fortran-Assertion-Module/releases) of the project, then to install the dependency you only will need to run the makefile with these flags.
```
make install
```
The `.mod` file should be installed in `/usr/include/` and the `.a` file should be installed in
`/usr/lib/` and obviously, this operation will require sudo permission.
If you want to do it manually, you will find the `.mod` file and `.a` file in the `build/` directory.
# Getting-Started
As I said before this module works by enabling `-cpp` the [c preprocesor](https://gcc.gnu.org/onlinedocs/gfortran/Preprocessing-Options.html) directives,
then inside of the module where you want to make assertions, you only need to include the header file `assertf.h`, thats why you need the flag `-cpp`.
```
#include <assertf.h>
```
Then to compile the modules or the program, you need to set these flags.
```
gfortran -cpp your-program.f90 -I/usr/include -lassert
```
The `-lassert` refers to the `.a` library and the `-I/usr/include` is needed to be able to include the `assert` module and `assertf.h` header. 

# Examples
## Picture Example
This is an example of a failed assertion.
![ArcoLinux-2023-02-11-22-1676176413_screenshot](https://user-images.githubusercontent.com/66882463/218293166-c2df5e93-522b-4b2e-baed-5fbc2204b16d.png)


![ArcoLinux-2023-02-11-22-1676176464_screenshot](https://user-images.githubusercontent.com/66882463/218293187-4bb0351c-a823-4a6c-9074-4338943b7e72.png)
## Video Example
https://user-images.githubusercontent.com/66882463/218293263-c756db72-f0e6-4f39-b420-5ef6d5a1cb9f.mp4

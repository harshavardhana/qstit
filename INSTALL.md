# Qstit

## Install

These are instructions for compiling Qstit from the source code. If you just want to use the program, easier methods are available, please see our webpage: http://subtitles.nova-cinema.org

### Linux

- Install the packages "libqt4-dev" (that includes the needed Qt libraries) and "build-essential", by typing the following command in a terminal:
```
sudo apt-get install libqt4-dev build-essential
```

- Open a terminal in the 'qstit' folder of the sources and type the following commands:
```
qmake src && make
```

An executable file named "qstit" is created. Double-click it to start the program.

- If you want Qstit to appear in the list of applications on your system, install it by typing:
```
sudo make install
```

To display the application icon correctly, you will also need to update the icon cache:
```
gtk-update-icon-cache -q -t -f /usr/share/icons/hicolor/
```

(for Ubuntu at least)

### Windows

Install the necessary tools (you can use Visual Studio, but we provide instructions for MinGW):

- You will first need to install MinGW, but note that in order to run with the latest version of Qt4, you will need an older version of MinGW (the one with GCC 4.4). It can be found in their archive or on various forums...
The latest installer from the MinGW website probably won't work correctly.

- Once you have the right version of MinGw installed, you can download and install the Qt librairies. Get version 4 (Qstit doesn't work with Qt5 yet) from the www.qt-project.org website. Choose the version for MinGW.

- Download the sources, and in the 'src' folder, run the following commands:

```
qmake
mingw32-make
```

- You can create a BAT file to execute the commands and make sure the environment variables are correctly defined for the paths of Qt and MinGW. Here is a simple model, copy and paste this in a simple text file name with the .bat extension, then run it to compile Qstit. You will need to change the PATH according to your system.

```
@echo off
echo Qstit make
echo ----------

set QTDIR=C:\Qt\4.8.4
set PATH=%PATH%;C:\Qt\4.8.4\bin
set PATH=%PATH%;C:\MinGW\bin
set PATH=%PATH%;%SystemRoot%\system32
set QMAKESPEC=win32-g++

qmake
mingw32-make

echo - Done -
pause
```

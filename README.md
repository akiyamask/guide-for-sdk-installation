# guide-for-sdk-installation
First we neeg to install these 5 softwares.

![a](https://github.com/akiyamask/guide-for-sdk-installation/blob/main/toolchains.png)

ARM：Be sure to tick all of these four boxes.
![a](https://github.com/akiyamask/guide-for-sdk-installation/blob/main/arm.png)

CMAKE:Add CMake to the system PATH for all users when prompted by the installer
![a](https://github.com/akiyamask/guide-for-sdk-installation/blob/main/cmake.png)

BUILDTOOLS FOR VISUALSTUDIO: NOTE: It is not VS COMMUNCITY
![a](https://github.com/akiyamask/guide-for-sdk-installation/blob/main/vsbtool.png)

PYTHON: Ensure that it’s installed 'for all users' and add Python 3.10 to the system PATH when prompted by
the installer.Additionally disable the MAX_PATH length limit when prompted at the end of the Python
installation
![a](https://github.com/akiyamask/guide-for-sdk-installation/blob/main/python.png)

GIT: Ensure you tick the checkbox to allow Git to be used from 3rd-party software and, unless you have a strong reason
otherwise, when installing Git you should also check the box "Checkout as is, commit as-is", select "Use Windows'
default console window", and "Enable experimental support for pseudo consoles" during the installation process.
![a](https://github.com/akiyamask/guide-for-sdk-installation/blob/main/git.png)

Next let us get the SDK.
In your cmd input these orders before which please create a Users\pico\Downloads path as shown like this.
Ok, let's bounce.

C:\Users\pico\Downloads> git clone -b master https://github.com/raspberrypi/pico-sdk.git
You will get a new folder named pico-sdk in your Downloads folder.

C:\Users\pico\Downloads> cd pico-sdk
C:\Users\pico\Downloads\pico-sdk> git submodule update --init
C:\Users\pico\Downloads\pico-sdk> cd ..
C:\Users\pico\Downloads> git clone -b master https://github.com/raspberrypi/pico-examples.git

You will get this results if succeed.



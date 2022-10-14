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

You will get these results if succeed.
![a](https://github.com/akiyamask/guide-for-sdk-installation/blob/main/1.png)

Then set the path with this NOTE the "..\.." is exactly this but not something else. Just copy and paste.
C:\Users\pico\Downloads> setx PICO_SDK_PATH "..\..\pico-sdk"

You will get these results if succeed.
![a](https://github.com/akiyamask/guide-for-sdk-installation/blob/main/2.png)

Then 
C:\Users\pico\Downloads> cd pico-examples
C:\Users\pico\Downloads\pico-examples> mkdir build
C:\Users\pico\Downloads\pico-examples> cd build
C:\Users\pico\Downloads\pico-examples\build> cmake -G "NMake Makefiles" ..


You will get these results if succeed.
![a](https://github.com/akiyamask/guide-for-sdk-installation/blob/main/3.png)

Then
C:\Users\pico\Downloads\pico-examples\build> nmake
You will get these results if succeed. NOTE this is a long installation process.(0%-100%)
![a](https://github.com/akiyamask/guide-for-sdk-installation/blob/main/4.png)

Next you have to install the visual studio code.
After installation open a Developer Command
Prompt window from the Windows Menu, by selecting Windows > Visual Studio 2022 > Developer Command Prompt for VS2022
from the menu. Then type (in the Developer Command Prompt for VS2022 but not the cmd)
C:> code
then the vscode will be launched.
We’ll now need to install the CMake Tools extension. Click on the Extensions icon in the left-hand toolbar (or type Ctrl +
Shift + X), and search for "CMake Tools" and click on the entry in the list, and then click on the install button.

Then click on the Cog Wheel at the bottom of the navigation bar on the left-hand side of the interface and select
"Settings". Then in the Settings pane click on "Extensions" and then "CMake Tools". Then scroll down to "Cmake:
Configure Environment". Click on "Add Item" and set the PICO_SDK_PATH to be ..\..\pico-sdk

Like this
![a](https://github.com/akiyamask/guide-for-sdk-installation/blob/main/5.png)

Then Additionally you will need to scroll down to "Cmake: Generator" and enter "NMake Makefiles" into the box.
Like this
![a](https://github.com/akiyamask/guide-for-sdk-installation/blob/main/6.png)

Next select open folder on the left-up side of the vscode. Select your pico-example in Downloads folder.
And click the build at the bottom of the vscode ( Remember to choose the GCC for arm-none-eabi)
Consequently, you will enter a build process like this
![a](https://github.com/akiyamask/guide-for-sdk-installation/blob/main/7.png)

After this you can close your vscode to find the uf2 file in your users/   /pico/Downloads/pico-examples/bulid/......
For instance, you find the build file named hello_usb.uf2 which is transfered from hello_usb.c.
You can drag it in your RP2040's saving area and it will run automatically! Through your serial you can see it.
Like this
![a](https://github.com/akiyamask/guide-for-sdk-installation/blob/main/8.png)

Anyway, we can use c file to edit the code, after which we build it into uf2 file and run it with RP2040.

















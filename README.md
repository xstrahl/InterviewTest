# Interview Test
Welcome to Xstrahl's software interview test. This test will challenge you to apply your programming knowlege to setting up a Qt5 based desktop GUI application using C++ and CMake. 

## Prerequisites
To get started you'll need to install the following:
* [Qt5](https://www.qt.io/download) (Download the open source version, install the latest version).
* [CMake](https://cmake.org/download/)
* A C++ IDE of your choice (if you don't have one already).
    * Note that your submission will be built in Visual Studio 2019 on a Windows 10 machine.
* Fork this repository to get started on your solution. 

## Project Description
Your task is to build a simple GUI application that has the ability to open a `.raw` image file. A test `.raw` file will be provided for you. The main GUI for the application has already been setup as well as the directory structure for the project.  

The structure of the raw image is the following:
* Height: 1920 pixels
* Width: 1536 pixels
* Image format: 16 bit (unsigned) gray scale, little-endian

Use the mock-up below as a reference for how to implement the GUI of the application. In general you'll need a menu in the top of the application to allow for opening of the image using `File` -> `Open`. This should prompt a file picker where the user can pick the `.raw` file. 

![](https://i.imgur.com/bbvEHVe.png)

### Hints

To configure via the CMake GUI, open CMake and set the `Source Dir` to the base directory of this project. Set the build directory to a folder **outside** of the source directory. 

When configuring via CMake be sure to select the correct generator based on the IDE you plan to use (see image below, your generator may be different):
![](https://i.imgur.com/CvFpWFz.png)

CMake will also ask for the `Qt5_DIR`. You need to set this to `<Qt5InstallDir>/<buildType>/lib/cmake/Qt5`. 

Once you have everything set up correctly, click "Generate". If no error show up, click "Open Project" and you can get started coding. 
 
### Rules
There are a few constraints to your solution:
* `CMAKE_AUTOMOC` must be turned **off**.
* `CMAKE_AUTOUIC` must be turned **off**. 
* Use target specific commands in CMake (i.e. use `target_link_libraries()` to link libraries to you project, not `link_directories()` and `target_include_directories()` not `include_directories()`).

### How you'll be evaluated:
* Diligence/Completeness of code 
    * Can we take your project and run it without having to make changes to the code.
    * How well does it handle edge cases (i.e. what if I try to open a `.png` not a `.raw`).
* Documentation
    * Did you document your code?
    * If so, how thorough is it? 

### Bonus
For "bonus" points, allow the user to have the ability to zoom in and out of the image. 

## Reference Implementation
See the `.gif` below for a reference implementation:

![](https://i.imgur.com/Le5ukLX.gif)

## Troubleshooting
If you have issues with dependencies you can contact [Paul Tsouchlos](mailto:PaulTsouchlos@xstrahl.com). 

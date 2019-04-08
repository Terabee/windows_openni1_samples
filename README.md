# README

The purpose of this README is to give guidelines for developing applications with Terabee 3Dcam 80x60 using the OpenNI 1 framework on Windows. 

For more information about the Terabee 3Dcam 80x60, please click [here](https://www.terabee.com/shop/3d-tof-cameras/terabee-3dcam/).

## System Requirements

* Windows 7 or later
* Visual Studio 2013

## Prepare software development environment

### Install OpenCV 2

In order to build and run samples from Terabee, you will have to install OpenCV.

Install OpenCV 2.4.11 pre-built binaries for Windows (available [here](https://opencv.org/releases.html)). The rest of the guide will assume that OpenCV in installed to C:\opencv.

The visual studio project provided in this repository is designed to work with Visual Studio 2013 (vc12). If you wan to use a newer version of OpenCV, you will have to check that pre-built binaries are compatible with your Visual Studio version and adapt include files, library path and files name accordingly.

### Install Terabee 3D depth camera SDK

* Download the Windows SDK from the Downloads section of Terabee 3Dcam [here](https://www.terabee.com/wp-content/uploads/2019/04/Terabee_3Dcam_SDK_1.5.0.1_Windows.zip).
* Install the SDK by running the file relevant to your system architecture and desired OpenNI version.

## Start developing your application

To get started with your application development, we provide sample codes to help you initiate your development. The following steps provide instructions on how to download and run sample codes. 

### Install Git

* Please download Git-SCM tools [here](https://git-scm.com/) to install Git client for Windows platform.

### Clone sample code
Clone the project using a git-bash console or the Git GUI:

```
git clone https://github.com/terabee/windows_openni1_samples.git Terabee_samples
```

### Build and Run Terabee samples

#### Depth Viewer

This sample will show you how to access camera data and display it into a window. It was created using Visual Studio 2013. If you want to use another version, you will have make sure it is compatible with the installed OpenCV version.

To run the sample, please follow those steps:

* Launch Visual Studio IDE by clicking DepthViewer.vcxproj
* Click on the Run button to build and launch the sample

### Build your own application
Taking as example the sample we provide, you can start to develop your own application. What you need to know to create a new project is:

* After the new project has been created, you need to add OpenNI headers and library path in the project configuration property. That is,

1. Right click the project in Solution Explorer and choose Properties

2. Expand "VC++ Directories", add "C:\Program Files\OpenNI\Include" to "Include Directories" and add "C:\Program Files\OpenNI\Lib64" to "Library Directories"

3. If you are developing a 32-bit application in a 64-bit machine, the paths might modified to "C:\Program Files (x86)\OpenNI\Include" and "C:\Program Files (x86)\OpenNI\Lib"

4. If you are developing a 32-bit application in a native 32-bit machine, the paths might modified to "C:\Program Files\OpenNI\Include" and "C:\Program Files\OpenNI\Lib"

5. Then, expand "Linker" in "Configuration Properties", add "openNI64.lib" to "Input->Additional Dependencies". (Or "openNI.lib" if you are developing a 32-bit application"

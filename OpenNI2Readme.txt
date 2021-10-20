///////////////////////////////////////////////
//
//
// aeroTAP OpenNI2 Driver 
// Last Updated: 2020.7.28
//
// Copyright nextEDGE Technology K.K. All rights reserved.
//
///////////////////////////////////////////////

** Updates **
2020.7.28 v1.8
-Updated filering for depthmap.
2020.7.6 v1.6
-Updated aeroTAP Library DLL, improved depthmap.
2020.4.29 v1.6
-Fixed issue with 320x240 mode FOV values
2020.4.25 v1.5
-Improved performnce ( Frame update rate ).
-Improved -Filter option for Skeleton tracking Midlleware
2020.1.11 v1.4
-Fixed issue with wrong PID value from OpenNI2 driver
2019.12.29 v1.3
-Modified that set ONI_STERAM_PROPERTY_MIRROING = false makes Mirror image
2019.12.23 v1.2
-Modified for License check of nuiTrack SDK
2019.12.16
-Added to License check for nuiTrack SDK
2019.12.2
-Fixed compatibility issue with parameter ONI_STREAM_PROPERTY_MIRRORING
-Added ONI_DEVICE_PROPERTY_IMAGE_REGISTRATION implementation
-Updated aeroTAP SDK
2019.11.7  
-Improved Performance
-Improved Post process quality in aeroTAP SDK
-Added Linux support ( Arm, Aarch64, Ubuntu ) 
2019.9.11  
-Improved Performance
-Improved Pose Process in aeroTAP SDK
- Fixed gray 254 made depth map hole
2019.6.10  
-Improved Performance
-Improved Pose Process in aeroTAP SDK
2019.4.4  
-Improved Performance
-Improved for aeroTAP 3D USB Camera

** How to use **
Device name = aeroTAP
i.e  When using OpenNI sampele code SimpleViewer, use 'aeroTAP' for device name.
SimpleViewer.exe aeroTAP


// Nite2 Sample:
UserView.exe -device aeroTAP

// PCL:
pcl_openni2_viewer.exe aeroTAP


// OPENNI.ini: When using nuiTrack or other OpenNI2 compatible application, you have to place OPENNI.ini and edit the following line.

[Device]

Override="aeroTAP"



Prerequisets:
-------------
- Windows
	/Bin/Win-x64
	/Bin/Win-x32
- Ubuntu
	/Bin/x64-Release
- RaspberryPi2/3
	/Bin/Arm-Release
- Dragonboard
	/Bin/aarch64-Release

NOTE: For Linux, 
  - Copy OpenNI libraries (libOpenNI2.so, libaeroTAP-sdk.so and libaeroTAP.so) to /system/lib (requires root) - or -
  - run `export LD_LIBRARY_PATH=.:$LD_LIBRARY_PATH` before starting the native executeable


// How to use:
-------------
1. Copy files on x86 or x64 foler to OpenNI/Drivers folder. i.e.
   -[Program Folder]   
       - aeroTAP_CAM.dll
       - eSPDI.dll
       - OPENNI.ini
   -OpenNI2/Drivers
       - aeroTAP.dll
       - aeroTAP.ini 

2. Place OPENNI.ini and edit [Device] section to use aeroTAP driver
2. Connect aeroTAP 3D USB camera
3. Run Application


// Hints
Q1. How to get RAW depth map data?   For PCL and RTabmap use
A1. Edit aeroTAP.ini and set value to 0 for Filter parameter.  i.e.  Filter=0

Q2. How to use 2nd connected aeroTAP camera?
A2. Edit aeroTAP.ini and set value to 1 for CamNo parameter.  i.e.  CamNo=1

Q3. How to set Camera Angle?
A3. Edit aeroTAP.ini and set value degree for Angle parameter.  i.e. Angle=15

Q4. Rotate Camera position?
A4. Set camera Rotate 90 degree then edit aeroTAP.ini and set value 1 for Rorate.  i.e. Rotate=1

//Known Issue
--------------
Ubuntu x64 - "VIDIOC STREAMON error 28" error when using aeroTAP camera on USB3.0 
	User USB 2.0 instead

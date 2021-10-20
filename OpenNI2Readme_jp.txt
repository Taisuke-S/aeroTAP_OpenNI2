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


** How to use **
-----------------


�f�o�C�X���� "aeroTAP" �Ƃ��Ďw�肵�܂��B

Device name = aeroTAP

// OpenNI2
��:  OpenNI2 �̃T���v���R�[�h SimpleViewer�ł́A���s�̍ۂɃf�o�C�X�����w�肷�邱�Ƃ��ł��܂��B
SimpleViewer.exe aeroTAP


// Nite2
��:  Nite2 �T���v���R�[�h SimpleViewer�ł́A���s�̍ۂɃf�o�C�X����-device�Ŏw�肷�邱�Ƃ��ł��܂��B
UserView.exe -device aeroTAP

// PCL:
��:  Nite2 �T���v���R�[�h SimpleViewer�ł́A���s�̍ۂɃf�o�C�X�����w�肷�邱�Ƃ��ł��܂��B
pcl_openni2_viewer.exe aeroTAP


// OPENNI.exe
 OPENNI2�݊��A�v���P�[�V���������s����ꍇ�A�f�o�C�X�̎w��́AOPENNI.INI�t�@�C�����������A[Device]�p�����[�^�Ɏw�肵�܂��B�T���v���Ɋ܂܂��OPENNI.INI�t�@�C����OPENNI2.DLL�Ɠ����t�H���_�[�ɏ������Ă��������B
��:
[Device]
Override="aeroTAP"



// �T���v���̗��p���@:
1. �h���C�o�́Ax86�܂���x64�t�H���_�[�ɂ���܂��B�h���C�o�@(aeroTAP.DLL, aeroTAP.ini )�́AOpenNI/Drivers�t�H���_�[�ɃR�s�[���܂��B���̑��A�T�u�t�@�C�� ( aeroTAP_CAM.DLL, eSPDI.DLL, OPENNI.INI)�t�@�C�����A�v���P�[�V�����Ɠ����t�H���_�̃R�s�[���܂��B
��:
   -[Program Folder]   
       - aeroTAP_CAM.dll
       - eSPDI.dll
       - OPENNI.ini
   -OpenNI2/Drivers
       - aeroTAP.dll
       - aeroTAP.ini 

2. OPENNI.ini ��ҏW���āA [Device]�Z�N�V������ aeroTAP �h���C�o��ݒ肵�܂��B
2. aeroTAP 3D USB �J������ڑ����܂��B
3. �T���v���v���O���������s
��: bin, bin.64�t�H���_��OpenNI2�R���p�C���ς݃T���v��������܂��BSimpleViewer.exe�����s�ł��܂��B


// ���̑��q���g
Q1. RAW�[�x�f�[�^���擾����ꍇ?   (PCL �� RTABmap�����s����ꍇ�Ȃ�)
A1. aeroTAP.ini ��ҏW���ARAWData �p�����[�^�̒l�� 0 ��ݒ肵�܂��B��:  Filter=0

Q2. aeroTAP�J������2��ڑ����Ă���ꍇ�ɁA2�Ԗڂ̃J�������g���ꍇ�B
A2. aeroTAP.ini ��ҏW���ACamNo �p�����[�^�̒l�� 1 ��ݒ肵�܂��B��:  CamNo=1

Q3. �J�������ォ�牺�Ɋp�x��t���Đݒu�����ꍇ�̕␳���@
A3. aeroTAP.ini ��ҏW���AAngle �p�����[�^�̒l�Ɋp�x xx ( 0 ���� 45 �̒l )��ݒ肵�܂��B�Ⴆ�΁A15�����������ꍇ�AAngle=15
Q4. �J������90����]���Đݒu����ꍇ
A4. aeroTAP.ini ��ҏW���ARorate �p�����[�^�̒l��1�ɐݒ肵�܂��BOPENNI2����ƁA��]���Ă��𑜓x��VGA�̂܂܂ł��B��: Rotate=1


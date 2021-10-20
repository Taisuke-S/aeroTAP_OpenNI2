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


デバイス名を "aeroTAP" として指定します。

Device name = aeroTAP

// OpenNI2
例:  OpenNI2 のサンプルコード SimpleViewerでは、実行の際にデバイス名を指定することができます。
SimpleViewer.exe aeroTAP


// Nite2
例:  Nite2 サンプルコード SimpleViewerでは、実行の際にデバイス名を-deviceで指定することができます。
UserView.exe -device aeroTAP

// PCL:
例:  Nite2 サンプルコード SimpleViewerでは、実行の際にデバイス名を指定することができます。
pcl_openni2_viewer.exe aeroTAP


// OPENNI.exe
 OPENNI2互換アプリケーションを実行する場合、デバイスの指定は、OPENNI.INIファイルを準備し、[Device]パラメータに指定します。サンプルに含まれるOPENNI.INIファイルをOPENNI2.DLLと同じフォルダーに準備してください。
例:
[Device]
Override="aeroTAP"



// サンプルの利用方法:
1. ドライバは、x86またはx64フォルダーにあります。ドライバ　(aeroTAP.DLL, aeroTAP.ini )は、OpenNI/Driversフォルダーにコピーします。その他、サブファイル ( aeroTAP_CAM.DLL, eSPDI.DLL, OPENNI.INI)ファイルをアプリケーションと同じフォルダのコピーします。
例:
   -[Program Folder]   
       - aeroTAP_CAM.dll
       - eSPDI.dll
       - OPENNI.ini
   -OpenNI2/Drivers
       - aeroTAP.dll
       - aeroTAP.ini 

2. OPENNI.ini を編集して、 [Device]セクションに aeroTAP ドライバを設定します。
2. aeroTAP 3D USB カメラを接続します。
3. サンプルプログラムを実行
例: bin, bin.64フォルダにOpenNI2コンパイル済みサンプルがあります。SimpleViewer.exeを実行できます。


// その他ヒント
Q1. RAW深度データを取得する場合?   (PCL や RTABmapを実行する場合など)
A1. aeroTAP.ini を編集し、RAWData パラメータの値に 0 を設定します。例:  Filter=0

Q2. aeroTAPカメラを2台接続している場合に、2番目のカメラを使う場合。
A2. aeroTAP.ini を編集し、CamNo パラメータの値に 1 を設定します。例:  CamNo=1

Q3. カメラを上から下に角度を付けて設置した場合の補正方法
A3. aeroTAP.ini を編集し、Angle パラメータの値に角度 xx ( 0 から 45 の値 )を設定します。例えば、15°下向けた場合、Angle=15
Q4. カメラを90°回転して設置する場合
A4. aeroTAP.ini を編集し、Rorate パラメータの値を1に設定します。OPENNI2を介すと、回転しても解像度はVGAのままです。例: Rotate=1


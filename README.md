# OpenNI2 for aeroTAP3D

Please refer to main github: http://structure.io/openni

# Purpose
The purpose of this archive is to give users an easy path to porting OpenNI2 to Jetson TX1 (64 bit arm). The binaries can be used as is or the source can be recombiled on the TX1 by just issuing the make command in the parent directory.

# Building
Please refer to Jetson Hacks: http://www.jetsonhacks.com/2014/08/28/building-openni2-structure-sensor/ for specific instructions. These instructions are designed for the Jetson TK1 board. The files in this archive have already been modified as needed for the TX1. You will just need to start with the instructions for building and installing the libfreenect library and following until the end.

# Modifications
This archive include provide OpenNI2 driver for aeroTAP3D camera. The archive includes OpenNI2 driver for aeroTAP for the Arm, 64Bit Arm, Linux, Windows 32Bit and 64bit platform.
This version aeroTAP OpenNI2 driver supports:
- aeroTAP 3D Camera
- aeroTAP 3D G2 Camera
- aeroTAP 3D GS Camera

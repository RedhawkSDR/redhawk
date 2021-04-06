# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description
REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements

### **[Release of REDHAWK 2.2.8](https://github.com/redhawksdr/redhawk/releases/tag/2.2.8) (April 2021)**
The effort in REDHAWK 2.2.8 focused on:

* EOS condition is reported correctly for all connections when an incoming stream receives an EOS flag.
* Rate in header for zero-rate SDDS headers is ignored
* Resolved issue when adding a new stream to an attachable port that would cause a program to segfault.
* Exiting a python sandbox session will now properly terminate a resource's processes started during the session that threw  `initialization` exceptions.


## Copyrights
This work is protected by Copyright. Please refer to the [Copyright File](COPYRIGHT) for updated copyright information.

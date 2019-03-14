# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description
REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements

### **[Release of REDHAWK 2.2.2](https://github.com/redhawksdr/redhawk/releases/tag/2.2.2) (March 2019)**
The effort in REDHAWK 2.2.2 focused on:

* Updating the redhawk.attach() call to not cache domains anymore. Instead, the last connected CORBA ORB is cached and subsequent calls make sure the ORB is still valid.
* Fixing refresh and NPE issues in the REDHAWK Explorer view. Event channels are now properly connected on Domain Manager restarts. ClientMessageReceptor threads no longer grow unbounded.

## Copyrights
This work is protected by Copyright. Please refer to the [Copyright File](COPYRIGHT) for updated copyright information.

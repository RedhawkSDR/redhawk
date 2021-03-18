# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description
REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements

### **[Release of REDHAWK 2.3.0](https://github.com/redhawksdr/redhawk/releases/tag/2.3.0) (March 2021)**
The effort in REDHAWK 2.3.0 focused on:

* Added methods to  C++ ThreadedComponent API, that allow developers to determine if stop was called or if the resource internally reached an finished state.
* Added Python iterator support to limit the number of entries that are returned from a servant's iterator interface.
* Fixed connection rate check for rh.MSDD during device startup when the MSDD radio supports multiple network interfaces.
* rh.MSDD  correctly enables the tuner's output module for successful allocations  The rh.MSDD property `advanced::max_nic_percentage` will now track the total output rate from the radio's network interface against this threshold to disallow allocations that oversubscribe the interface.
* Resolving issue to correctly set the time-of-day in ONEPPS mode.
Added properties `msdd_status::tod_host_delta` (gives the time-of-day offset between the host and the MSDD's TOD module while in ONEPPS mode) and `msdd_status::ntp_running` (shows whether ntp is running on the host while in ONEPPS mode).
* Added JAVA Bulk IO Stream API support to bulkio.jar
* EOS condition is reported correctly for all connections when an incoming stream receives an EOS flag.
* An application's external property maps to the correct component when the component's name is a substring of another component.
* Fixed issue where timecodes  values were not properly adjusted during filter operations.
* rh.fastfilter adds a bybass mode property. When bypass mode is enabled, any input stream data bypasses all filter operations and passed directly to any output connections.
* rh.psd component properly handles values above 2.4 GHz for SRI keywords CHAN_RF and COL_RF.
* Resolved issue when adding a new stream to an attachable port that would cause a program to segfault.
* Exiting a python sandbox session will now properly terminate a resource's processes started during the session that threw  `initialization` exceptions.

### New Features
The following features were added in REDHAWK 2.3.0:


#### Core Framework Features

* Added Bulkio Stream support in Java

#### Documentation Features

* Added support for Java Bulk IO stream API


## Copyrights
This work is protected by Copyright. Please refer to the [Copyright File](COPYRIGHT) for updated copyright information.

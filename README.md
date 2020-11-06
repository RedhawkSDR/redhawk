# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description
REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements

### **[Release of REDHAWK 2.2.7](https://github.com/redhawksdr/redhawk/releases/tag/2.2.7) (November 2020)**
The effort in REDHAWK 2.2.7 focused on:

* Plugin infrastructure created for GPP to track custom system metrics
* Queue flush reported on all affected streams in the incoming queue
* When reading Bulk IO streams, allow the consume size to be greater than the read size (equivalent to read+skip)
* Resolving an issue with intermittent failures in `omniEvents` when writing to `syslog` running on CentOS 7.
* Components generate from command line with applications like createBinaryComponent generate the correct header on the SCD and PRF files
* Java message ports are consistent with Python and C++ message ports. When the message fails, it tries again in subsequent messages
* Python helper pythonComplexListToBulkioComplex converts numpy.float to Python native float


## Copyrights
This work is protected by Copyright. Please refer to the [Copyright File](COPYRIGHT) for updated copyright information.

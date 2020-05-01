# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description
REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements

### **[Release of REDHAWK 2.2.6](https://github.com/redhawksdr/redhawk/releases/tag/2.2.6) (May 2020)**
The effort in REDHAWK 2.2.6 focused on:

* Resolving an exception that occurred when calling the`AllocationManager`'s `listAllocations` method with no arguments.
* Adding developer documentation to explain how to enable JacORB for Java components.
* Fixing typos in component sample code comments.
* Implementing fixes to properly initialize the persona device logger.
* Changing `_bindir` to `_libdir` in the generated `.spec` file for generated C++ components.
* Adding a return code to `cleanomni` to indicate when one of the steps failed. In the event of an error, `cleanomni` still attempts each step of the cleanup process before exiting with a non-zero status.
* Modifying Device Manager behavior to no longer hang on shutdown when non-DCD devices/services remain registered.
* Resolving an issue with the `DeviceManager` exiting during device and service registrations due to unhandled exceptions.
* Updating the behavior of the GPP's memory threshold monitoring to more accurately reflect real world usage. The available memory is calculated using `MemAvailable`, which provides the best estimate per the Linux kernel and does not include swap memory. The default value for the free memory threshold is now the lesser of 20% of total memory, or 6GB.
* Resolving a dead lock issue that occurred during the `omniEvents` check point operation.
* Preventing the file system from crashing when files are removed while `list()` is invoked.
* Resolving handling of process lifecycle by the GPP when process identifiers are reused on a busy system. Adding safeguard against the GPP terminating processes when the process identifier and process group identifier are not the same.


## Copyrights
This work is protected by Copyright. Please refer to the [Copyright File](COPYRIGHT) for updated copyright information.

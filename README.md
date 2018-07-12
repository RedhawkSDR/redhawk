# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description
REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements
### **[Release of REDHAWK 2.1.3](https://github.com/redhawksdr/redhawk/releases/tag/2.1.3) (July 2018)**:

The effort in REDHAWK 2.1.3 focused on:

* Adding snapshot capability of network data and performing SDDS packet analysis on the captured data.
* Adding scripts and configuration files that allow REDHAWK core services to run as system services.  In addition to these services, integrators can define REDHAWK waveforms that are deployed during the system boot process.
* Extending the tool, `rh_net_diag`, to provide read/write/execute permissions checks on directories important for running a REDHAWK system.
* Changing the default logging directory for omniEvents service to reside in `/var/log/omniEvents`.
* Changing FrontEnd Interfaces (FEI) property definitions: 
 * For devices, the `FRONTEND::tuner_allocation` and `FRONTEND::listener_allocation` allocation properties are now writeonly instead of readwrite. Because the properties are now created as writeonly, they can no longer be queried. This change was made to prevent confusion with the actual state of the FrontEnd device, which is reported by the `FRONTEND::tuner_status property`. Existing Core Asset FEI devices have been updated with this change. New FrontEnd devices created with the IDE will automatically have this change.
* Adding functionality to the IDE so when users edit a property's name, the IDE automatically supplies an appropriate ID for the property based on REDHAWK's naming convention.
* Adding documentation to the REDHAWK Manual regarding naming elements in structures such that element names can be reused across different structures.
* Updating the `rh.VITA49` REDHAWK shared library to include support for VITA 49.2. Initial release adheres to the draft specification, revision 00.51 dated 5 Dec 2016, which was available during development.
* Adding functionality in the IDE to install the diagram layout when installing a SAD/DCD file (either by drag-drop or via its RPM `.spec` file). At runtime, the IDE checks for the diagram layout and if present, preserves the developer's layout.
* Adding an option to enable the Domain Manager's logging level to be dynamically changed.
* Adding a new packed bit data port type and data format for BulkIO:
  * Port API for component developers is fully implemented in C++, Python, and Java.
  * Plotting, monitoring, and interacting with data are supported in the IDE and Python Sandbox.
  * For C++ and Python, a new `bitbuffer` class provides high-level access to packed bit data.
  * In Python, all BulkIO ports now support a stream-based API that is consistent with C++.
* Adding CF base class support and IDE tooling to allow users to create, implement, and test a FrontEnd scanner device.
* Adding extensible hierarchical name structure support for loggers.
* Correcting behavior for structures that have a default value that is mixed simple values and sequences; if the sequence is empty, it is not treated as nil.
* Adding support for working with multi-out ports.
* Adding Allocation Manager functionality in the IDE:  
 * Viewing current allocations and allocation details for each allocation is supported.
 * Searching for devices used for an allocation and Device Managers referenced by an allocation is supported.
 * Allocations can be deallocated.
* Adding context-sensitive property views in the REDHAWK IDE for the following:
  * Waveform and node properties are displayed when selecting the respective runtime editor.  Runtime connection details are also displayed (read-only) when selecting a connection in a diagram editor.
  * `SoftwareAssembly` and `DeviceConfiguration` properties are displayed when selecting the respective design-time editor. Design-time connection properties are displayed when selecting a connection in a diagram editor.
* Providing better context-specific icons throughout the IDE, and updating images and text in the REDHAWK Manual to reflect these new icons.
* Providing new functionality for interacting with event channels and message event ports.
* Adding Connection Manager functionality in the IDE:
 * Viewing current connections and connection details for each connection is supported.
 * Searching for the source or target of a connection is supported.
 * Connections can be disconnected.
* Fixing an issue so when waveforms containing references to mistyped properties are launched, the IDE displays all the properties including the property that had a mis-matched override in the SAD file.
* Adding validation for mistyped property refs.
* Fixing the DomainManager's improperly defined scoped locks.
* Implementing several C++ fixes to allow REDHAWK to compile on newer compilers.
* Correcting default property kinds in the DTD and XSD so they are no longer out of sync with the behavior of the Core Framework and the ICD.
* Adding new behavior to the C++ input stream API: It is now possible to "peek" into data sets that have reached EOS by setting consume to 0 when using read or tryread.
* Adding support to custom IDL and FEI control ports so they now accept a connection id argument to specify the connection to use and throw exceptions if the port call is exercised and no connection exists or a connection is specified that does not exist.
* Fixing an issue so when unhandled exceptions occur in Python and Java components, the components terminate rather than remain in a defunct state. If termination was not requested, the GPP now sends a message to the IDM channel when a component exits with a non-zero status.
* Updating the FEI specification to require a device to only partially support a requested signal range rather than the whole signal to return a valid request. The `validateRequest` function in the `frontendInterfaces` support package checks that a partial overlap of the requested band succeeds rather than requiring full coverage of the requested range.
* Patching omniORBpy to prevent possible segfaults in multithreaded code.
* Updating the IDE on CentOS 7 to use the latest available Eclipse tooling, Eclipse Photon.
* Correcting behavior so readonly property kind properties for devices and services can now be modified during deployment using Device Configuration Descriptor (dcd.xml) file.
* Correcting a bad XML file in the SDRROOT that caused loading of the SDRROOT to stop and report an error.
* Updating `rh.VITA49` to adhere to the approved version of V49.2 Standard (August 2017).
* Adding an option for `MessageSupplierPort` to send messages to a specific connection.
* Deprecating REDHAWK Enterprise Integration and removing all references to it within the documentation.
* Providing the ability to generate configuration files for waveforms and nodes for use by the REDHAWK admin service.
* Changing the `redhawk` user's home directory. When installing REDHAWK, the home directory is now `/var/redhawk`. When upgrading, the existing `redhawk` user home directory is updated to `/var/redhawk` if it is currently set to `/home/redhawk`.
* Refactoring IO redirection to use epoll system call to handle redirection of component output to a single file and direct IO redirection when configured for one output file per component process.
* Correcting behavior so when a component has a struct property with an element that is a complex sequence, the value can be overloaded correctly on a waveform.

## Copyrights
This work is protected by Copyright. Please refer to the [Copyright File](COPYRIGHT) for updated copyright information.

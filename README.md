# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description
REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements
**[Release of REDHAWK 2.1.0](https://github.com/redhawksdr/redhawk/releases/tag/2.1.0) (April 2017)** - The effort in REDHAWK 2.1.0 focused on:
* Adding support for Components to be deployed on a specific GPP, and conversely allowing the GPP to restrict deployments through a matching set of id/value pairs. These id/value pairs are defined in the Software Assembly Descriptor and Device Configuration Definition files respectively. Users may refer to this feature as the "special snowflake" deployment Property.
* Shared address space Components: Significant enhancement of Component model and BULKIO to support high performance I/O. Preliminary developer documentation for the REDHAWK 2.1.0 Beta Release is available at https://github.com/RedhawkSDR/core-framework/tree/develop-2.1/docs/shared-address. This feature will be under extensive evaluation during the 2.1.x beta release series and is expected to provide the ground work for several new major enhancements to REDHAWK.
* Adding support for a new type of Property, "utctime", extending the list that includes types such as "short" or "string". This timestamp Property is used in Property change events and can be queried from Components/Devices with the id QUERY_TIMESTAMP, which is useful when synchronizing the state of the system. The new type of Property can be used by Component/Device developers as an additional type of Property.
* Adding cacheDirectory and workingDirectory Properties to the GPP. These properties provide the deployer with control over where Components are stored (cacheDirectory) and the directory from which Components are executed (workingDirectory).
* Redesigning the IDE's Event Viewer to improve the ability to monitor event channels.
* Ending support of Command-line interactive mode (-i) on Components, Services, and Devices. Terminal prompt interactions should be through the Python Sandbox.
* Improving Python tooling to help manage REDHAWK systems. For example, these improvements include eventChannelManager, allocationManager, and connectionManager helpers as well as simpler event monitoring.
* Adding functionality to allow Components that have a usesdevice dependency to now be launched on the same host (i.e., Device Manager/Node) as the Device satisfying the usesdevice requirement. This functionality is provided through an extension of the componentplacement hostcollocation.
* Improving recovery of a REDHAWK Domain after a catastrophic failure. The Device Manager reboots all associated Devices/Services when it detects a reset Domain Manager after a catastrophic failure in the Domain Manager. This reboot only happens if (1) persistence is enabled and (2) the name service log, event service log, and persistence database are emptied.
* Adding new concurrent logging appender for C++ Components to improve readability of logging messages when multiple processes are writing to the same log file.
* Improving the New Project Wizard to warn users if the project location selected already contains files that will become part of the project. Increase user awareness of files that may be moved, deleted, or packaged with a project.
* Updating the IDE to use the latest available Eclipse tooling, Eclipse Neon. For more information about Eclipse Neon, refer to http://www.eclipse.org/neon/noteworthy.
* Documenting a publisher/subscriber pattern when accessing an EventChannel from the Domain.
* Documenting available affinity processing directives when deploying Devices, Services, and Components.
* Adding support for the REDHAWK Core Framework, IDE, assets, and new REDHAWK projects to now compile against and run on Java 8.
* Extending DeviceManager to call configure() on Services at the time they register. This enables users to implement custom Property handling if so desired.
* Resolving issue when activating local servants for MessageConsumerPort and MessageSupplierPort Java classes.
* Improving Python Sandbox tooling for new Domain features and resources. Specifically, extended DataSource to provide access to all the available SRI and the data timestamp.
* Adding reservation schema graph in the documentation to enhance the text describing capacity allocation reservation for the GPP.
* Improving documentation of Signal Related Information (SRI).
* Updating Contributor License Agreement (CLA).
* Addressing numerous bug fixes.

**[Release of REDHAWK 2.0.5](https://github.com/redhawksdr/redhawk/releases/tag/2.0.5) (February 24, 2017)** - The effort in REDHAWK 2.0.5 focused on:
* Maintaining the correct time stamp when pushing data from the Sandbox DataSource.
* Improving a Component's response to messages irrespective of whether or not the Component is started or stopped.
* Improving FileSink support for framed data and timecode with BLUE file output.
* Improving the handling of missing event message fields in C++ and Python.
* Ensuring external Port names are recognized.
* Addressing numerous bug fixes.

## Copyrights
This work is protected by Copyright. Please refer to the [Copyright File](COPYRIGHT) for updated copyright information.

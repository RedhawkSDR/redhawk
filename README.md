# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description
REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements
### **[Release of REDHAWK 2.1.1](https://github.com/redhawksdr/redhawk/releases/tag/2.1.1) (August 2017)**:

### Core REDHAWK Features and APIs
 * Shared address space Components: Significant enhancement of Component model and BulkIO to support high performance I/O. Preliminary developer documentation for the REDHAWK 2.1.0 beta release is available [here](https://github.com/RedhawkSDR/core-framework/tree/develop-2.1/docs/shared-address).
    * This feature will be under extensive evaluation during the 2.1.x beta release series and is expected to provide the ground work for several new major enhancements to REDHAWK.
* Adding the API for a new type of tuner, a scanning Device.
* Adding support for a new type of Property, utctime, extending the list that includes types such as short or string. This timestamp Property is used in Property change events and can be queried from Components/Devices with the id `QUERY_TIMESTAMP`, which is useful when synchronizing the state of the system. The new type of Property can be used by Component/Device developers as an additional type of Property.
* Adding functionality for capacity to be reserved for an entire host collocation on the SAD file. The reservation is a capacity floor for the Components in the host collocation, where the amount of capacity utilized by the aggregate set of Components is this reservation or actual, whichever is higher. This reservation is allocated against the target GPP running this Application, allowing the GPP to verify that the request can be satisfied, reducing the likelihood of over-subscription.
* Adding functionality to allow Components that have a usesdevice dependency to now be launched on the same host (Device Manager/Node) as the Device satisfying the usesdevice requirement. This functionality is provided through an extension of the componentplacement hostcollocation.
* Extending DeviceManager to call `configure()` on Services at the time they register. This enables users to implement custom Property handling if so desired.

### REDHAWK Systems
* Changing the default logging directory for omniEvents service to reside in `/var/log/omniEvents`.
* Improving `nodeBooter` so it does not deploy if `--user` or `--group` are set while `--daemon` is not, and if the command-line arguments to `nodeBooter` are malformed, deployment fails.
* Adding support for the state of the Connection Manager and Event Channel Manager to be restored when persistence is enabled.

### Project Code Generation
* Fixing code generators for Port generation of C++ Components to correctly handle data structures returned from methods.
* Providing functionality to add custom headers to project files when generating code.
*  Providing Generate Waveform and Generate Node buttons in the IDE editors to initiate file generation. This ensures that Waveform and Node project spec files are created or modified only when requested by the user.

### Python Tooling and Sandbox
* Adding snapshot capability of network data and performing SDDS packet analysis on the captured data.
* Improving Python tooling to help manage REDHAWK systems. For example, these improvements include eventChannelManager, allocationManager, and connectionManager helpers as well as simpler event monitoring.
* Improving Python Sandbox tooling for new Domain features and resources. Specifically, extended DataSource to provide access to all the available SRI and the data timestamp.
* Adding an option to enable the Domain Manager’s logging level to be dynamically changed.
* Correcting issue in the Python Sandbox so now when the BulkIO queue is full, the Python Sandbox no longer locks up when trying to release stopped Components.

### GPP
* Improving flexibility to ignore GPP threshold checks when determining if the GPP should go into a BUSY state.

### IDE
* Updating the IDE to use the latest available Eclipse tooling, Eclipse Oxygen.
* Providing the [TM Terminal](https://marketplace.eclipse.org/content/tm-terminal) in the IDE, a full-featured terminal emulator that provides full ANSI cursor control, readline, and coloring.
* Adding the Components tab to the Waveform editor in the IDE to allow editing of Component instantiation details, including logging configuration. This information will be used to resolve the `LOGGING_CONFIG_URI `parameter during Component deployment.
* Showing IDL details when Ports are selected in the REDHAWK Explorer view.
* Providing validation of Property references in SAD and DCD files and flagging invalid Property references as errors.
* Adding the ability to terminate services in the Sandbox via the hover pad or the delete key and making the terminate icon more distinct throughout the IDE.
* Providing an option in the IDE to perform a FrontEnd Device allocation in the background to aid developers who are debugging their FrontEnd Devices.
* Improving the IDE’s Domain refresh logic to prevent the IDE from consuming excessive numbers of threads in some scenarios.
* Correcting the parsing of some numeric literals in Octave M files.
* Fixing links in the IDE’s help contents so REDHAWK help now displays correctly when links within the help are selected.

### REDHAWK Enterprise Integration
* Updating REDHAWK Java Driver and REDHAWK REST to make it easier for users to access External Properties in Waveforms.
* Adding implementations of ConnectionManager, AllocationManager interfaces to REDHAWK Driver. Adding utility methods for programatically setting the log level of Domain, Application, Device, and Component Resources.
* Adding REST access to Event Channel Manager functionality.

### Documentation
* Adding documentation for developing a logging configuration plug-in that will be used to resolve `LOGGING_CONFIG_URI` parameter during deployment of Devices, Services and Components.
* Renaming the Generating Code section to Generating Code for Components and explaining the code generation process and what occurs in the IDE when the code is generated.
* Revising the BulkIO High-speed data code example in User Manual.


### **[Release of REDHAWK 2.0.6](https://github.com/redhawksdr/redhawk/releases/tag/2.0.6) (July 2017)**:
* Initial FOSS Release of REDHAWK Enterprise Integration Assets, which provide the ability to interact with REDHAWK in a JRE environment.  The REDHAWK Enterprise Integration Assets include:
  * REDHAWK Driver: Provides simplified access to REDHAWK via standard Java interfaces. This Asset shields all interaction with the underlying REDHAWK Components and provides a simplified API for Java developers interacting with a REDHAWK Domain. The REDHAWK Driver can be leveraged as a standalone Java Archive (JAR) file.
  * REDHAWK OSGi Connector: Implements OSGi’s Managed Service Factory interface to allow users to register pre-configured instances of REDHAWK connections into a Karaf container.
  * REDHAWK REST: Provides a REST Service to command and control a REDHAWK instance.
  * REDHAWK WebSocket: Provides an HTML5-compliant WebSocket implementation that enables the ability to stream data from any REDHAWK BulkIO-enabled Port or Event Channel.
  * Camel REDHAWK: Provides a Camel Component for interacting with a REDHAWK Domain. This Component can be connected with other Apache Camel Components as a data flow solution.

  For more information about the REDHAWK Enterprise Integration Assets, refer to the REDHAWK  Enterprise Integration User Guide.

* Providing diagnostic messages for log4py configuration files that contain errors and adding support to allow line continuation characters in the log configuration files.
* Improving the IDE's Domain refresh logic to prevent the IDE from consuming excessive numbers of threads in some scenarios.
* Documenting a publisher/subscriber pattern when accessing an EventChannel from the Domain.
* Modifying Burst IO implementation so that BurstIO output Ports will only override the BurstSRI mode flag in pushBurst if given std::complex sample data.
* Ensuring the creation of and appropriate permissions are on the services directory in SDRROOT.
* Fixing code generators for Port generation of C++ Components to correctly handle data structures returned from methods.
* Resolving issue when activating local servants for MessageConsumerPort and MessageSupplierPort Java classes.
* Resolving issue when ossie.utils.log4py.config is imported after ossie.utils.sb. Fixed by CCB-263 (Formatting issues in -logcfgfile causes python devices to crash) and added unit test to address issue when ossie.utils.log4py.config is imported after ossie.utils.sb.
* Improving documentation of Signal Related Information (SRI).
* Supporting the default version of Octave available in CentOS 7 (3.8.2).
* Correcting the parsing of some numeric literals in Octave M files.
* Resolving issue with the GPP segfaulting when a Component's soft package dependency does not have proper file access privileges.
* Resolving issue with getStreamDefinition returning a pointer to memory that could be reclaimed during processing, which would invalidate any access through that pointer.  The caller now receives a pointer to a copy of a Stream Definition.
* Correctly computing deployment-specific capacities that manage hardware resource requirements in cases where the Component is part of a host collocation deployment.
* Updating Contributor License Agreement (CLA).
* Revising the BulkIO High-speed data code example in User Manual.
* Updating the Python package to create instances of the same Application for multiple processes or threads without conflicts.
* Updating the Python Sandbox to make and break connections from multiple threads without conflicts.

## Copyrights
This work is protected by Copyright. Please refer to the [Copyright File](COPYRIGHT) for updated copyright information.

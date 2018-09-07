# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description
REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements

### **[Release of REDHAWK 2.2.0](https://github.com/redhawksdr/redhawk/releases/tag/2.2.0) (September 2018)**
The REDHAWK 2.2.0 release is a culmination of all the 2.1.x beta releases into the next Long Term Supported (LTS) product release of REDHAWK. In summary, REDHAWK 2.2.0 focused on:

* Adding support for Components to be deployed on a specific GPP, and conversely allowing the GPP to restrict deployments through a matching set of id/value pairs. These id/value pairs are defined in the Software Assembly Descriptor and Device Configuration Definition files respectively. Users may refer to this feature as the "special snowflake" deployment Property.
* Adding the API for a new type of tuner, a scanning Device.
* Shared address space Components: Significant enhancement of Component model and BulkIO to support high performance I/O.  Developer documentation  is available at https://github.com/RedhawkSDR/core-framework/tree/develop-2.2/docs/shared-address.
* Adding support for a new type of Property, utctime, extending the list that includes types such as short or string. This timestamp Property is used in PropertyChangeEvents and can be queried from Components/Devices with the id QUERY_TIMESTAMP, which is useful when synchronizing the state of the system. utctime can be used by Component/Device developers as an additional type of Property.
* Adding cacheDirectory and workingDirectory Properties to the GPP. These properties provide the deployer with control over where Components are stored (cacheDirectory) and the directory from which Components are executed (workingDirectory).
* Redesigning the IDE's Event Viewer to improve the ability to monitor event channels.
* Adding functionality for capacity to be reserved for an entire host collocation on the SAD file. The reservation is a capacity floor for the Components in the host collocation, where the amount of capacity utilized by the aggregate set of Components is this reservation or actual, whichever is higher. This reservation is allocated against the target GPP running this Application, allowing the GPP to verify that the request can be satisfied, reducing the likelihood of over-subscription.
* Waveform Metrics support: Application objects now contain a "metrics" function that returns GPP usage metrics for individual Components as well as overall for the Application. Metrics are viewable in the Properties view of the IDE.
* Adding support for DCD files to have a startorder attribute, which functions similarly to the SAD file's startorder. On startup, "start" is automatically called on Devices and Services (when possible), and on shutdown, reverse-order "stop" is called. The IDE's tooling for DCD files has been updated to display and edit startorder.
* Adding snapshot capability of network data and performing SDDS packet analysis on the captured data.
* Ending support of Command-line interactive mode (-i) on Components, Services, and Devices. Terminal prompt interactions should be through the Python Sandbox.
* Improving Python tooling to help manage REDHAWK systems. For example, these improvements include more intuitive event monitoring as well as new EventChannelManager, AllocationManager, and ConnectionManager helpers.
* Adding functionality to allow Components that have a usesdevice dependency to now be launched on the same host (Device Manager/Node) as the Device satisfying the usesdevice requirement. This functionality is provided through an extension of the componentplacement hostcollocation.
* Improving recovery of a REDHAWK Domain after a catastrophic failure. The Device Manager reboots all associated Devices/Services when it detects a reset Domain Manager after a catastrophic failure in the Domain Manager. This reboot only happens if (1) persistence is enabled and (2) the name service log, event service log, and persistence database are emptied.
* Adding functionality within the code generators so they create C++, Java, or Python constants for enumerated values defined in the PRF.
* Adding support for debugger options in the Python sandbox for C++ (Valgrind or gdb), Python (pdb), or Java (jdb) Components, Services, or Devices.
* Adding scripts and configuration files that allow REDHAWK core services to run as system services.  In addition to these services, integrators can define REDHAWK waveforms that are deployed during the system boot process.
* Adding the Components tab to the Waveform editor in the IDE to allow editing of Component instantiation details, including logging configuration. This information will be used to resolve the LOGGING_CONFIG_URI parameter during Component deployment.
* Improving the New Project Wizard to warn users if the project location selected already contains files that will become part of the project. Increase user awareness of files that may be moved, deleted, or packaged with a project.
* Updating the IDE to use the latest available Eclipse tooling, Eclipse Neon. For more information about Eclipse Neon, refer to http://www.eclipse.org/neon/noteworthy.
* Adding a Libraries chapter in the REDHAWK Manual to explain how to use shared libraries.
* Documenting available affinity processing directives when deploying Devices, Services, and Components.
* Extending the tool, `rh_net_diag`, to provide read/write/execute permissions checks on directories important for running a REDHAWK system.
* Creating a new MSDD device released with bug fixes and enhancements and regenerated for REDHAWK 2.1.
* Changing the default logging directory for omniEvents service to reside in `/var/log/omniEvents`.
* Adding support for the REDHAWK Core Framework, IDE, assets, and new REDHAWK projects to now compile against and run on Java 8.
* Improving nodeBooter so it does not deploy if --user or --group are set while --daemon is not, and if the command-line arguments to nodeBooter are malformed, deployment fails.
* Changing FrontEnd Interfaces (FEI) property definitions: 
 * For devices, the `FRONTEND::tuner_allocation` and `FRONTEND::listener_allocation` allocation properties are now writeonly instead of readwrite. Because the properties are now created as writeonly, they can no longer be queried. This change was made to prevent confusion with the actual state of the FrontEnd device, which is reported by the `FRONTEND::tuner_status property`. Existing Core Asset FEI devices have been updated with this change. New FrontEnd devices created with the IDE will automatically have this change.
* Improving the user experience when locating and connecting to existing REDHAWK Domains.
* Providing users with the option to copy Properties from other projects in their workspace or choose from pre-defined REDHAWK Properties when developing a Component or Device.
* Displaying a REDHAWK editor when double-clicking on SCD XML files.
* Showing IDL details when Ports are selected in the REDHAWK Explorer view.
* Adding a notification that is now displayed after exporting projects to the Target SDR.
* Providing better support for adding and editing Services in a DCD file.
* Adding a Connection Callbacks section to the REDHAWK Manual.
* Extending DeviceManager to call configure() on Services at the time they register.  This enables users to implement custom Property handling if so desired.
* Providing functionality to add custom headers to project files when generating code.
* Removing some obsolete options from the Core Framework and BulkIO configure scripts.
* Adding support for the state of the Connection Manager and Event Channel Manager to be restored when persistence is enabled.
* Updating the IDE to use the latest available Eclipse tooling, Eclipse Oxygen.
* Improving Python Sandbox tooling for new Domain features and resources. Specifically, extended DataSource to provide access to all the available SRI and the data timestamp.
* Adding reservation schema graph in the documentation to enhance the text describing capacity allocation reservation for the GPP.
* Adding functionality to the IDE so when users edit a property's name, the IDE automatically supplies an appropriate ID for the property based on REDHAWK's naming convention.
* Providing validation of Property references in SAD and DCD files and flagging invalid Property references as errors.
* Adding the ability to terminate services in the Sandbox via the hover pad or the delete key and making the terminate icon more distinct throughout the IDE.
* Adding the stop timeout control to the Application. Options, like the stop timeout, can be configured when designing Waveforms in the IDE.
* Adding functionality in the IDE to install the diagram layout when installing a SAD/DCD file (either by drag-drop or via its RPM `.spec` file). At runtime, the IDE checks for the diagram layout and if present, preserves the developer's layout.
* Adding an option to enable the Domain Manager's logging level to be dynamically changed.
* Adding a new packed bit data port type and data format for BulkIO:
  * Port API for component developers is fully implemented in C++, Python, and Java.
  * Plotting, monitoring, and interacting with data are supported in the IDE and Python Sandbox.
  * For C++ and Python, a new `bitbuffer` class provides high-level access to packed bit data.
  * In Python, all BulkIO ports now support a stream-based API that is consistent with C++.
* Correcting issue in the Python Sandbox so now when the BulkIO queue is full, the Python Sandbox no longer locks up when trying to release stopped Components.
* Providing Generate Waveform and Generate Node buttons in the IDE editors to initiate file generation. This ensures that Waveform and Node project spec files are created or modified only when requested by the user.
* Adjusting the default tuner type for the Python Sandbox tuner allocation. It is now RX_DIGITIZER rather than DDC, matching the default tuner for a generated FEI Device.
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
* Adding validation for mistyped property refs.
* Adding support to custom IDL and FEI control ports so they now accept a connection id argument to specify the connection to use and throw exceptions if the port call is exercised and no connection exists or a connection is specified that does not exist. 
**Caution: This functionality was added to all FEI ports, including the RFInfo port.  As a result, if an RFInfo port is configured as a uses port and there are _no connections_, an exception will occur and must be caught to prevent a disruption to the operation of the device or component.  This behavior will be corrected in a future release.**
* Fixing an issue so when unhandled exceptions occur in Python and Java components, the components terminate rather than remain in a defunct state. If termination was not requested, the GPP now sends a message to the IDM channel when a component exits with a non-zero status.
* Updating the FEI specification to require a device to only partially support a requested signal range rather than the whole signal to return a valid request. The `validateRequest` function in the `frontendInterfaces` support package checks that a partial overlap of the requested band succeeds rather than requiring full coverage of the requested range.
* Updating the IDE on CentOS 7 to use the latest available Eclipse tooling, Eclipse Photon.
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

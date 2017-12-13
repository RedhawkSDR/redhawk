# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description
REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements
### **[Release of REDHAWK 2.1.2](https://github.com/redhawksdr/redhawk/releases/tag/2.1.2) (December 2017)**:

### Core REDHAWK Features and APIs
* Shared address space Components: Significant enhancement of Component model and BULKIO to support high performance I/O. Preliminary developer documentation for the REDHAWK 2.1.1 Beta Release is available at <a href="https://github.com/RedhawkSDR/core-framework/tree/2.1.2/docs/shared-address">https://github.com/RedhawkSDR/core-framework/tree/2.1.2/docs/shared-address</a>. This feature will be under extensive evaluation during the 2.1.x beta release series and is expected to provide the ground work for several new major enhancements to REDHAWK.
* Implementing a new zero-copy IPC mechanism for BulkIO that uses shared memory to transfer data between two processes on the same host. This is a follow-on enhancement to the shared address space Components feature.
Preliminary developer documentation for the REDHAWK 2.1.0 beta release is available at <a href="https://github.com/RedhawkSDR/core-framework/tree/2.1.2/docs/shared-memory/shared-memory-ipc.md">https://github.com/RedhawkSDR/core-framework/tree/2.1.2/docs/shared-memory/shared-memory-ipc.md</a>.
* FrontEnd Interfaces (FEI) Property definition change: For Devices, the FRONTEND::tuner_allocation and FRONTEND::listener_allocation allocation properties are now writeonly instead of readwrite. Because the properties are now created as writeonly, they can no longer be queried. This change was made to prevent confusion with the actual state of the FrontEnd Device, which is reported by the FRONTEND::tuner_status property. Existing Core Asset FEI Devices have been updated with this change. New FrontEnd Devices created with the IDE will automatically have this change.
 * Adding support for a new type of Property, utctime, extending the list that includes types such as short or string. This timestamp Property is used in PropertyChangeEvents and can be queried from Components/Devices with the id QUERY_TIMESTAMP, which is useful when synchronizing the state of the system. utctime can be used by Component/Device developers as an additional type of Property.
* Adding functionality for capacity to be reserved for an entire host collocation on the SAD file. The reservation is a capacity floor for the Components in the host collocation, where the amount of capacity utilized by the aggregate set of Components is this reservation or actual, whichever is higher. This reservation is allocated against the target GPP running this Application, allowing the GPP to verify that the request can be satisfied, reducing the likelihood of over-subscription.
* Adding support for DCD files to have a startorder attribute, which functions similarly to the SAD file's startorder. On startup, "start" is automatically called on Devices and Services (when possible), and on shutdown, reverse-order "stop" is called. The IDE's tooling for DCD files has been updated to display and edit startorder.
* Adding support for the DeviceManager to resolve run time environment settings when deploying Devices and Services that have soft package dependencies.
* Resolving issue so that during Application release, calls to the Application object no longer result in misleading errors.
* Adding functionality within the code generators so they create C++, Java, or Python constants for enumerated values defined in the PRF.
* Improving flexibility to ignore GPP threshold checks when determining if the GPP should go into a BUSY state.
* Removing some obsolete options from the Core Framework and BulkIO configure scripts.
* Resolving issue where processes with spaces in the names would cause the GPP to terminate.
* Resolving issue to allow for slow startup conditions of OmniNames service before starting OmniEvents service.
* Adding the stop timeout control to the Application. Options, like the stop timeout, can be configured when designing Waveforms in the IDE.
* Resolving issue with incorrect exception being thrown during allocateCapacity.
* Resolving issue when shutting down orb from Python resources.
* Providing a warning in the logs if a message is too large.
* Resolving issue with the code generators so they can be run on systems with FIPS enabled.
* Resolving issue so generated C++ FEI Devices do not leak memory when deallocating listeners. Existing Devices must be regenerated and recompiled to apply this fix.
* Resolving a memory leak in FrontendTunerDevice::create(). Existing Devices must be recompiled to apply this fix.
* Resolving issue so the function returnRFInfoPkt transforms all fields between types frontend::RFInfoPkt and FRONTEND::RFInfoPkt.
* Adjusting the default tuner type for the Python Sandbox tuner allocation. It is now RX_DIGITIZER rather than DDC, matching the default tuner for a generated FEI Device.
* Preventing sb.DataSink from adding an empty timestamp when it receives EOS in an empty packet.

### REDHAWK Systems
* Adding scripts and configuration files that allow REDHAWK core services to run as system services. In addition to these services, integrators can define REDHAWK Waveforms that are deployed during the system boot process.

### Python Tooling and Sandbox
* Adding snapshot capability of network data and performing SDDS packet analysis on the captured data.
* Improving Python tooling to help manage REDHAWK systems. For example, these improvements include more intuitive event monitoring as well as new EventChannelManager, AllocationManager, and ConnectionManager helpers.
* Adding support for debugger options in the Python sandbox for C++ (Valgrind or gdb), Python (pdb), or Java (jdb) Components, Services, or Devices.
* Improving Python Sandbox tooling for new Domain features and resources. Specifically, extended DataSource to provide access to all the available SRI and the data timestamp.
* Adding an option to enable the Domain Manager's logging level to be dynamically changed.

### GPP
* Waveform Metrics support: Application objects now contain a "metrics" function that returns GPP usage metrics for individual Components as well as overall for the Application. Metrics are viewable in the Properties view of the IDE. Waveform metrics can now be accessed in the REDHAWK Driver Java and REST APIs.

### IDE
* Adding the Components tab to the Waveform editor in the IDE to allow editing of Component instantiation details, including logging configuration. This information will be used to resolve the `LOGGING_CONFIG_URI` parameter during Component deployment.
* Improving the user experience when locating and connecting to existing REDHAWK Domains.
* Providing users with the option to copy Properties from other projects in their workspace or choose from pre-defined REDHAWK Properties when developing a Component or Device.
* Displaying a REDHAWK editor when double-clicking on SCD XML files.
* Adding a notification that is now displayed after exporting projects to the Target SDR.
* Providing better support for adding and editing Services in a DCD file.
* Resolving issue so Diagram shapes no longer stack if they are part of a feedback loop.
* Removing old code generation templates for REDHAWK 1.8 from the IDE. Old IDE diagrams for Waveforms and Nodes from pre-2.0.0 were also removed.

### Core Assets
* Creating a new MSDD Device released with bug fixes and enhancements and regenerated for REDHAWK 2.1.
* Updating the `rh.VITA49` REDHAWK shared library to include support for the VITA 49.2 standard. Initial release adheres to the draft specification, revision 00.51 dated 5 Dec 2016, which was available during development.

### REDHAWK Enterprise Integration
* Ensuring the `getAllocIds` method return object is a List.
* Updating REDHAWK Driver to properly clean up driver-registered Device Managers on shutdown.
* Adding IDL source to appropriate Core Framework jars.
Incorporated additional method to produce a jar bundle with a manifest built dynamically via the BnD Tools, source jar, and zip of XSDs.
* Adding implementations of ConnectionManager, AllocationManager interfaces to REDHAWK Driver. Adding utility methods for programatically setting the log level of Domain, Application, Device, and Component resources.
* Adding REST access to Event Channel Manager functionality.
* Updating REDHAWK Driver to have wrapper methods for retrieving state, connections, activeSRIs, and UsesPortStatistics from BULKIO objects. Updating REDHAWK REST to make connections, activeSRIs, UsesPortStatistics, and state available.
* Adding wrapper methods to RedhawkApplication and RedhawkComponent interfaces for easier access to aware(), componentDevices(), componentProcessIds(), and componentImplementations(). REST responses for Component and Application now display componentDevice, aware, componentProcessId, and componentImplementation information.
* Adding ability to get and set adminState from REDHAWK Driver and REDHAWK REST.  Adding ability to view usageState and operationalState from REDHAWK Driver and REDHAWK REST.
* Adding ability to registerRemoteDomain, unregisterRemoteDomains, get device implementation information and a deviceConfiguration profile via REDHAWK Driver and REDHAWK REST.
* Adding ability to preconfigure HTTPS and WSS, and adding documentation to explain this functionality in the Web Server Configuration section in the REDHAWK Enterprise Integration User Guide.
* Adding a helper method to dynamically connect two Components; Improving methods used to set REDHAWK Properties; and Adding AllocationFactory to ease users' ability to generate allocations.
* Adding functionality in REDHAWK REST and Websocket to support JAAS-based method level access.

### Documentation
* Adding a Connection Callbacks section to the REDHAWK Manual.
* Updating the REDHAWK Manual with accessibility rules for all properties. Updating the REDHAWK ICD with the description of the new "property" kind.
* Adding a Libraries chapter in the REDHAWK Manual to explain how to use shared libraries.
* Adding documentation explaining how to use the Allocation Manager.


## Copyrights
This work is protected by Copyright. Please refer to the [Copyright File](COPYRIGHT) for updated copyright information.

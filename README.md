# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description

REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements

**[Release of REDHAWK 2.0.7](https://github.com/redhawksdr/redhawk/releases/tag/2.0.7) (September 2017)** - The effort in REDHAWK 2.0.7 focused on:

#### Core Framework

* Resolving soft package dependency issue so DeviceManager resolves run time environment settings when deploying Devices and Services that have soft package dependencies.
* Resolving issue so that during Application release, calls to the Application object no longer result in misleading errors.
* Improving flexibility to ignore GPP threshold checks when determining if the GPP should go into a BUSY state.
* Resolving issue where processes with spaces in the names would cause the GPP to terminate.
* Resolving issue to allow for slow startup conditions of OmniNames service before starting OmniEvents service.
* Resolving issue with uninitialized data structures with BulkIO and SourceSDDS that inhibited BulkIO data transfers.
* Resolving issue with incorrect exception being thrown during allocateCapacity.
* Resolving issue when shutting down orb from Python resources.
* Providing a warning in the logs if a message is too large.
* Resolving issue with the code generators so they can be run on systems with FIPS enabled.
* Resolving issue so generated C++ FEI Devices do not leak memory when deallocating listeners. Existing Devices must be regenerated and recompiled to apply this fix.
* Resolving a memory leak in FrontendTunerDevice::create(). Existing Devices must be recompiled to apply this fix.
* Resolving issue so the functions returnRFInfoPkt transform all fields between types frontend::RFInfoPkt and FRONTEND::RFInfoPkt.
* Resolving issue so BulkIO input stream calls to read() and tryread() with a sample count do not segfault when their queue contains only an empty packet with EOS set.

#### IDE

* Providing an option in the IDE to perform a FrontEnd Device allocation in the background to aid developers who are debugging their FrontEnd Devices.
* Adding the Eclipse "TM Terminal" in the IDE, a full-featured terminal emulator that provides full ANSI cursor control, readline, and coloring.
* Fixing links in the IDE's help contents so REDHAWK help now displays correctly when links within the help are selected.
* Resolving issue so Diagram shapes no longer stack if they are part of a feedback loop.

#### Documentation

* Adding documentation for developing a logging configuration plug-in that will be used to resolve the LOGGING\_CONFIG\_URI parameter during deployment of Devices, Services and Components.
* Renaming the Generating Code section to Generating Code for Components and explaining the code generation process and what occurs in the IDE when the code is generated.
* Updating the REDHAWK User Manual with accessibility rules for all properties. Updating the REDHAWK ICD with the description of the new "property" kind.

#### REDHAWK Enterprise Integration

* Adding toString() method to RedhawkStruct object, ensuring the getAllocIds(RedhawkStruct s) return object is a List, and adding a helper method for retrieving allocIds called getAllocIds().
* Updating REDHAWK Driver to properly clean up driver-registered Device Managers on shutdown.
* Adding IDL source to appropriate Core Framework jars. Incorporated additional method to produce jar bundle with manifest built dynamically via the BnD Tools, source jar, and zip of XSDs.
* Updating REDHAWK Java Driver and REDHAWK REST to make it easier for users to access External Properties in Waveforms.
* Adding implementations of ConnectionManager, AllocationManager interfaces to REDHAWK Driver. Adding utility methods for programatically setting the log level of Domain, Application, Device, and Component Resources.
* Adding REST access to Event Channel Manager functionality.
* Updating REDHAWK Driver to have wrapper methods for retrieving state, connections, activeSRIs, and UsesPortStatistics from BULKIO objects. Updating REDHAWK REST to make connections, activeSRIs, UsesPortStatistics, and state available.
* Adding wrapper methods to RedhawkApplication and RedhawkComponent interfaces for easier access to aware(), componentDevices(), componentProcessIds(), and componentImplementations(). REST Responses for Component and Application now display componentDevice, aware, componentProcessId, and componentImplementation information.
* Adding ability to get and set adminState from REDHAWK Driver and REDHAWK REST. Adding ability to view usageState and operationalState from REDHAWK Driver and REDHAWK REST.
* Adding ability to registerRemoteDomain, unregisterRemoteDomains, get device implementation information and a deviceConfiguration profile via REDHAWK Driver and REDHAWK REST.
* Preconfiguring HTTPS and WSS in REDHAWK Enterprise Integration and adding Web Server Configuration section in REDHAWK Enterprise Integration User Guide.


**[Release of REDHAWK 2.0.6](https://github.com/redhawksdr/redhawk/releases/tag/2.0.6) (July 2017)** -  The effort in REDHAWK 2.0.6 focused on:

* Initial FOSS Release of REDHAWK Enterprise Integration Assets, which provide the ability to interact with REDHAWK in a JRE environment. The REDHAWK Enterprise Integration Assets include:
   * REDHAWK Driver: Provides simplified access to REDHAWK via standard Java interfaces. This Asset shields all interaction with the underlying REDHAWK Components and provides a simplified API for Java developers interacting with a REDHAWK Domain. The REDHAWK Driver can be leveraged as a standalone Java Archive (JAR) file.
   * REDHAWK OSGi Connector: Implements OSGi's Managed Service Factory interface to allow users to register pre-configured instances of REDHAWK connections into a Karaf container.
   * REDHAWK REST: Provides a REST Service to command and control a REDHAWK instance.
   * REDHAWK WebSocket: Provides an HTML5-compliant WebSocket implementation that enables the ability to stream data from any REDHAWK BulkIO-enabled Port or Event Channel.
   * Camel REDHAWK: Provides a Camel Component for interacting with a REDHAWK Domain. This Component can be connected with other Apache Camel Components as a data flow solution.

  For more information about the REDHAWK Enterprise Integration Assets, refer to the REDHAWK Enterprise Integration User Guide.

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
* Resolving issue with the GPP seg faulting when a Component's soft package dependency does not have proper file access privileges.
* Resolving issue with getStreamDefinition returning a pointer to memory that could be reclaimed during processing; which would invalidate any access through that pointer. The caller now receives a pointer to a copy of a Stream Definition.
* Correctly computing deployment-specific capacities that manage hardware resource requirements in cases where the Component is part of a host collocation deployment.
* Updating Contributor License Agreement (CLA).
* Revising BulkIO High-speed data code example in User Manual.
* Updating the Python package to create instances of the same Application for multiple processes or threads without conflicts.
* Updating the Python Sandbox to make and break connections from multiple threads without conflicts.

## Copyrights

This work is protected by Copyright. Please refer to the [Copyright File](COPYRIGHT) for updated copyright information.

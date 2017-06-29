# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description
REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements
**[Release of REDHAWK 2.0.6](https://github.com/redhawksdr/redhawk/releases/tag/2.0.6) (July 2017)** - Download the new Core Framework, IDE, and documentation from our Downloads page. The effort in REDHAWK 2.0.6 focused on:

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

**[Release of REDHAWK 2.0.5](https://github.com/redhawksdr/redhawk/releases/tag/2.0.5) (February 24, 2016)** - The effort in REDHAWK 2.0.5 focused on:

* Maintaining the correct time stamp when pushing data from the Sandbox DataSource.
* Improving a Component's response to messages irrespective of whether or not the Component is started or stopped.
* Improving FileSink support for framed data and timecode with BLUE file output.
* Improving the handling of missing event message fields in C++ and Python.
* Ensuring external Port names are recognized.
* Addressing numerous bug fixes.

**[Release of REDHAWK 2.0.4](https://github.com/redhawksdr/redhawk/releases/tag/2.0.4) (December 30, 2016)** - The effort in REDHAWK 2.0.4 focused on:

* Adding support for the CentOS 7 operating system.
* Updating the REDHAWK IDE to require Java 8.
* Adding support for two new Core Assets, SinkSDDS and SourceSDDS, which convert between SDDS and BulkIO data formats.
* Adding messages to indicate to the user the reason why the GPP is busy.
* Adding more IDE XML validation to help users catch issues sooner when designing projects.
* Correcting issues with Redhawk-generated build scripts that prevented errors from being displayed.
* Adding 'Connect' and 'Show Properties View' in the Graphiti diagram context menus.
* Adding GPP label to the Domain Manager log message when deploying Components or Waveforms to enable quick identification of which GPP the Domain Manager is attempting to launch Components on.
* Improving the REDHAWK Explorer product to use the new Graphiti diagrams introduced in the REDHAWK 2.0.0 IDE.
* Improving IDE namespace support to give users an error if they have multiple resources with conflicting IDs in the SDRROOT.
* Addressing numerous bug fixes.

**[Release of REDHAWK 2.0.3](https://github.com/redhawksdr/redhawk/releases/tag/2.0.3) (October 5, 2016)** - REDHAWK 2.0.3 addresses the following:

* Improvements to GPP automatic resource monitoring caused a memory leak. - Fixed.
* Incorrect return type in the GPS interface implementation of FrontEnd Interfaces. - Fixed.
* Python Devices failed to launch when a logging config file is specified. - Fixed.

**[Release of REDHAWK 2.0.2](https://github.com/redhawksdr/redhawk/releases/tag/2.0.2) (September 1, 2016)** - The effort in REDHAWK 2.0.2 focused on:

* Improving how error messages are displayed to the user in the IDE
* Adding new abilities to interact with logging for Components and Devices in the IDE
* Providing better awareness of resource utilization on the host computer
* Adding better support for creating FEI Devices written in Python
* Addressing numerous Discrepancy Reports (DRs)

## Copyrights
This work is protected by Copyright. Please refer to the [Copyright File](COPYRIGHT) for updated copyright information.

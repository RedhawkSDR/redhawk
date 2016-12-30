# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description
REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements
**[Release of REDHAWK 2.0.4](https://github.com/redhawksdr/redhawk/releases/tag/2.0.4) (December 2016)** - The effort in REDHAWK 2.0.4 focused on:

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

**[Release of TuneFilterDecimate 2.0.1 for the REDHAWK 2.0 series](https://github.com/RedhawkSDR/TuneFilterDecimate/releases/tag/2.0.1) (July 29, 2016)** - TuneFilterDecimate 2.0.1 resolves the following issue:

* Fixed calculation of SRI keyword `CHAN_RF` for tuning mode `NORM`

**[Release of FileWriter 4.0.2 for the REDHAWK 2.0 series](https://github.com/redhawksdr/FileWriter/releases/tag/4.0.2) (July 5, 2016)** - FileWriter 4.0.2 resolves the following issues:

* Fixed feature that starts a new file following a retune
* Fixed initial configuration of overridden property values
* Fixed several bugs with recording timer

**[Release of USRP_UHD 3.0.2 for the REDHAWK 1.10 series](https://github.com/redhawksdr/USRP_UHD/releases/tag/3.0.2) (May 11, 2016)** - USRP_UHD 3.0.2 resolves the following issues:

* Fixed error causing invalid SRI to be sent for all allocations after the initial allocation
* Added node-config script to the DeviceAdded node-config script to the Device
* Fixed error causing Ubuntu build failure

**[Release of REDHAWK 2.0.1](https://github.com/redhawksdr/redhawk/releases/tag/2.0.1) (April 15, 2016)** - The effort in REDHAWK 2.0.1 focused on:

* Enhancing the level of control that a system deployer has to customize the reservation schema used to manage computing resources
* Adding Python operators and Java methods to simplify common arithmetic operations on BulkIO time stamps
* Addressing numerous Discrepancy Reports (DRs)

**[Release of REDHAWK 2.0.0](https://github.com/redhawksdr/redhawk/releases/tag/2.0.0) (December 10, 2016)** - The effort in REDHAWK 2.0.0 focused on improving system management, establishing a core set of REDHAWK assets, and enhancing the IDE user experience, including:

* improving processing performance
* promoting consistency among core assets
* improving and focusing on a comprehensive set of core assets, including the addition of Waveforms
* providing an improved user experience by re-implementing IDE diagrams for Waveforms and Nodes
* adding IDE support for REDHAWK shared library projects
* adding IDE support for differentiating projects with namespaces

## Copyrights
This work is protected by Copyright. Please refer to the [Copyright File](COPYRIGHT) for updated copyright information.

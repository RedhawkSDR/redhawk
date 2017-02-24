# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description
REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements
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

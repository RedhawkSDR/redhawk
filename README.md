# REDHAWK

![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)

## Description

REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements
**[Release of REDHAWK 2.0.8](https://github.com/redhawksdr/redhawk/releases/tag/2.0.8) (February 2018)** - The effort in REDHAWK 2.0.8 focused on:

#### Core Framework
* Preventing sb.DataSink from adding an empty timestamp when it receives EOS in an empty packet.
* Adding inline header comments documenting C++ BulkIO input stream, output stream, and data block APIs.
* Fixing improperly scoped locks in Core Framework control.
* Implementing several C++ fixes to allow REDHAWK to compile on newer compilers.
* Correcting default property kinds in the DTD and XSD so they are no longer out of sync with the behavior of the Core Framework and the ICD.
* Adding new behavior to the C++ input stream API: It is now possible to "peek" into data sets that have reached EOS by setting consume to 0 when using read or tryread.
* Patching omniORBpy to prevent possible segfaults in multithreaded code.
* Correcting behavior so readonly property kind properties for Devices and Services can now be modified during deployment using Device Configuration Descriptor (dcd.xml) file.

#### IDE
* Resolving issue so when launching Waveforms containing references to mistyped properties, the IDE displays all the properties including the property that had a mis-matched override in the SAD file.
* Removing old code generation templates for REDHAWK 1.8 from the IDE. Old IDE diagrams for Waveforms and Nodes from pre-2.0.0 were also removed.
* Adding M2Eclipse to the REDHAWK IDE, which provides tooling to work with Maven-based projects such as the REDHAWK Enterprise Integration assets.

#### Documentation
* Adding documentation to the REDHAWK Manual regarding naming elements in structures such that element names can be reused across different structures.
* Adding documentation explaining how to use the Allocation Manager.

#### REDHAWK Enterprise Integration
* Enhancing the REDHAWK Enterprise Integration Demo GUI by adding support for Raster and Line plots from time- or fft-based data using Sigplot, using JTransforms with REDHAWK Websocket to perform FFT, cleaning up the Demo GUI, and updating screenshots and documentation to include new FFT and Raster functionality in the GUI.
* Adding a helper method to dynamically connect two Components; Improving methods used to set REDHAWK Properties; and Adding AllocationFactory to ease users' ability to generate allocations.
* Adding functionality in REDHAWK REST and Websocket to support JAAS-based method level access.

## Copyrights

This work is protected by Copyright. Please refer to the [Copyright File](COPYRIGHT) for updated copyright information.

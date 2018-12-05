# REDHAWK
![REDHAWK IDE](images/REDHAWK_ScreenShot_scaled.png)
## Description
REDHAWK is a software-defined radio (SDR) framework designed to support the development, deployment, and management of real-time software radio applications. To support the design and development of software applications, REDHAWK provides tools that allow development and testing of software modules called "Components" and composition of Components into "Waveform Applications" that can be seamlessly deployed on a single computer or multiple network-enabled computers.

The REDHAWK integrated development environment (IDE) provides tools to support development of REDHAWK software. The development and deployment of REDHAWK Applications are aided by graphical editors and drag-and-drop Waveform construction. The IDE allows users to interact with and control multiple running REDHAWK instances and applications.

## Recent Announcements

### **[Release of REDHAWK 2.2.1](https://github.com/redhawksdr/redhawk/releases/tag/2.2.1) (December 2018)**
The effort in REDHAWK 2.2.1 focused on:

* Improving how the `MessageSupplier` port's `sendMessages()` method handles bulk message failures when the size exceeds the maximum CORBA transfer size. On failure, messages are now sent individually.
* Fixing the Octet output format for the bluefile FileSink.
* Changing the output for the "number of samples pushed" when data for a BulkIO stream is generated spanning multiple timestamps. The output changed from being the "number of samples spanning the timestamp packets" to being the "number of samples that was requested".
* Resolving an issue for BulkIO input ports to hold multiple back-to-back streams with the same stream ID in a pending, independent state.
* Ensuring that the Python Publisher and Subscriber classes disconnect from their event channels before unregistering from the Event Channel Manager.
* Ensuring that calling stop on a component no longer causes an exception from a timeout if the NOOP sleep time in C++ components is too long.
* Enabling waveforms to successfully run when the `useScreen` property is set to true on the GPP in a Device Manager.
* Correctly resolving `@@@WAVEFORM.INSTANCE@@@` and `@@@DEVICE_MANAGER.NAME@@@` in log files for components and devices, respectively.
* Fixing an issue with `loadSADFile` and `generateSADXML`. When using `loadSADFile`, all connections in the XML file are appropriately created in the Python sandbox, and when using `generateSADXML`, connections in the sandbox are included in the resulting XML.
* Preserving `EOS` and `sriChanged` flags on a per-stream basis when a BulkIO input port queue is flushed. As a result, when a queue flush occurs, any stream that has an EOS in the queue will receive an empty packet with EOS set.
* Preventing duplicate service name registration in the REDHAWK domain. When a Device Manager attempts to register a service with a name that is already in use, the Domain Manager throws an exception and the Device Manager terminates the service's process.
* Generating a unique identifier for NIC allocations from host-collocated components in a waveform.
* Supporting NIC allocations for host-collocated components in a waveform.
* Fixing a memory leak in BulkIO input ports when using `getPacket()` to fetch data.
* Fixing an issue to allow files to be truncated when component host logging is enabled on the GPP.
* Enabling persistence at runtime (persistence is compiled into the Core Framework by default) by providing a backend database to store the configuration when launching a Domain Manager using the `nodeBooter` argument `--dburl`.
The persistence options to `nodeBooter` are handled more strictly:
    * If `--dburl` is given when launching a Domain Manager, and the database file location cannot be accessed, an error is reported and the Domain Manager is not launched.
    * If `--dburl` is given when launching only a Device Manager, an error is reported and the Device Manager is not launched.
    * The `--nopersist` argument to `nodeBooter` is deprecated and has no effect.
* Enabling Non-Uniform Memory Access (NUMA) affinity processing by default in the GPP.  Prior releases required a source code rebuild to enable this feature.
* Resolving an issue to allow for the use of a connection ID in each control port's getter methods, FrontEnd Interfaces, or custom IDL when a value is being returned.
* Resolving an issue with increased application launch times identified during endurance testing.
* Correcting the handling of shared library SoftPkg dependencies for loadable devices to properly add Java and Python dependencies to the environment prior to running components.

## Copyrights
This work is protected by Copyright. Please refer to the [Copyright File](COPYRIGHT) for updated copyright information.

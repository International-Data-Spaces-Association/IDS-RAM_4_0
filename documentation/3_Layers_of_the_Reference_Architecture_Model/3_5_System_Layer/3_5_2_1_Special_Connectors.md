# Special Connectors

What type of Connector is to be implemented may depend on
various aspects, such as the execution environment given or
the current developmental stage regarding Data Services or
Data Flows used. In the following, three exemplary scenarios
are outlined:

## Developer Connector
As is the case for the development of any software, developing
Data Services or configuring Data Flows comprises several
phases (specification, implementation, debugging, testing,
profiling, etc.). For reasons of simplification, it may be useful
to run Connectors without application container management.
In doing so, the development process can be accelerated,
as packing and starting the container can be omitted,
and debugging can be done in the development environment.
After successfully passing all tests, the configuration model
used for the Developer Connector can be used to deploy a
productive (live) Connector. Upon deployment in the live environment,
the Connector is ready for being used.

## Mobile Connector
Mobile operating systems (e.g., Android, iOS, or Windows
Mobile) use platforms with limited hardware resources. In
such environments, application container management is
not necessarily required. The same applies for operating systems
which do not support application containers, or systems
without any operating system (e.g. microcontrollers). In such
environments, Data Services (and the execution core) can be
started directly on the host system, without requiring any virtualization.
The differences between Connectors with containers
and Connectors without containers can be met by different
Execution Configurator modules.


## Embedded Connector
Another way of Connector miniaturization offers the Embedded
Connector. Embedded Connectors have the same design
as Mobile Connectors, and do not necessarily require application
container management either. However, unlike Mobile
or Developer Connectors, the Configuration Manager is
not part of the Connector hardware platform here, which is
why remote configuration capabilities of the platform are required
(e.g., using an API or configuration files).
Additional steps for Connector miniaturization may include
the use of a common runtime for all components, or simplified
versions of the Data Router and the Data Bus. If data
is to be sent to a fixed recipient only, a simple Data Bus client
library may be sufficient. Similarly, it may be sufficient to
hard-code a single, fixed connection to the Data Bus instead
of using a configurable component. To save communication
overhead, simple API calls inside the common runtime could
be used.
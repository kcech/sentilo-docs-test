API Docs
========

Contents:

.. toctree::
   :maxdepth: 1

   api_docs/general_model
   api_docs/security
   api_docs/services
	
The Application Programming Interface (API) define a set of commands,
functions and protocols that must be followed by who wants to interact
with the platform from external systems, like sensors/actuators or
applications.

The starting capacities of the platform related to its external
interface are:

-  Allow registering applications/modules and providers/sensors in the
   platform (Catalog).
-  Allow to applications/modules and sensors to subscribe to services
   defined in the catalog as well as post events(Publish/Subscribe).
-  Allow sending information from sensors to applications/modules
   (Data).
-  Allow sending orders from applications/modules to sensors (Order).
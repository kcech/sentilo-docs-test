Data
====

Description
-----------

The data service allows to read, write or delete the observations of the
registered sensors.

All requests for this service will have the following format:

::

    http://<your_api_server.com>/data/<provider_id>/<sensor_id>

where **** and **** correspond to the sensor and provider identifiers on
which we want to perform the requested action.

Actions
-------

The available actions for this service are:

-  `Publish observations of a sensor <./data/publish_sensor_data>`__
-  `Publish observations from sensors of a
   provider <./data/publish_provider_sensor_data>`__
-  `Delete observations <./data/delete_sensor_data>`__
-  `Read observations from a sensor <./data/retrieve_sensor_data>`__
-  `Read observations from sensors of a
   provider <./data/retrieve_provider_sensor_data>`__

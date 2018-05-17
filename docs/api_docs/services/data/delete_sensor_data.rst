Delete Observations
===================

Description
-----------

This action allows to delete observations made by one or several sensors
of a provider.

::

    http://<your_api_server.com>/data/<provider_id>/<sensor_id>

.. raw:: html

   <table>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Formats

.. raw:: html

   </th>

.. raw:: html

   <td>

json

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Method

.. raw:: html

   </th>

.. raw:: html

   <td>

DELETE

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Permission

.. raw:: html

   </th>

.. raw:: html

   <td>

Writing

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Returns

.. raw:: html

   </th>

.. raw:: html

   <td>

No output data

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

Parameters
----------

No additional data is sent.

Response data
-------------

This action does not return additional data beyond the `HTTP status
code <../../general_model#reply>`__.

Examples
--------

Request to delete the last observation of a sensor
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If we want delete the last observation received by the plataform of the
sensor with id REC1102 of the provider named rec, the request to do is:

::

    http://<your_api_server.com>/data/rec/RE0012

Request to delete the last observations of a provider´s sensors
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If we want to delete the last observation of each sensor ot the provider
named rec, the request to do is:

::

    http://<your_api_server.com>/data/rec

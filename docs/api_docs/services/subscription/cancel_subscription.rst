Cancel subscriptions
====================

Description
-----------

This action allows to cancel any or a set of our active subscriptions.

::

   http://<your_api_server.com>/subscribe/<event_type>/<resource_id>

.. raw:: html

   <table>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Format

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

Write

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

No additional data returned

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

**** and **** are optional and allow to filter the subscription to
cancel by event type or related resource.

Parameters
----------

No additional data can be sent.

Response data
-------------

This action does not return any additional data beyond the `HTTP status
code <../../general_model.html#reply>`__.

Examples
--------

Request to cancel subscriptions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If we want to cancel all our active subscriptions, the request will be:

::

   http://<your_api_server.com>/subscribe

Request to cancel subscriptions for a specific event type
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If we want to cancel all our active subscriptions of a specific event
type like order, the request will be:

::

   http://<your_api_server.com>/subscribe/order

Request to cancel subscriptions for a specific resource
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If we want to cancel all our active data subscriptions of a specific
sensor like RE0012 belonging to the rec provider, the request will be:

::

   http://<your_api_server.com>/subscribe/data/rec/RE0012

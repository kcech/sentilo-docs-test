Publish Alarm
=============

Description
-----------

This action allows you to publish an alarm related with an alert. Once
the system receives the alarm, persists it and sends the notification to
all who are subscribed to alarms alert.

::

    http://<your_api_server.com>/alarm/<alert_id> 

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

PUT

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

Return

.. raw:: html

   </th>

.. raw:: html

   <td>

No additional data is returned

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

Each alarm will have its own associated information structure defined in
the generic format (JSON).

The platform only persists and transfers the information to recipients
without interpreting its contents.

.. raw:: html

   <table>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Key

.. raw:: html

   </th>

.. raw:: html

   <th>

Description

.. raw:: html

   </th>

.. raw:: html

   <th>

Optional

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

message

.. raw:: html

   </td>

.. raw:: html

   <td>

Free field

.. raw:: html

   </td>

.. raw:: html

   <td>

Not

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

Response data
-------------

This actions does not return additional data beyond the `HTTP status
code <../../general_model#reply>`__ associated with each request to
the platform.

Examples
--------

Post a new alarm associated with an alert
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following example shows how to send a request to the platform in
order to publish a new alarm associated to an alert with identifier 43:

::

    http://<your_api_server.com>/alarm/43 

and like body message:

::

   {"message":"Threshold limit exceeded: 32"} 

**Please note the following:**\\

-  (% style=“font-size: 16px; background-color: rgb(245, 245, 245);”
   %)If the alert is in offline state, the server rejects the
   publication.

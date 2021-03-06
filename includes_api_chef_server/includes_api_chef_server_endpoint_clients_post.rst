.. The contents of this file are included in multiple topics.
.. This file should not be changed in a way that hinders its ability to appear in multiple documentation sets.

The ``POST`` method is used to create a new |chef api client|.

This method has no parameters.

**Request**

.. code-block:: xml

   POST /organizations/NAME/clients

with a request body similar to:

.. code-block:: javascript

   {
     "name": "name_of_API_client",
     "admin": false
   }

where ``name_of_API_client`` is the name of the |chef api client| to be created and ``admin`` indicates whether the |chef api client| will be run as an admin |chef api client|.

**Response**

The response is similar to:

.. code-block:: javascript

   {
     "uri": "http://localhost:4000/clients/monkeypants",
     "private_key": "-----BEGIN PRIVATE KEY-----\n
                   MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCyVPW9YXa5PR0rgEW1updSxygB\n
                   wmVpDnHurgQ7/gbh+PmY49EZsfrZSbKgSKy+rxdsVoSoU+krYtHvYIwVfr2tk0FP\n
                   nhAWJaFH654KpuCNG6x6iMLtzGO1Ma/VzHnFqoOeSCKHXDhmHwJAjGDTPAgCJQiI\n
                   eau6cDNJRiJ7j0/xBwIDAQAB\n
                   -----END PRIVATE KEY-----"
   }

Store the private key in a safe place. It will be required later (along with the client name) to access the |chef server| when using the |api chef server|.

**Response Codes**

.. list-table::
   :widths: 200 300
   :header-rows: 1

   * - Response Code
     - Description
   * - ``201``
     - |response code 201 created|
   * - ``400``
     - |response code 400 bad request|
   * - ``401``
     - |response code 401 unauthorized|
   * - ``403``
     - |response code 403 forbidden|
   * - ``409``
     - |response code 409 conflict|
   * - ``413``
     - |response code 413 entity_too_large|

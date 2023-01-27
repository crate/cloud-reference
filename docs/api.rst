===
API
===

Similar to Croud, we offer an API to allow programmatic access to our Cloud
products. The API can be accessed by generating a key and secret in your 
account page:

.. image:: _assets/img/create-api-key.png
   :alt: Cloud Console New Api Key

Click the *Generate new key* button to create your key. A popup with your
key and secret will appear. Make sure to store your secret safely, as you
cannot access it again.

Access
------

The key and secret can be used as HTTP Basic Auth credentials when calling the
API:

.. code-block:: console

    sh$ $ curl -s -u $your_key:$your_secret https://console.cratedb.cloud/api/v2/users/me/ {"email":"some@example.com","hmac":"...","is_superuser":false,"name":"Some User","organization_id":"123","status":"active","uid":"uid","username":"some@example.com"}


Examples
--------

Our API is documented with `Swagger`_. It contains endpoints for:

- Organizations
- Regions
- Projects
- Clusters
- Products
- Users
- Roles
- Subscriptions
- Audit logs

It provides example requests with all the required parameters, expected
responses, and all response codes. Access the API documentation `here`_.

.. _Swagger: https://console.cratedb.cloud/api/docs
.. _here: https://console.cratedb.cloud/api/docs

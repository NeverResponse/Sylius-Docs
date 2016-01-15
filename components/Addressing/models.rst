Models
======

.. _component_addressing_model_address:

Address
-------

The customer's address is represented by an **Address** model. It should contain all data
concerning customer's address and as default has the following properties:

+--------------------+------------------------------------------------+
| Property           | Description                                    |
+====================+================================================+
| id                 | Unique id of the address                       |
+--------------------+------------------------------------------------+
| firstName          | Customer's first name                          |
+--------------------+------------------------------------------------+
| lastName           | Customer's last name                           |
+--------------------+------------------------------------------------+
| phoneNumber        | Customer's phone number                        |
+--------------------+------------------------------------------------+
| organization       | Organization's name                            |
+--------------------+------------------------------------------------+
| country            | Country's ISO code                             |
+--------------------+------------------------------------------------+
| administrativeArea | Administrative area's code                     |
+--------------------+------------------------------------------------+
| locality           | Address' major locality i.e. city              |
+--------------------+------------------------------------------------+
| dependentLocality  | Address' minor locality i.e. neighbourhood     |
+--------------------+------------------------------------------------+
| firstAddressLine   | First line of the address block                |
+--------------------+------------------------------------------------+
| secondAddressLine  | Second line of the address block               |
+--------------------+------------------------------------------------+
| postcode           | Address' postcode                              |
+--------------------+------------------------------------------------+
| createdAt          | Date when address was created                  |
+--------------------+------------------------------------------------+
| updatedAt          | Date of last address' update                   |
+--------------------+------------------------------------------------+


.. note::
   This model implements the :ref:`component_addressing_model_address-interface`. |br|
   For more detailed information go to `Sylius API Address`_.

.. _Sylius API Address: http://api.sylius.org/Sylius/Component/Addressing/Model/Address.html

.. _component_addressing_model_country:

Country
-------

The geographical area of a country is represented by a **Country** model.
It should contain all data concerning a country and as default has the following properties:

+---------------------+----------------------------------------------+
| Property            | Description                                  |
+=====================+==============================================+
| id                  | Unique id of the country                     |
+---------------------+----------------------------------------------+
| code                | Country's ISO code                           |
+---------------------+----------------------------------------------+
| administrativeAreas | Collection of **AdministrativeArea** objects |
+---------------------+----------------------------------------------+
| enabled             | Indicates whether country is enabled         |
+---------------------+----------------------------------------------+

.. note::
   This model implements the :ref:`component_addressing_model_country-interface`
   and :ref:`component_resource_code-aware-interface`. |br|
   For more detailed information go to `Sylius API Country`_.

.. _Sylius API Country: http://api.sylius.org/Sylius/Component/Addressing/Model/Country.html

.. _component_addressing_model_administrative-area:

AdministrativeArea
------------------

Smaller area inside a country is represented by a **AdministrativeArea** model.
You can use it to manage provinces or states and assign it to an address as well.
It should contain all data concerning an administrative area and as default has the following properties:

+----------+----------------------------------------------+
| Property | Description                                  |
+==========+==============================================+
| id       | Unique id of the administrative area         |
+----------+----------------------------------------------+
| code     | Unique code of the administrative area       |
+----------+----------------------------------------------+
| name     | Administrative area's name                   |
+----------+----------------------------------------------+
| country  | The **Country** this area is assigned to     |
+----------+----------------------------------------------+

.. note::
   This model implements the :ref:`component_addressing_model_administrative-area-interface`
   and :ref:`component_resource_code-aware-interface`. |br|
   For more detailed information go to `Sylius API AdministrativeArea`_.

.. _Sylius API AdministrativeArea: http://api.sylius.org/Sylius/Component/Addressing/Model/AdministrativeArea.html

.. _component_addressing_model_zone:

Zone
----

The geographical area is represented by a **Zone** model.
It should contain all data concerning a zone and as default has the following properties:

+----------+---------------------------------------------------------+
| Property | Description                                             |
+==========+=========================================================+
| id       | Unique id of the zone                                   |
+----------+---------------------------------------------------------+
| code     | Unique code of the zone                                 |
+----------+---------------------------------------------------------+
| name     | Zone's name                                             |
+----------+---------------------------------------------------------+
| type     | Zone's type                                             |
+----------+---------------------------------------------------------+
| scope    | Zone's scope                                            |
+----------+---------------------------------------------------------+
| members  | All of the **ZoneMember** objects assigned to this zone |
+----------+---------------------------------------------------------+

.. note::
   This model implements the :ref:`component_addressing_model_zone-interface`
   and :ref:`component_resource_code-aware-interface`. |br|
   For more detailed information go to `Sylius API Zone`_.

.. _Sylius API Zone: http://api.sylius.org/Sylius/Component/Addressing/Model/Zone.html

.. _component_addressing_model_zone-member:

ZoneMember
----------

In order to add a specific location to a **Zone**,
an instance of **ZoneMember** must be created with that location's code.
On default this model has the following properties:

+-----------+------------------------------------------------------+
| Property  | Description                                          |
+===========+======================================================+
| id        | Unique id of the zone member                         |
+-----------+------------------------------------------------------+
| code      | Unique code of affiliated member i.e. country's code |
+-----------+------------------------------------------------------+
| belongsTo | The **Zone** this member is assigned to              |
+-----------+------------------------------------------------------+

.. note::
   This model implements :ref:`component_addressing_model_zone-member-interface`
   and :ref:`component_resource_code-aware-interface`. |br|
   For more detailed information go to `Sylius API ZoneMember`_.

.. _Sylius API ZoneMember: http://api.sylius.org/Sylius/Component/Addressing/Model/ZoneMember.html

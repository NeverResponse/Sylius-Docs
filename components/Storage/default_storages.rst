Default Storages
================

By default there are three storages available.

.. _component_storage_cookie-storage:

CookieStorage
-------------

**CookieStorage** is used to manage data in the cookies' `ParameterBag`_
of Symfony's `Request`_ class, which we quire via their `RequestStack`_ service.

.. _ParameterBag: http://api.symfony.com/2.0/Symfony/Component/HttpFoundation/ParameterBag.html
.. _Request: http://api.symfony.com/2.0/Symfony/Component/HttpFoundation/Request.html
.. _RequestStack: http://api.symfony.com/2.7/Symfony/Component/HttpFoundation/RequestStack.html

.. _component_storage_doctrine-cache-storage:

DoctrineCacheStorage
--------------------

**DoctrineCacheStorage** is used to manage data in Doctrine's `Cache`_ class.

.. _Cache: http://www.doctrine-project.org/api/common/2.5/class-Doctrine.Common.Cache.Cache.html

.. _component_storage_session-storage:

SessionStorage
--------------

**SessionStorage** is used to manage data in any class implementing the Symfony's `SessionInterface`_.

.. _SessionInterface: http://l3.shihan.me/api/class-Symfony.Component.HttpFoundation.Session.SessionInterface.html

.. note::
   Every default storage implements the :ref:`component_storage_storage-interface`.

.. tip::
   Feel free to implement your own storage, using any container you would like!

Basic Usage
===========

Storing data
------------

The methods of every **storage** work the same way. The only difference is the type of container we store in.

For example let's use the :ref:`component_storage_cookie-storage`:

.. code-block:: php

   <?php

   use Sylius\Component\Storage\CookieStorage;
   use Symfony\Component\HttpFoundation\RequestStack;

   $key = 'aeiouy';
   $value = 'Hello!';

   $requestStack = // get the requestStack which request cookies' data you would like to manage

   $storage = new CookieStorage($requestStack);

   $storage->setData($key, $value); // insert your data to the storage

   $storage->hasData($key); // returns true as the key is in the storage
   $storage->getData($key); // returns 'Hello'

   $storage->removeData($key); // remove your data from the storage
   $storage->hasData($key); // now returns false as we removed the key along with it's value

If the key which you try to get doesn't exist in the storage,
the ``getData`` method returns it's second parameter.
If it isn't specified, returns null.

.. code-block:: php

   $storage->getData('failure', 'Goodbye'); // returns 'Goodbye'
   $storage->getData('failure'); // returns null

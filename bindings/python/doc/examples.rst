Examples
==================

Scan contexts and list channels of each device

.. code-block:: python

 import iio

 for ctxname in iio.scan_contexts():
     ctx = iio.Context(ctxname)
     for dev in ctx.devices:
         if dev.channels:
             for chan in dev.channels:
                 print("{} - {} - {}".format(ctxname, dev.name, chan._id))
         else:
             print("{} - {}".format(ctxname, dev.name))


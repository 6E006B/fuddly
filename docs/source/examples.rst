.. _useful-examples:

Useful Examples
***************

.. _ex:zip-mod:

ZIP archive modification
========================

The following example (refer to the figure `below <#zip-example>`_)
illustrates how to modify the second file contents of a ZIP archive,
and let ``fuddly`` recalculate every constraints for you.

.. code-block:: python
   :linenos:

    abszip = dm.get_atom('ZIP')
    abszip.set_current_conf('ABS', recursive=True)
    abszip.absorb(zip_buff, constraints=AbsNoCsts(size=True,struct=True)

    abszip['ZIP/file_list/file:2/data'][0].absorb(b'TEST', constraints=AbsNoCsts())
    abszip.unfreeze(only_generators=True)
    abszip.get_value()


.. _zip-example:
.. figure::  images/zip_mod.png
   :align:   center

   ZIP archive second file contents modification

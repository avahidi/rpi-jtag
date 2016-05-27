
========
RPi-JTAG
========

.. image:: data/side.jpg
	   :alt: version 0.1 in action

Raspberry Pi IO header to JTAG IDC-20P connector, plus optional UART connectors and power indicators.

Note that JTAG pins are shared with GPIO, which you will need to re-configure in order to enable JTAG.
I use my minipi_ bootloader to do this, which gives me access to JTAG early in the boot.
But you can also do this manually from the u-boot prompt::

    mw.l 0x3F200000 0x00002000
    mw.l 0x3F200008 0x0061B0C0


license
-------

CERN OHL v1.2, because lets face it, this is rocket science ;)

see LICENSE_ for details

download
--------

The repository contains the KiCad project. There are also standalone schematics_ and gerber files for
oshpark_ and dirtypcbs_ (and itead/seeed). Note that I have only tested dirtypcbs.


.. _minipi: https://bitbucket.org/vahidi/mini-pi-bootloader
.. _oshpark: https://bitbucket.org/vahidi/rpi-jtag/raw/master/data/oshpark.zip
.. _dirtypcbs: https://bitbucket.org/vahidi/rpi-jtag/raw/master/data/dirtypcbs.zip
.. _schematics: https://bitbucket.org/vahidi/rpi-jtag/raw/master/data/schema.pdf
.. _LICENSE: https://bitbucket.org/vahidi/rpi-jtag/raw/master/LICENSE

.. image:: data/top.jpg
	   :alt: top view

.. image:: data/bottom.jpg
	   :alt: botom view

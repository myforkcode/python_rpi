.. -*- coding: utf-8; -*-

================================================
 OpenWrt Feed for Python Module on Raspberry Pi
================================================

This is an openwrt feed providing python modules for Raspberry Pi.
The feed provides moduless below:

* `Rpi.GPIO python module <https://pypi.python.org/pypi/RPi.GPIO>`_ as `python-rpi-gpio` package.

Usage
=====

To configure the openwrt buildroot, put a line below in your feeds.conf.

.. code-block:: text

    src-git python_rpi https://github.com/pman0214/python_rpi.git

Update the feed and install the package feeds.

.. code-block:: bash

   $ ./scripts/feeds update python_rpi
   $ ./scripts/feeds install python-rpi-gpio

Run `make menuconfig` and locate packages to configure.
Python packages are available under ``Languages > Python``.

Package building documents are available on `OpenWrt Wiki - How to Build a Single Package <https://wiki.openwrt.org/doc/howtobuild/single.package>`_.

Under Development
=================

The packages are tested on Chaos Calmer 15.05 on Raspberry Pi 2.
Bug reports and pull requests are welcome.

Copyright, License
==================

Copyright (c) 2016, Shigemi ISHIDA

This software is released under the BSD 3-clause license. See LICENSE.

.. -*- coding: utf-8; -*-

================================================
 OpenWrt Feed for Python Module on Raspberry Pi
================================================

This is an openwrt feed providing python modules for Raspberry Pi.
The feed provides moduless below:

* `Rpi.GPIO python module <https://pypi.python.org/pypi/RPi.GPIO>`_.

Usage
=====

To configure the openwrt buildroot, put a line below in your feeds.conf.

.. code-block:: text

    src-git python_rpi https://github.com/pman0214/python_rpi.git

Testing
=======

The feed is only tested with Chaos Calmer 15.05 on Raspberry Pi 2.
Bug reports and pull requests are welcome.

Copyright, License
==================

Copyright (c) 2016, Shigemi ISHIDA

This software is released under the BSD 3-clause license. See LICENSE.

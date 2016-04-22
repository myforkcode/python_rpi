.. -*- coding: utf-8; -*-

====================================
 OpenWrt Feed for Raspberry Pi GPIO
====================================

This is an openwrt feed providing `Rpi.GPIO python module <https://pypi.python.org/pypi/RPi.GPIO>`_.

Usage
=====

To configure the openwrt buildroot, put a line below in your feeds.conf.

.. code-block:: text

    src-git rpi_gpio https://bitbucket.org/pman0214/rpi-gpio-openwrt.git

Copyright, License
==================

Copyright (c) 2016, Shigemi ISHIDA

This software is released under the BSD 3-clause license. See LICENSE.

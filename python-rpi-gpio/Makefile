#
# Copyright (c) 2016, Shigemi ISHIDA
# All rights reserved.
# 
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions
# are met:
# 1. Redistributions of source code must retain the above copyright
#    notice, this list of conditions and the following disclaimer.
# 2. Redistributions in binary form must reproduce the above copyright
#    notice, this list of conditions and the following disclaimer in the
#    documentation and/or other materials provided with the distribution.
# 3. Neither the name of the Institute nor the names of its contributors
#    may be used to endorse or promote products derived from this software
#    without specific prior written permission.
# 
# THIS SOFTWARE IS PROVIDED BY THE INSTITUTE AND CONTRIBUTORS ``AS IS'' AND
# ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
# IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
# ARE DISCLAIMED.  IN NO EVENT SHALL THE INSTITUTE OR CONTRIBUTORS BE LIABLE
# FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
# DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS
# OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION)
# HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT
# LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY
# OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF
# SUCH DAMAGE.

include $(TOPDIR)/rules.mk

PKG_NAME:=RPi.GPIO
PKG_VERSION:=0.6.3
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/e2/58/6e1b775606da6439fa3fd1550e7f714ac62aa75e162eed29dbec684ecb3e/
PKG_MD5SUM:=e4abe1cfb5eacebe53078032256eb837

PKG_LICENSE:=MIT
PKG_MAINTAINER:=Shigemi ISHIDA <ishida+devel@f.ait.kyushu-u.ac.jp>

PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-rpi-gpio
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Raspberry Pi GPIO Python module
  URL:=https://pypi.python.org/pypi/RPi.GPIO
  DEPENDS:=+python
endef

define Package/python-rpi-gpio/description
  RPi.GPIO provides a class to control the GPIO on a Raspberry Pi.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,\
		install --prefix="$(PKG_INSTALL_DIR)/usr" \
	)
endef

define Package/python-rpi-gpio/postinst
#!/bin/sh
# check if we are on real system
if [ -z "$${IPKG_INSTROOT}" ]; then
    echo "Creating a symlink /lib/libc.so to /lib/libc.so.0"
    cd /lib
    ln -s /lib/libc.so.0 /lib/libc.so
fi
exit 0
endef

define Package/python-rpi-gpio/prerm
#!/bin/sh
# check if we are on real system
if [ -z "$${IPKG_INSTROOT}" ]; then
    echo "Creating a symlink /lib/libc.so"
    rm /lib/libc.so
fi
exit 0
endef

$(eval $(call PyPackage,python-rpi-gpio))
$(eval $(call BuildPackage,python-rpi-gpio))

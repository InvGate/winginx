Nginx for Windows
=================

Nginx for Windows is a installer that set up a Nginx instance
running as a service under Microsoft Windows platforms. 
The Nginx version will be downloaded in compilation time from Nginx's official site - http://nginx.org/
To achieve service behaviour it uses the "Non Sucking Service Manager" - http://nssm.cc/

Usage
-----

In order to build this script, you must have NSIS installed. Under Debian/Ubuntu:

::

$ apt-get install nsis

Afterwards, just build the NSIS script:

::

$ make

A binary called ``nginx-service.exe`` will be created inside the "build" folder and can be installed on
any Windows 32&64 bits by just double clicking on it.



New versions
------------

In order to use new versions of Nginx or NSSM you should edit the variables inside the makefile choosing the apropiate version number:

NGINX_VERSION=X.Y.Z
NSSM_VERSION=2.16


Examples
--------

The installer will create a folder called ``sites-available`` just like in debian. Inside there are two examples of Nginx sites. You should copy one of them to the sites-enabled folder and restart the service or reload configuration with:

::

 C:\Program Files (x86)\Nginx> nginx.exe -s reload
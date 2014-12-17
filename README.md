lighttpd POODLE for Debian Squeeze
==================================

First Version (1.6.1)
---------------------

Patch to enable the of the `ssl.use-sslv3` config option to allow Debian Squeeze users to address
CVE-2014-3566 (aka POODLE), without having to upgrade to Wheezy.

- Created initially from a stripped down diff of vanilla lighttpd 1.4.28 -> 1.4.29
- Customised for the patchset already applied to 1.4.28-2+squeeze1.6


```
apt-get source lighttpd
cd lighttpd-1.4.28/
patch -p1 < ../ssl-poodle.patch
dpkg-buildpackage -rfakeroot -uc -b
```

Second Version (1.6.2)
----------------------

Decided that we don't really need a config for something that is insecure!

- Stripped out to barebones and tweaked to make a lighter and a hopefully more portable patch
- *DOES NOT* support `ssl.use-sslv3` config, but disables SSLv3 support by default
- Works with vanilla lighttpd 1.4.28 (albeit with fuzz and skipping debian/changelog)


```
apt-get source lighttpd
cd lighttpd-1.4.28/
patch -p1 < ../ssl-poodle-light.patch
dpkg-buildpackage -rfakeroot -uc -b
```

lighttpd POODLE for Debian Squeeze
==================================

Enables the of the `ssl.use-sslv3` config option to allow for Debian Squeeze users to address
CVE-2014-3566 (aka POODLE), without having to upgrade to Wheezy.

- Created initially from a stripped down diff of vanilla lighttpd 1.4.28 -> 1.4.29
- Customised for the patchset already applied to 1.4.28-2+squeeze1.6


```
apt-get source lighttpd
cd lighttpd-1.4.28/
patch -p1 < ../ssl-poodle.patch
dpkg-buildpackage -rfakeroot -uc -b
```

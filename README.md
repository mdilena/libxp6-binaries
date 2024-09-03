# libxp6-binaries

libxp6 binaries for Debian.

## Build Instructions

When re-building the package for a different distribution, check that the compat level is still valid and has not being deprecated, by looking up at [Compat Upgrade Checklist][https://manpages.debian.org/testing/debhelper/debhelper-compat-upgrade-checklist.7.en.html]. This needs to be done for both libXp6 and its dependencies.

Make sure to build `x11proto-print` first, as that's a require dependency at build time. To build both that and `libXp6` run the following command, from the source code's top folder:

```bash
debuild -b -uc -us
```

If any error comes up check whether other dependencies need to be installed, otherwise the command will generate a new `.deb` file in the folder above the source code one, which can be installed as following:

```bash
sudo apt install ./<package_name>.deb
```

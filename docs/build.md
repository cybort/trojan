# Build

We'll only cover the build process on Linux since we will be providing Windows and macOS binaries. Building trojan on every platform is similar.

## Dependencies

Install these dependencies before you build:

- [CMake](https://cmake.org/) >= 2.8.12
- [Boost](http://www.boost.org/) >= 1.54.0
- [OpenSSL](https://www.openssl.org/) >= 1.0.2

## Clone

Type in

```bash
git clone https://github.com/trojan-gfw/trojan.git
cd trojan/
```

to clone the project and go into the directory.

## Build and Install

Type in

```bash
mkdir build
cd build/
cmake ..
make
ctest
sudo make install
```

to build, test, and install trojan. If everything goes well you'll be able to use trojan.

The `cmake ..` command can be extended with the following options:

- `STATIC`
    - `-DSTATIC=OFF`: don't link any libraries statically (default).
    - `-DSTATIC=ON`: link Boost and libc (only under Windows) statically.
- `SYSTEMD_SERVICE`
    - `-DSYSTEMD_SERVICE=AUTO`: detect systemd automatically and decide whether to install service (default).
    - `-DSYSTEMD_SERVICE=ON`: install systemd service unconditionally.
    - `-DSYSTEMD_SERVICE=OFF`: don't install systemd service unconditionally.
- `CONFIG_TYPE`
    - `-DCONFIG_TYPE=SERVER`: install server config to `/etc/trojan.json` (default).
    - `-DCONFIG_TYPE=CLIENT`: install client config to `/etc/trojan.json`.
    - `-DCONFIG_TYPE=NONE`: don't install config.

[Homepage](.) | [Prev Page](config) | [Next Page](usage)

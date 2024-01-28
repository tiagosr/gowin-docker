Gowin + LiteX FPGA Toolchain
============================

This Docker container is meant to synthesize bitstreams for [Gowin](https://www.gowinsemi.com/en/) FPGAs (like the [Tang Nano 9K](https://wiki.sipeed.com/hardware/en/tang/Tang-Nano-9K/Nano-9K.html)) using [LiteX](https://github.com/enjoy-digital/litex).

Especially useful on newer Macs.

**NOTE:** To get decent performance, turn on [Rosetta in Docker preferences](https://levelup.gitconnected.com/docker-on-apple-silicon-mac-how-to-run-x86-containers-with-rosetta-2-4a679913a0d5).

Example
-------

### Building

Download Gowin_V1.9.9_linux.tar.gz from Gowin's website (needs a user account now) to the same folder as Dockerfile, then run:

```shell
$ docker build . \
    -t gowin-docker:latest
```

### Running

```shell
$ docker run --rm \
    --platform linux/amd64 \
    --mac-address xx:xx:xx:xx:xx:xx \
    -v "${HOME}/gowin_E_YOURLICENSE.lic:/data/license.lic" \
    -it gowin-docker:latest
```

**NOTE:** Change the MAC address to fit with the licensee's MAC address.

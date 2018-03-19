Wavi Core 0.12.1
=====================

This is the official reference wallet for Wavi digital currency and comprises the backbone of the Wavi peer-to-peer network. You can [download Wavi Core](https://www.wavi.org/downloads/) or [build it yourself](#building) using the guides below.

Running
---------------------
The following are some helpful notes on how to run Wavi on your native platform.

### Unix

Unpack the files into a directory and run:

- `bin/wavi-qt` (GUI) or
- `bin/wavid` (headless)

### Windows

Unpack the files into a directory, and then run wavi-qt.exe.

### OS X

Drag Wavi-Qt to your applications folder, and then run Wavi-Qt.

### Need Help?

* See the [Wavi documentation](https://github.com/wavidev-the-man/wavi/tree/master/doc)
for help and more information.
* Ask for help on [WAVI Discord channel](https://discord.gg/6vGNAh5).
* Ask for help on the [BitcoinTalk](https://bitcointalk.org/index.php?topic=3146751) forums.

Building
---------------------
The following are developer notes on how to build Wavi Core on your native platform. They are not complete guides, but include notes on the necessary libraries, compile flags, etc.

- [OS X Build Notes](build-osx.md)
- [Unix Build Notes](build-unix.md)
- [Windows Build Notes](build-windows.md)
- [OpenBSD Build Notes](build-openbsd.md)
- [Gitian Building Guide](gitian-building.md)

Development
---------------------
The Wavi Core repo's [root README](/README.md) contains relevant information on the development process and automated testing.

- [Developer Notes](developer-notes.md)
- [Multiwallet Qt Development](multiwallet-qt.md)
- [Release Notes](release-notes.md)
- [Release Process](release-process.md)
- Source Code Documentation ***TODO***
- [Translation Process](translation_process.md)
- [Translation Strings Policy](translation_strings_policy.md)
- [Unit Tests](unit-tests.md)
- [Unauthenticated REST Interface](REST-interface.md)
- [Shared Libraries](shared-libraries.md)
- [BIPS](bips.md)
- [Dnsseed Policy](dnsseed-policy.md)

### Resources
* Discuss on the [WaviTalk](https://wavitalk.org/) forums, in the Development & Technical Discussion board.
* Discuss on [#wavipay](http://webchat.freenode.net/?channels=wavipay) on Freenode. If you don't have an IRC client use [webchat here](http://webchat.freenode.net/?channels=wavipay).

### Miscellaneous
- [Assets Attribution](assets-attribution.md)
- [Files](files.md)
- [Tor Support](tor.md)
- [Init Scripts (systemd/upstart/openrc)](init.md)

License
---------------------
Distributed under the [MIT software license](http://www.opensource.org/licenses/mit-license.php).
This product includes software developed by the OpenSSL Project for use in the [OpenSSL Toolkit](https://www.openssl.org/). This product includes
cryptographic software written by Eric Young ([eay@cryptsoft.com](mailto:eay@cryptsoft.com)), and UPnP software written by Thomas Bernard.

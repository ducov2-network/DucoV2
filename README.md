<p align="center">
  <a href="http://ducov2.is-great.net/">
    <img src="https://i.imgur.com/VYdLo1T.png" alt="Logo" align="center" width="25%">
  </a>
</p>


# DUCOV2 (DUC2)

Copyright (c) 2019-2020 The DucoV2 Network.    
Copyright (c) 2018-2020 The Arqma Network.    
Copyright (c) 2014-2020 The Monero Project.  
Portions Copyright (c) 2012-2013 The Cryptonote developers.

## BlockChain Specifications

Network properties:
- Name: DUCOV2
- Ticker: DUC2
- Max supply: 75 ml
- Pre: 3.5 ml
- Block time: 90 seconds
- Decimals: 9
- Algorithm: RandomARQ
- Consensus: PoW
- Anonymity: BulletProof RingCT

## DucoV2 resources

- Website: http://ducov2-network.com/
- Block Explorer:
- Source: https://github.com/ducov2-network/ducov2
- Software: https://github.com/ducov2-network/ducov2/releases
- Discord: https://discord.gg/eRZUjdG
- Telegram: https://t.me/ducov2
- BitcoinTalk:
- Twitter: https://twitter.com/DucoV2

## EXCHANGE & TRADE



## Mining Ducov2


## Community Links



## DUCOV2 Introduction

DucoV2 is a private, secure, untraceable, decentralised digital currency. You are your bank, you control your funds, and nobody can trace your transfers unless you allow them to do so.

**Privacy:** DucoV2 uses a cryptographically sound system to allow you to send and receive funds without your transactions being easily revealed on the blockchain (the ledger of transactions that everyone has). This ensures that your purchases, receipts, and all transfers remain absolutely private by default.

**Security:** Using the power of a distributed peer-to-peer consensus network, every transaction on the network is cryptographically secured. Individual wallets have a 25 word mnemonic seed that is only displayed once, and can be written down to backup the wallet. Wallet files are encrypted with a passphrase to ensure they are useless if stolen.

**Untraceability:** By taking advantage of ring signatures, a special property of a certain type of cryptography, DucoV2 is able to ensure that transactions are not only untraceable, but have an optional measure of ambiguity that ensures that transactions cannot easily be tied back to an individual user or computer.

## SSL

As a network, DucoV2 supports complete, cryptographically secured connections at all levels. This includes, but is not limited to DucoV2 Network Nodes (Full nodes), Remote Nodes and all wallets - CLI and GUI for desktop, and Android and iOS [ iOS is under development].    

DucoV2 Network will be consistently implementing the highest security protocols to achieve the greatest privacy for all transactions, as well as all communications made over the DucoV2 Network.

The use of SSL connections means that there will not be any possibility to use the DucoV2 Network with unsecured or tampered connections (daemons), and that your privacy will remain a feature built in a protocol level.

 * Below is an example how to generate SSL Keys with openssl

    `$ openssl genrsa -out /tmp/KEY 4096`    
    `$ openssl req -new -key /tmp/KEY -out /tmp/REQ`    
    `$ openssl x509 -req -days 999999 -sha256 -in /tmp/REQ -signkey /tmp/KEY -out /tmp/CERT`    

 * Above example will generate 4096bit SSL Cert at /tmp (which can be changed)*


## About this project

This is the core implementation of DucoV2. It is open source and completely free to use without restrictions, except for those specified in the license agreement below. There are no restrictions on anyone creating an alternative implementation of DucoV2 that uses the protocol and network in a compatible manner.

As with many development projects, the repository on Github is considered to be the "staging" area for the latest changes. Before changes are merged into that branch on the main repository, they are tested by individual developers in their own branches, submitted as a pull request, and then subsequently tested by contributors who focus on testing and code reviews. That having been said, the repository should be carefully considered before using it in a production environment, unless there is a patch in the repository for a particular show-stopping issue you are experiencing. It is generally a better idea to use a tagged release for stability.

**Anyone is welcome to contribute to DucoV2's codebase!** If you have a fix or code change, feel free to submit it as a pull request directly to the "master" branch. In cases where the change is relatively small or does not affect other parts of the codebase it may be merged in immediately by any one of the collaborators. On the other hand, if the change is particularly large or complex, it is expected that it will be discussed at length either well in advance of the pull request being submitted, or even directly on the pull request.

## License

See [LICENSE](LICENSE).

## Contributing

If you want to help out, see [CONTRIBUTING](CONTRIBUTING.md) for a set of guidelines.

## Compiling DucoV2 from source

## Build

### IMPORTANT

That build is from the master branch, which is used for active development and can be either unstable or incompatible with release software. Please compile release branches.

### Dependencies

#### We are strongly suggest to update cmake and boost to the latest available release.

##### [Cmake v3.17.3](https://github.com/Kitware/CMake/releases/download/v3.17.3/cmake-3.17.3.tar.gz)

##### [Boost](https://dl.bintray.com/boostorg/release/1.73.0/source/boost_1_73_0.tar.gz)

##### Ducov2 build been tested on Ubuntu Server 20.04 Focal Fosa with above releases as long with [gcc9.3](https://gcc.gnu.org/gcc-9/)

The following table summarizes the tools and libraries required to build. A
few of the libraries are also included in this repository (marked as
"Vendored"). By default, the build uses the library installed on the system,
and ignores the vendored sources. However, if no library is found installed on
the system, then the vendored source will be built and used. The vendored
sources are also used for statically-linked builds because distribution
packages often include only shared library binaries (`.so`) but not static
library archives (`.a`).

| Dep          | Min. version  | Vendored | Debian/Ubuntu pkg  | Arch pkg     | Fedora            | Optional | Purpose        |
| ------------ | ------------- | -------- | ------------------ | ------------ | ----------------- | -------- | -------------- |
| GCC          | 7.3.0         | NO       | `build-essential`  | `base-devel` | `gcc`             | NO       |                |
| CMake        | 3.12.0        | NO       | `cmake`            | `cmake`      | `cmake`           | NO       |                |
| pkg-config   | any           | NO       | `pkg-config`       | `base-devel` | `pkgconf`         | NO       |                |
| Boost        | 1.62          | NO       | `libboost-all-dev` | `boost`      | `boost-devel`     | NO       | C++ libraries  |
| OpenSSL      | 1.1.1         | NO       | `libssl-dev`       | `openssl`    | `openssl-devel`   | NO       | sha256 sum     |
| libsodium    | 1.0.16        | NO       | `libsodium-dev`    | ?            | `libsodium-devel` | NO       | Cryptography   |
| libunwind    | any           | NO       | `libunwind8-dev`   | `libunwind`  | `libunwind-devel` | YES      | Stack traces   |
| liblzma      | any           | NO       | `liblzma-dev`      | `xz`         | `xz-devel`        | YES      | For libunwind  |
| libreadline  | 6.3.0         | NO       | `libreadline6-dev` | `readline`   | `readline-devel`  | YES      | Input editing  |
| ldns         | 1.6.17        | NO       | `libldns-dev`      | `ldns`       | `ldns-devel`      | YES      | SSL toolkit    |
| expat        | 1.1           | NO       | `libexpat1-dev`    | `expat`      | `expat-devel`     | YES      | XML parsing    |
| GTest        | 1.5           | YES      | `libgtest-dev`[1]  | `gtest`      | `gtest-devel`     | YES      | Test suite     |
| Doxygen      | any           | NO       | `doxygen`          | `doxygen`    | `doxygen`         | YES      | Documentation  |
| Graphviz     | any           | NO       | `graphviz`         | `graphviz`   | `graphviz`        | YES      | Documentation  |
| HIDAPI       | ?             | NO       | `libhidapi-dev`    | ``           | ``                | NO       | for Device     |
| libusb-1.0   | 1.0           | NO       | `libusb-1.0-0-dev` | ``           | ``                | NO       |                |
| libudev      | ?             | NO       | `libudev-dev`      | ``           | ``                | NO       |                |
-------------------------------------------------------------------------------------------------------------------------------


[1] On Debian/Ubuntu `libgtest-dev` only includes sources and headers. You must
build the library binary manually. This can be done with the following command:

`sudo apt-get install libgtest-dev && cd /usr/src/gtest && sudo cmake . && sudo make && sudo mv libg* /usr/lib/`

Debian / Ubuntu one liner for all dependencies

`$ sudo apt update && sudo apt install --yes git build-essential curl cmake pkg-config libboost-all-dev libssl-dev libsodium-dev libunwind8-dev liblzma-dev libreadline8-dev libldns-dev libexpat1-dev doxygen graphviz libudev-dev libusb-1.0-0-dev libhidapi-dev xsltproc gperf autoconf automake libtool-bin`

Install all dependencies at once on OSX:

`$ brew update && brew bundle --file=contrib/apple/brew`

### Cloning the repository

Clone recursively to pull-in needed submodule(s):

`$ git clone https://github.com/ducov2-network/DucoV2 ducov2`

If you already have a repo cloned, initialize and update:

`$ cd ducov2 && git checkout release-v0.1.1`
`$ git submodule init && git submodule update`

### Build instructions

Ducov2 uses the CMake build system and a top-level [Makefile](Makefile) that
invokes cmake commands as needed.

#### On Linux and OS X

* Install the dependencies

* Change to the root of the source code directory and build:

	`$ cd ducov2 && make release`

	*Optional*: If your machine has several cores and enough memory, enable parallel build by running `make -j<number of threads>` instead of `make`. For this to be worthwhile, the machine should have one core and about 2GB of RAM available per thread.

* The resulting executables can be found in `build/release/bin`

* Add `PATH="$PATH:$HOME/ducov2/build/release/bin"` to `.profile`

* Run ducov2 with `ducov2d --detach`

* **Optional**: build and run the test suite to verify the binaries:

	`$ make release-test`

    *NOTE*: `core_tests` test may take a few hours to complete.

* **Optional**: to build binaries suitable for debugging:

	`$ make debug`

* **Optional**: to build statically-linked binaries:

	`$ make release-static`

Dependencies need to be built with -fPIC. Static libraries usually aren't, so you may have to build them yourself with `-fPIC`. Refer to their documentation for how to build them.

* **Optional**: build documentation in `doc/html` (omit `HAVE_DOT=YES` if `graphviz` is not installed):

	HAVE_DOT=YES doxygen Doxyfile

#### On the Raspberry Pi

Tested on a Raspberry Pi Zero with a clean install of minimal Raspbian Stretch (2017-09-07 or later) from https://www.raspberrypi.org/downloads/raspbian/. If you are using Raspian Jessie, [please see note in the following section](#note-for-raspbian-jessie-users).

* `$ apt-get update && apt-get upgrade` to install all of the latest software

* Install the dependencies for DucoV2 from the 'Debian' column in the table above.

* Increase the system swap size:

	`$ sudo /etc/init.d/dphys-swapfile stop`
	`$ sudo nano /etc/dphys-swapfile`
	`$ CONF_SWAPSIZE=1024`
	`$sudo /etc/init.d/dphys-swapfile start`

* Clone ducov2 and checkout most recent release version:

	`$ git clone https://github.com/ducov2-network/DucoV2.git`
	`$ cd ducov2`

* Build:

	`$ make release`

* Wait 4-6 hours

* The resulting executables can be found in `build/release/bin`

* Add `PATH="$PATH:$HOME/ducov2/build/release/bin"` to `.profile`

* Run ducov2 with `ducov2d --detach`

* You may wish to reduce the size of the swap file after the build has finished, and delete the boost directory from your home directory

#### *Note for Raspbian Jessie users:*

If you are using the older Raspbian Jessie image, compiling ducov2 is a bit more complicated. The version of Boost available in the Debian Jessie repositories is too old to use with ducov2, and thus you must compile a newer version yourself. The following explains the extra steps, and has been tested on a Raspberry Pi 2 with a clean install of minimal Raspbian Jessie.

* As before, `$ apt-get update && apt-get upgrade` to install all of the latest software, and increase the system swap size

	`$ sudo /etc/init.d/dphys-swapfile stop`
	`$ sudo nano /etc/dphys-swapfile`
	`$ CONF_SWAPSIZE=1024`
	`$ sudo /etc/init.d/dphys-swapfile start`

* Then, install the dependencies for ducov2 except `libunwind` and `libboost-all-dev`

* Install the latest version of boost (this may first require invoking `$ apt-get remove --purge libboost*` to remove a previous version if you're not using a clean install):

	`$ cd`
	`$ wget https://sourceforge.net/projects/boost/files/boost/1.68.0/boost_1_68_0.tar.bz2`
	`$ tar xvfo boost_1_68_0.tar.bz2`
	`$ cd boost_1_68_0`
	`$ ./bootstrap.sh`
	`$ sudo ./b2`

* Wait ~8 hours

	`$ sudo ./bjam install`

* Wait ~4 hours

* From here, follow the [general Raspberry Pi instructions](#on-the-raspberry-pi) from the "Clone ducov2 and checkout most recent release version" step.

#### On Windows:

Binaries for Windows are built on Windows using the MinGW toolchain within
[MSYS2 environment](http://msys2.github.io). The MSYS2 environment emulates a
POSIX system. The toolchain runs within the environment and *cross-compiles*
binaries that can run outside of the environment as a regular Windows
application.

**Preparing the build environment**

1. Download and install the [MSYS2 installer](http://msys2.github.io).

2. Open the MSYS shell via the `MSYS2 MSYS` shortcut at Menu Start

3. Update packages using pacman:

	`$ pacman -Syu`

4. Exit the MSYS shell using Alt+F4 or by clicking X at top-right corner. It is Very Important to do not exit to shell!!.

5. Start `MSYS2 MINGW64` from Menu Start

6. Update packages again using pacman:

	`$ pacman -Syu`

7. Install dependencies:

    To build for 64-bit Windows:

    `$ pacman -S git mingw-w64-x86_64-toolchain make mingw-w64-x86_64-cmake mingw-w64-x86_64-boost mingw-w64-x86_64-openssl mingw-w64-x86_64-libsodium mingw-w64-x86_64-hidapi automake autoconf binutils patch`

**Building**

* Download ducov2 with command:

	`$ git clone https://github.com/ducov2-network/DucoV2.git`

* Change branch to last Release:

	`$ cd ducov2 && git checkout release-v0.1.1`

* Activate and update submodules:

  `$ git submodule init && git submodule update`

* If you are on a 64-bit system, run:

  `$ USE_SINGLE_BUILDDIR=1 make release-static-win`

* The resulting executables can be found in `build/release/bin`

* **Optional**: to build Windows binaries suitable for debugging on a 64-bit system, run:

  `$ make debug-static-win`

* The resulting executables can be found in `build/debug/bin`

*** ducov2 does Not support 32-bit Windows anymore ***

### On FreeBSD:

The project can be built from scratch by following instructions for Linux above. If you are running ducov2 in a jail you need to add the flag: `allow.sysvipc=1` to your jail configuration, otherwise lmdb will throw the error message: `Failed to open lmdb environment: Function not implemented`.

We expect to add ducov2 into the ports tree in the near future, which will aid in managing installations using ports or packages.

### On OpenBSD:

#### OpenBSD < 6.2

This has been tested on OpenBSD 5.8.

You will need to add a few packages to your system. `pkg_add db cmake gcc gcc-libs g++ miniupnpc gtest`.

The doxygen and graphviz packages are optional and require the xbase set.

The Boost package has a bug that will prevent librpc.a from building correctly. In order to fix this, you will have to Build boost yourself from scratch. Follow the directions here (under "Building Boost"):
https://github.com/bitcoin/bitcoin/blob/master/doc/build-openbsd.md

You will have to add the serialization, date_time, and regex modules to Boost when building as they are needed by ducov2.

To build: `$ env CC=egcc CXX=eg++ CPP=ecpp DEVELOPER_LOCAL_TOOLS=1 BOOST_ROOT=/path/to/the/boost/you/built make release-static-64`

#### OpenBSD >= 6.2

You will need to add a few packages to your system. `$ pkg_add cmake miniupnpc zeromq libiconv`.

The doxygen and graphviz packages are optional and require the xbase set.


Build the Boost library using clang. This guide is derived from: https://github.com/bitcoin/bitcoin/blob/master/doc/build-openbsd.md

We assume you are compiling with a non-root user and you have `doas` enabled.

Note: do not use the boost package provided by OpenBSD, as we are installing boost to `/usr/local`.

### Create boost building directory
`$ mkdir ~/boost`
`$ cd ~/boost`

### Fetch boost source
`$ ftp -o boost_1_64_0.tar.bz2 https://netcologne.dl.sourceforge.net/project/boost/boost/1.64.0/boost_1_64_0.tar.bz2`

### MUST output: (SHA256) boost_1_64_0.tar.bz2: OK
`$ echo "7bcc5caace97baa948931d712ea5f37038dbb1c5d89b43ad4def4ed7cb683332 boost_1_64_0.tar.bz2" | sha256 -c`
`$ tar xfj boost_1_64_0.tar.bz2`

### Fetch and apply boost patches, required for OpenBSD
`$ ftp -o boost_test_impl_execution_monitor_ipp.patch https://raw.githubusercontent.com/openbsd/ports/bee9e6df517077a7269ff0dfd57995f5c6a10379/devel/boost/patches/patch-boost_test_impl_execution_monitor_ipp`
`$ ftp -o boost_config_platform_bsd_hpp.patch https://raw.githubusercontent.com/openbsd/ports/90658284fb786f5a60dd9d6e8d14500c167bdaa0/devel/boost/patches/patch-boost_config_platform_bsd_hpp`

### MUST output: (SHA256) boost_config_platform_bsd_hpp.patch: OK
`$ echo "1f5e59d1154f16ee1e0cc169395f30d5e7d22a5bd9f86358f738b0ccaea5e51d boost_config_platform_bsd_hpp.patch" | sha256 -c`
### MUST output: (SHA256) boost_test_impl_execution_monitor_ipp.patch: OK
`$ echo "30cec182a1437d40c3e0bd9a866ab5ddc1400a56185b7e671bb3782634ed0206 boost_test_impl_execution_monitor_ipp.patch" | sha256 -c`

`$ cd boost_1_64_0`
`$ patch -p0 < ../boost_test_impl_execution_monitor_ipp.patch`
`$ patch -p0 < ../boost_config_platform_bsd_hpp.patch`

### Start building boost
`$ echo 'using clang : : c++ : <cxxflags>"-fvisibility=hidden -fPIC" <linkflags>"" <archiver>"ar" <striper>"strip"  <ranlib>"ranlib" <rc>"" : ;' > user-config.jam`
`$ ./bootstrap.sh --without-icu --with-libraries=chrono,filesystem,program_options,system,thread,test,date_time,regex,serialization,locale --with-toolset=clang`
`$ ./b2 toolset=clang cxxflags="-stdlib=libc++" linkflags="-stdlib=libc++" -sICONV_PATH=/usr/local
$ doas ./b2 -d0 runtime-link=shared threadapi=pthread threading=multi link=static variant=release --layout=tagged --build-type=complete --user-config=user-config.jam -sNO_BZIP2=1 -sICONV_PATH=/usr/local --prefix=/usr/local install
`

### On Solaris:

The default Solaris linker can't be used, you have to install GNU ld, then run cmake manually with the path to your copy of GNU ld:

`$ mkdir -p build/release`
`$ cd build/release`
`$ cmake -DCMAKE_LINKER=/path/to/ld -D CMAKE_BUILD_TYPE=Release ../..`
`$ cd ../..`
`$ make`

### On Linux for Android (using docker):

### Build image
`docker build -f utils/build_scripts/android32.Dockerfile -t ducov2-android .`
### Create container
`docker create -it --name ducov2-android ducov2-android bash`
### Get binaries
`docker cp ducov2-android:/opt/android/ducov2/build/release/bin .`

### Building portable statically linked binaries

By default, in either dynamically or statically linked builds, binaries target the specific host processor on which the build happens and are not portable to other processors. Portable binaries can be built using the following targets:

* `make release-static-linux-x86_64` builds binaries on Linux on x86_64 portable across POSIX systems on x86_64 processors
* `make release-static-linux-armv8` builds binaries on Linux portable across POSIX systems on armv8 processors
* `make release-static-linux-armv7` builds binaries on Linux portable across POSIX systems on armv7 processors
* `make release-static-linux-armv6` builds binaries on Linux portable across POSIX systems on armv6 processors
* `make release-static-win` builds binaries on 64-bit Windows portable across 64-bit Windows systems

### Cross Compiling

You can also cross-compile ducov2 static binaries on Linux for Windows and macOS with the `depends` system.

* `make depends target=x86_64-linux-gnu` for 64-bit linux binaries.
* `make depends target=x86_64-w64-mingw32` for 64-bit windows binaries. Requires: python3 g++-mingw-w64-x86-64 wine1.6 bc
* `make depends target=x86_64-apple-darwin19.2.0` for macOS binaries. Requires: cmake imagemagick libcap-dev librsvg2-bin libz-dev libbz2-dev libtiff-tools curl bsdmainutils python3-setuptools
* `make depends target=arm-linux-gnueabihf` for armv7 binaries. Requires: g++-arm-linux-gnueabihf
* `make depends target=aarch64-linux-gnu` for armv8 binaries. Requires: g++-aarch64-linux-gnu

*** For `x86_64-apple-darwin19.2.0` you need to download SDK first ***        

The required packages are the names for each toolchain on apt. Depending on your OS Distribution, they may have different names.

Using `depends` might also be easier to compile ducov2 on Windows than using MSYS. Activate Windows Subsystem for Linux (WSL) with a distribution (for example Ubuntu), install the apt build-essentials and follow the `depends` steps as stated above.

### Compability with older Linux Versions < GLIBC_2.25

* `make depends-compat target=x86_64-linux-gnu` for 64-bit linux binaries.


## Running ducov2d

The build places the binary in `bin/` sub-directory within the build directory
from which cmake was invoked (repository root by default). To run in
foreground:

`$ ./bin/ducov2d`

To list all available options, run `./bin/ducov2d --help`.  Options can be
specified either on the command line or in a configuration file passed by the
`--config-file` argument.  To specify an option in the configuration file, add
a line with the syntax `argumentname=value`, where `argumentname` is the name
of the argument without the leading dashes, for example `log-level=1`.

To run in background:

`$ ./bin/ducov2d --log-file ducov2d.log --detach`

To run as a systemd service, copy
[ducov2d.service](utils/systemd/ducov2d.service) to `/etc/systemd/system/` and
[ducov2d.conf](utils/conf/ducov2d.conf) to `/etc/`. The [example
service](utils/systemd/ducov2d.service) assumes that the user `ducov2` exists
and its home is the data directory specified in the [example
config](utils/conf/ducov2d.conf).

If you're on Mac, you may need to add the `--max-concurrency 1` option to
ducov2-wallet-cli, and possibly ducov2d, if you get crashes refreshing.

## Internationalization

See [README.i18n.md](README.i18n.md).

## Using Tor

> There is a new, still experimental, [integration with Tor](ANONYMITY_NETWORKS.md). The
> feature allows connecting over IPv4 and Tor simultaneously - IPv4 is used for
> relaying blocks and relaying transactions received by peers whereas Tor is
> used solely for relaying transactions received over local RPC. This provides
> privacy and better protection against surrounding node (sybil) attacks.

While ducov2 isn't made to integrate with Tor, it can be used wrapped with torsocks, by
setting the following configuration parameters and environment variables:

* `--p2p-bind-ip 127.0.0.1` on the command line or `p2p-bind-ip=127.0.0.1` in
  ducov2d.conf to disable listening for connections on external interfaces.
* `--no-igd` on the command line or `no-igd=1` in ducov2d.conf to disable IGD
  (UPnP port forwarding negotiation), which is pointless with Tor.
* `DNS_PUBLIC=tcp` or `DNS_PUBLIC=tcp://x.x.x.x` where x.x.x.x is the IP of the
  desired DNS server, for DNS requests to go over TCP, so that they are routed
  through Tor. When IP is not specified, ducov2d uses the default list of
  servers defined in [src/common/dns_utils.cpp](src/common/dns_utils.cpp).
* `TORSOCKS_ALLOW_INBOUND=1` to tell torsocks to allow ducov2d to bind to interfaces
   to accept connections from the wallet. On some Linux systems, torsocks
   allows binding to localhost by default, so setting this variable is only
   necessary to allow binding to local LAN/VPN interfaces to allow wallets to
   connect from remote hosts. On other systems, it may be needed for local wallets
   as well.
* Do NOT pass `--detach` when running through torsocks with systemd, (see
  [utils/systemd/ducov2d.service](utils/systemd/ducov2d.service) for details).
* If you use the wallet with a Tor daemon via the loopback IP (eg, 127.0.0.1:9050),
  then use `--untrusted-daemon` unless it is your own hidden service.

Example command line to start ducov2d through Tor:

`DNS_PUBLIC=tcp torsocks ducov2d --p2p-bind-ip 127.0.0.1 --no-igd`

### Using Tor on Tails

TAILS ships with a very restrictive set of firewall rules. Therefore, you need
to add a rule to allow this connection too, in addition to telling torsocks to
allow inbound connections. Full example:

`$ sudo iptables -I OUTPUT 2 -p tcp -d 127.0.0.1 -m tcp --dport 13372 -j ACCEPT`
`$ DNS_PUBLIC=tcp torsocks ./ducov2d --p2p-bind-ip 127.0.0.1 --no-igd --rpc-bind-ip 127.0.0.1 \
        --data-dir /home/amnesia/Persistent/your/directory/to/the/blockchain`
## Debugging

This section contains general instructions for debugging failed installs or problems encountered with ducov2. First ensure you are running the latest version built from the Github repository.

### Obtaining stack traces and core dumps on Unix systems

We generally use the tool `gdb` (GNU debugger) to provide stack trace functionality, and `ulimit` to provide core dumps in builds which crash or segfault.

* To use gdb in order to obtain a stack trace for a build that has stalled:

Run the build.

Once it stalls, enter the following command:

`$ gdb /path/to/ducov2d `pidof ducov2d``

Type `thread apply all bt` within gdb in order to obtain the stack trace

* If however the core dumps or segfaults:

Enter `ulimit -c unlimited` on the command line to enable unlimited filesizes for core dumps

Enter `echo core | sudo tee /proc/sys/kernel/core_pattern` to stop cores from being hijacked by other tools

Run the build.

When it terminates with an output along the lines of "Segmentation fault (core dumped)", there should be a core dump file in the same directory as ducov2d. It may be named just `core`, or `core.xxxx` with numbers appended.

You can now analyse this core dump with `gdb` as follows:

`$ gdb /path/to/ducov2d /path/to/dumpfile`

Print the stack trace with `bt`

* To run ducov2 within gdb:

Type `$gdb /path/to/ducov2d`

Pass command-line options with `--args` followed by the relevant arguments

Type `run` to run ducov2d

### Analysing memory corruption

We use the tool `valgrind` for this.

Run with `valgrind /path/to/ducov2d`. It will be slow.

### LMDB

Instructions for debugging suspected blockchain corruption as per @HYC

There is an `mdb_stat` command in the LMDB source that can print statistics about the database but it's not routinely built. This can be built with the following command:

`$ cd ~/ducov2/external/liblmdb && make`

The output of `mdb_stat -ea <path to blockchain dir>` will indicate inconsistencies in the blocks, block_heights and block_info table.

The output of `mdb_dump -s blocks <path to blockchain dir>` and `mdb_dump -s block_info <path to blockchain dir>` is useful for indicating whether blocks and block_info contain the same keys.

These records are dumped as hex data, where the first line is the key and the second line is the data.

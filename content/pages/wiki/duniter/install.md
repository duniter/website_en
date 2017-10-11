Title: Install a Duniter node
Order: 9
Date: 2017-06-19
Slug: install
Authors: cgeek

This document is a little guide to install & deploy your own Duniter instance to either:

* Participate writing the blockchain (you need to be a member)
* Have a mirroring node

## Summary

* [Desktop](#desktop)
  * [GNU/Linux](#gnulinux)
    * [Ubuntu 64 bits](#ubuntu-64-bits)
    * [Debian 64 bits](#debian-64-bits)
    * [Other distribution](#other-distribution)
  * [Windows](#windows)
  * [MacOS](#macos)
* [Server](#server)
  * [GNU/Linux](#gnulinux_1)
    * [Ubuntu/Debian package (64 bits)](#ubuntudebian-package-64-bits)
    * [YunoHost](#yunohost)
    * [Automated install script](#automated-install-script)
    - [Other distributions (64 bits)](#other-distributions-64-bits)
    * [Docker](#docker)
  * [Windows](#windows_1)

----

# Desktop

A desktop machine will make it easier for you to manage your Duniter instance thanks to a graphical interface.

Your instance will be up as long as you keep your computer and Duniter software on. If you close your software or shut down your computer, Duniter will be able to resync with the network when you restart it.

> Once you are done with the installation, you can follow [the desktop user's guide](https://forum.duniter.org/t/duniter-desktop-guide/902) to understand how to use Duniter.

## GNU/Linux
### Ubuntu 64 bits

1. Go to the [releases page](https://github.com/duniter/duniter/releases) and choose the latest build. You have to download the file with `.deb` extension.
  <br>
  <img src="../../../images/wiki/duniter/install/ubuntu_file.png" width="500" height="106">

2. Process the installation by a double-click on the downloaded `.deb` file (or with `dpkg` software if you prefer to use it).

3. Use Ubuntu Dash to look for "Duniter" and click on it to launch the software:
  <img src="../../../images/wiki/duniter/install/ubuntu_dash.png" width="536" height="246">

### Debian 64 bits

1. Go to the [releases page](https://github.com/duniter/duniter/releases) and choose the latest build. You have to download the file with `.deb` extension.

2. Process the installation by opening the file with `GDebi` (or with `dpkg` software if you prefer to use it).
  <img src="../../../images/wiki/duniter/install/deb_gdebi.png" width="460" height="202">

3. Use GNOME Shell to look for "Duniter" and click on it to launch the software.
  <img src="../../../images/wiki/duniter/install/deb_gnome.png" width="690" height="428">

> At any moment you could also use `duniter-desktop` command to launch Duniter. It is an equivalent.

### Other distribution
#### With tarball archive

1. Go to the [releases page](https://github.com/duniter/duniter/releases) and choose the latest build. Download the file with `.tar.gz` extension.

2. Extract the tarball: `tar zxvf duniter-*.tar.gz`.

3. Run it with `./nw/nw`.

## Windows

1. Go to the [releases page](https://github.com/duniter/duniter/releases) and choose the latest build. You have to download the file with `.exe` extension.

2. Process the installation by a double-click on the downloaded `.exe` file.
  <img src="../../../images/wiki/duniter/install/win_fichier.png" width="591" height="39">
  > It may occur that the downloaded file misses the `.exe` extension. This is a Windows protection. You have to circumvent it by renaming the file and add `.exe` to the end of the name to be able to execute it.

3. Follow the installation procedure. You basically just need to accept the licence and click "Next" on each step.
  <br>
  <img src="../../../images/wiki/duniter/install/win_install.png" width="503" height="387">

4. Duniter is now installed, by default it will be launched at the end of the installation. You can launch it in the Windows menus "Start > Programs > Duniter > Duniter".
  <br>
  <img src="../../../images/wiki/duniter/install/win_programme.png" width="271" height="58">

## MacOS

It does not exist a Mac version. However, you could still compile the Server version like below.

# Server

For the most advanced users, a server install allows you to have a node up 100% of the time since a server is made to run forever.

You will control your instance using *command line tools*, but if you want you could also access the graphical interface using a web browser. Note how this is an even more advanced usage and requires security skills for not opening an admin access to your node.

> Once you are done with the installation, you can follow [the command line user's guide](../commands).

## GNU/Linux
### Ubuntu/Debian package (64 bits)

1. Go to the [releases page](https://github.com/duniter/duniter/releases) and choose the latest build. You have to download the file with `.deb` extension.

2. Process the installation by launching `dpkg -i` on the downloaded file. This requires root credentials.

```bash
dpkg -i [downloaded_file_name].deb
```

3. Launch the daemon with:
```bash
duniter start
```
If you want to launch the node with the administration web interface:
```bash
duniter webstart
```

### YunoHost

A [YunoHost package](https://github.com/duniter/duniter_ynh) is available.

### Manual compilation

Duniter can be compiled on the majority of Linux machines (32 bits or 64 bits) in just a few steps:

1. Install [Node.js version 6 or above](https://nodejs.org) + [Yarn](https://yarnpkg.com/lang/en/docs/install/)

2. Go to the [latest release page](https://github.com/duniter/duniter/releases/latest) and download the `Source code (tar.gz)` file.

3. Start the installation from the uncompressed folder `duniter/` :
  > N.B. : **do not launch these commands as `root`.** [This won't work, we know it](https://github.com/duniter/duniter/issues/412).

        cd duniter
        yarn
        
4. Use [the Duniter commands](./commands) by prefixing `duniter` with `bin/`. Example: 

        bin/duniter --version

### Docker

Unavailable.

## Windows

Their is no difference with the [Windows Desktop](#windows) installation. A server usage with Windows is just a never shut down desktop for Duniter.

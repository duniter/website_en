Title: Install a Duniter node
Order: 9
Date: 2017-06-19
Slug: install
Authors: cgeek

This document is a little guide to install & deploy your own Duniter instance to either:

* Participate writing the blockchain (you need to be a member)
* Have a mirroring node

## Table of content

* [Desktop or server](#desktop-or-server)
    * [Desktop version](#desktop-version)
    * [Server version](#server-version)
* [GNU/Linux](#gnulinux)
    * [Ubuntu/Debian 64 bits](#ubuntudebian-64-bits)
    * [Gentoo 64 bits](#gentoo-64-bits)
    * [YunoHost](#yunohost)
    * [Other distributions](#other-distributions)
    * [Docker](#docker)
    * [Manual building](#manual-building)
    * [Automatic startup](#automatic-startup)
* [Windows](#windows)
* [MacOS](#macos)

----

# Desktop or server

There are two versions of Duniter. Choose the wich most fits your needs.

## Desktop version

A desktop machine will make it easier for you to manage your Duniter instance thanks to a graphical interface.

Your instance will be up as long as you keep your computer and Duniter software on. If you close your software or shut down your computer, Duniter will be able to resync with the network when you restart it.

## Server version

For the most advanced users, a _server_ install allows you to have a node up 100% of the time since a server is made to run forever.

You will control your instance using command line tools, but if you want you could also access the graphical interface using a web browser.

> Once you are done with the installation, you can follow [the command line user's guide](../commands).

# GNU/Linux

## Ubuntu/Debian 64 bits

### Download package

Go to the [release page](https://git.duniter.org/nodes/typescript/duniter/wikis/Releases) to get a link to the last stable release.

Choose the file you need:

* Files for Ubuntu and Debian are terminated by the `.deb` extension.
* Choose either the file which name is containing `desktop` or `server` for respectively _desktop_ or _server_ version.
* Choose the file matching your architecture. If you don't know what it is, you probably need version x64.

  <img src="../../../images/wiki/duniter/install/ubuntu_file.png" width="500" height="106">

### Install Duniter

In order to process installation:

* If you are using Ubuntu, double-click on the downloaded file.
* If you are using Debian, open the downloaded file with `GDebi` option:
  <br>
  <img src="../../../images/wiki/duniter/install/deb_gdebi.png" width="460" height="202">

> Note: you can also use the `dpkg` command line to install the package. Example:

    sudo dpkg -i duniter-*-linux-x64.deb

### Start application

In order to start the _desktop_ version:

* With Ubuntu, use _Dash_ to look for _Duniter_ and click on it to launch the software:
  <br>
  <img src="../../../images/wiki/duniter/install/ubuntu_dash.png" width="536" height="246">
* With Debian, use _GNOME Shell_ to look for _Duniter_ and click on it to launch the software:
  <br>
  <img src="../../../images/wiki/duniter/install/deb_gnome.png" width="690" height="428">

> Note: it is also possible to start _bureau_ version with the `duniter-desktop` command. Using the command or the GUI is equivalent.

To launch the daemon (_server_ version):

    duniter start

> You can follow [the command line user's guide](../commands) in order to use your server node.

The _server_ version node for Ubuntu/Debian is usable with [automatic startup](#automatic-startup) (_Systemd_).

## Gentoo 64 bits

In order to install Duniter on Gentoo, there is a package in the overlay [sveyret-overlay](https://github.com/sveyret/sveyret-overlay). A _README_ file can be found in this overlay to help you and add it to the _Portage_ tree.

You will then be able to install the package `net-p2p/duniter`:

    emerge -av net-p2p/duniter

The following _USE flags_ allow you to decide what will be built:

| Flag | Description |
|------|-------------|
| `desktop` | Build and install the _desktop_ version instead of the _server_ one |
| `gui` | Add the GUI (mandatory for _desktop_ version, add the web interface for _server_ version) |

The _server_ version node for Gentoo can also be [automatically started](#automatic-startup).

## YunoHost

A [YunoHost package](https://github.com/duniter/duniter_ynh) is available (_server_ version only).

## Other distributions

For other distributions, there is a binary file containing the _desktop_ version.

1. Go to the [release page](https://git.duniter.org/nodes/typescript/duniter/wikis/Releases) to get a link to the last stable release and download the `duniter-desktop` file with `.tar.gz` extension.

2. Extract the tarball: `tar zxvf duniter-*.tar.gz`.

3. **Go to the extracted directory** and run Duniter with `./nw`.

## Docker

> Note: Docker must be installed on your computer in order to create a Duniter container.

> Note: only the Duniter _server_ version exists on a Docker image.

To get the image of the last version:

    docker pull duniter/duniter-ts

It is then possible to create the container with:

    docker run -d -p127.0.0.1:9220:9220 -p10901:10901 -p20901:20901 --name duniter duniter/duniter-ts

Without any other option, the container will automatically execute `duniter direct_webstart`. The `-d` in the command line make the container being executed in the background (daemon). The `--name` option is used to give a unique name to the container, which will then be easier to use for the next commands. The `-p` options are used to connect in-container ports with the host ones:

* port 9220 is for the web UI; specifying the IP address 127.0.0.1 (localhost) will prevent an external computer from accessing this node configuration.
* port 10901 is used for BMA access; exporting this port is then only necessary if you activate BMA.
* port 20901 is used for WS2P access.

> Note : do not use both daemon options for Duniter and Docker (for example: `docker run -d duniter/duniter-ts webstart`) or the container will immediately stop.

Once the node is started, it is accessable either using web UI, going to http://localhost:9220, either using command line:

    docker exec -it duniter duniter sync g1.duniter.fr 443

In the above command, the first `duniter` is the name given to the container at creation time, while the second one is the executed command.

You can stop and restart the container using standard Docker commands:

    docker stop duniter
    docker start duniter

### Using a keyfile

If the file `/etc/duniter/keys.yml` is found on the container, it is used as keyfile for the node identity. For this file is visible by Duniter, it must be granted appropriate access rights. If the file `keys.yml` is for example on the host in the `~/duniter/conf` directory, here are the commands to execute for it is used:

    chown -R 1111:1111 ~/duniter/conf
    chmod -R 644 ~/duniter/conf
    docker run -d -p127.0.0.1:9220:9220 -p10901:10901 -p20901:20901 --mount src=~/duniter/conf,dst=/etc/duniter --name duniter duniter/duniter-ts

> Note: some of the above commands need “root” access, usage of `sudo` may be required.

### Configuration external storage

By default, configuration and database are stored on the container. It is however possible to store them on the host computer. For this to be done, folder `/var/lib/duniter` must be shared with appropriate rights. For example, for the data to be recorded in the `~/duniter/data` directory, here are the commands to be executed:

    chown -R 1111:1111 ~/duniter/data
    docker run -d -p127.0.0.1:9220:9220 -p10901:10901 -p20901:20901 --mount src=~/duniter/data,dst=/var/lib/duniter --name duniter duniter/duniter-ts

> Note: some of the above commands need “root” access, usage of `sudo` may be required.

## Manual building

_Server_ version of Duniter can be compiled on the majority of Linux machines (32 bits or 64 bits) in just a few steps (first two should only be done once):

** Prerequisites **

At least, packages `git` and `build-essential` are required, you can install them by:

    sudo apt-get update && sudo apt-get install git build-essential

**1. Node.js install**

A tool can be used to install the wanted Node.js version and change as needed: its name is [nvm](https://github.com/creationix/nvm).

You may install nvm with:

    curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.4/install.sh | bash
    
You can then install Node.js:

    nvm install 8.9.1

> Note: for version older than Duniter 1.6, required Node.js version is 6.

**2. [Yarn](https://yarnpkg.com/) install**

Yarn may be installed by:

    curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
    echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
    sudo apt-get update && sudo apt-get install yarn

**3. Téléchargement de Duniter**

Go to the [release page](https://git.duniter.org/nodes/typescript/duniter/wikis/Releases) to get a link to the last stable release and download the `Source code (tar.gz)` file.

**4. Start the installation from the uncompressed folder `duniter/`:**

> Note: **do not launch these commands as `root`.** [This won't work, we know it](https://github.com/duniter/duniter/issues/412).

    cd duniter
    yarn

**5. Use [the Duniter commands](./commands)** by prefixing `duniter` with `bin/`. Example:

    bin/duniter --version

**6. Add web interface** (not added by default), to add `direct_webstart` et `webstart` commands:

    bin/duniter plug duniter-ui@1.6.x

> Note: for Duniter **1.5.9** ou below:

    bin/duniter plug duniter-ui@1.4.x
    sed -i "s/duniter\//..\/..\/..\/..\//g" node_modules/duniter-ui/server/controller/webmin.js

## Automatic startup

> Automatic startup is only available on _server_ versions.

Since version 1.6.15, automatic statup scripts are delivered for distribution based on _Systemd_ or _OpenRC_.

In order for the node to be automatically launched at computer startup, execute the following command with administrator rights (`sudo`):

* for _Systemd_:

        systemctl enable duniter.service

* for _OpenRC_:

        rc-update add duniter default

By default, the server will start as `duniter` user in the directory `/var/lib/duniter`.

You can customize the service behavior:

* for _Systemd_, using [drop-ins](https://coreos.com/os/docs/latest/using-systemd-drop-in-units.html) — for example, in order to start with web interface, you can create a file named `/etc/systemd/system/duniter.service.d/10-web.conf` with the following content:

        [Service]
        Environment="DUNITER_WEB=web"

* for _OpenRC_, by modifying the `/etc/conf.d/duniter` file.

Adjustable environment variables for this service are:

| Variable | Type | Description |
|----------|------|-------------|
| `DUNITER_WEB` | _Systemd_ | Must be empty for classical startup, or _web_ to start the web interface |
| `DUNITER_WEB` | _OpenRC_ | Start web interface if the value is defined an evaluate to true (`yes`, for example) |
| `DUNITER_HOME` | all | Server file location, default: `/var/lib/duniter/.config/duniter` |
| `DUNITER_DATA` | all | Name (location) of the database, default: `duniter_default` |
| `DUNITER_KEYS` | _OpenRC_ | If this variable is defined, it must indicate the location of a key file for node identity |
| `DUNITER_WEB_HOST` | _OpenRC_ | This variable allow to modify default host name for web interface |
| `DUNITER_WEB_PORT` | _OpenRC_ | This variable allow to modify default port for web interface |
| `DUNITER_GROUP` | _OpenRC_ | Name of the group with which node is executed, default: `duniter` |
| `DUNITER_USER` | _OpenRC_ | Name of the user with which node is executed, default: `duniter` |
| `DUNITER_OPTS` | _Systemd_ | Any other option to be given to command line at startup |
| `DUNITER_SSD_OPTIONS` | _OpenRC_ | Any other option to be given to `start-stop-daemon` command line |

> Note: up to version 1.6.17 (_Systemd_) or 1.6.22 (_OpenRC_), default value for `DUNITER_HOME` was `/var/lib/duniter`.

# Windows

A _desktop_ version is available for Windows.

1. Go to the [release page](https://git.duniter.org/nodes/typescript/duniter/wikis/Releases) to get a link to the last stable release. You have to download the file with `.exe` extension.

2. Process the installation by a double-click on the downloaded `.exe` file.
  <img src="../../../images/wiki/duniter/install/win_fichier.png" width="591" height="39">
  > It may occur that the downloaded file misses the `.exe` extension. This is a Windows protection. You have to circumvent it by renaming the file and add `.exe` to the end of the name to be able to execute it.

3. Follow the installation procedure. You basically just need to accept the licence and click "Next" on each step.
  <br>
  <img src="../../../images/wiki/duniter/install/win_install.png" width="503" height="387">

4. Duniter is now installed, by default it will be launched at the end of the installation. You can launch it in the Windows menus "Start > Programs > Duniter > Duniter".
  <br>
  <img src="../../../images/wiki/duniter/install/win_programme.png" width="271" height="58">

# MacOS

There is no specific MacOS version. However, you still can build the _server_ version.

Title: Duniter Commands
Order: 9
Date: 2017-04-08
Slug: commands
Authors: cgeek
Here is a guide to the different commands of the `duniter` command-line executable.

## Initialize its node

### `wizard key`

Lets you configure the cryptographic keychain used by your node. It is through this trousseau that your node can be identified and its answers authenticated, verified.

This keychain consists of a private key and a public key Ed25519.

    duniter wizard key
    ? Modify you keypair? Yes
    ? Key's salt *****************
    ? Key's password ********************

### `wizard network`

Allows you to configure your node's network connectivity: both local (network interface and machine port on which to connect) and distance (declaration of your node on how to contact it from the Internet).

    duniter wizard network
    ? IPv4 interface: eth0 192.168.1.667
    ? IPv6 interface: eth0 2a01: e35: 8ae7: 8bb0: 3de1: ee66: a6ba: a438 (Global)
    ? Port: 10900
    ? Remote IPv4: 88.174.120.187
    ? Remote port: 10900
    ? UPnP is available: use automatic port mapping? (Easier) Yes
    ? Does this server have a DNS name? Yes
    ? DNS name: cgeek.fr

Obviously, you must put your own values ​​here, and therefore do not put "192.168.1.667" or "2a01:e35:8ae7:8bb0:3de1:ee66:a6ba:a438" or "cgeek.fr".

### `sync`

For a new or deleted node (for example, following the use of `reset data`), it is necessary to initialize its node by synchronizing an existing blockchain. This operation will download the blockchain and then extract all the data of the currency: canvas of trust, existing currency units, transactions.

Synchronize its node with the network Ğ1 (Duniter currency):

    duniter sync g1.duniter.org 443
    Progress:

    download: [|||| ] 23%
    Apply: [] 0%

This command takes time. Be patient.

#### Option `--nointeractive`

Disables the display with progress bars in favor of a conventional control output.

    duniter sync g1.duniter.org 443
    2017-04-10T08: 31: 42 + 02: 00 - info: Try with g1.duniter.org:10901 4aCqwi
    2017-04-10T08: 31: 42 + 02: 00 - info: Sync started.
    2017-04-10T08: 31: 42 + 02: 00 - info: Getting remote blockchain info ...
    2017-04-10T08: 31: 42 + 02: 00 - info: Connecting to g1.duniter.org ...
    2017-04-10T08: 31: 42 + 02: 00 - info: Peers ...

#### Option `--nopeers`

Disables P2P downloading and downloading of network node listing.

    duniter sync g1.duniter.org 443
    2017-04-10T08: 32: 26 + 02: 00 - info: Try with g1.duniter.org:10901 4aCqwi
    2017-04-10T08: 32: 26 + 02: 00 - info: Sync started.
    2017-04-10T08: 32: 26 + 02: 00 - info: Getting remote blockchain info ...
    2017-04-10T08: 32: 26 + 02: 00 - info: Connecting to g1.duniter.org ...
    2017-04-10T08: 32: 26 + 02: 00 - info: Downloading Blockchain ...
    2017-04-10T08: 32: 26 + 02: 00 - debug: dl starts from 0
    2017-04-10T08: 32: 26 + 02: 00 - info: Getting chunck # 36/36 from 9000 to 9023 on peer g1.duniter.org:10901
    2017-04-10T08: 32: 26 + 02: 00 - info: GOT chunck # 36/36 from 9000 to 9023 on peer g1.duniter.org:10901

#### Option `--onlypeers`

Retrieves only peer information, does not retrieve block information.

#### Option `--cautious`

Force the careful verification of the validity of each block in relation to the rules of the protocol.

    duniter sync g1.duniter.org 443 --cautious

#### Option `--memory`

Perform synchronization in memory only. Synchronization will not be stored on the hard disk. This option is useful for a quick blockchain integrity check when combined with the `--cautious` option.

    duniter sync g1.duniter.org 443 --cautious --memory

## Start / Stop its node

A Duniter node usually runs in the background. Duniter provided several commands in order to be started / stopped in disputes operating modes.

### `start`

Starts the Duniter node * without GUI *, in the background. The only way to communicate with the node as an administrator is to see its logs with `duniter logs`.

    duniter start
    Starting duniter_default daemon ...
    duniter_default daemon started. PID: 1328

### `stop`

Stop a Duniter knot that would turn in the background. If no node is running, the command does nothing.

    duniter stop
    Stopping duniter_default daemon ...
    duniter_default daemon stopped.

### `status`

Says whether the node is currently running in the background or not.

    duniter status
    duniter is running using PID 1832.

### `restart`

Shortcut for `stop` followed by` start`. If no node was started, the command is equivalent to a simple `start`.

    duniter restart
    duniter_default daemon is not running
    Starting duniter_default daemon ...
    duniter_default daemon started. PID: 1913

### `webstart`

Starts the Duniter *node with GUI* in the background.

The node is then graphically accessible at [localhost:9220] (http://localhost:9220).

    duniter webstart
    Starting duniter_default daemon ...
    duniter_default daemon started. PID: 2878

#### Option `--webmhost`

It is possible to replace the interface `localhost` with the interface of your choice.

    duniter webstart --webmhost 192.168.1.35

The node is then accessible graphically at the address http://192.168.1.35:9220.

#### Option `--webmport`

You can replace the `9220` port with the port of your choice.

    duniter webstart --webmport 9330

The node can then be accessed graphically at http://localhost:9330.

### `webrestart`

Shortcut for `stop` followed by` webstart`. If no node was launched, the command is equivalent to a simple `webstart`.

The node is then graphically accessible at [localhost:9220] (http://localhost:9220).

    dunter webrestart
    Stopping duniter_default daemon ...
    duniter_default daemon stopped.
    Starting duniter_default daemon ...
    duniter_default daemon started. PID: 2938

## Administration
     
### `direct_start`

Starts the *live* node, without running in the background. The logs of the application will appear live in the console.

To stop the node, perform the `Ctrl^C` key combination.

    duniter direct_start
    2017-04-10T11: 12: 28 + 02: 00 - info: >> Server starting ...
    2017-04-10T11: 12: 28 + 02: 00 - info: Node version: 1.2.1
    2017-04-10T11: 12: 28 + 02: 00 - info: Node pubkey: 2ny7YAdmzReQxAayyJZsyVYwYhVyax2thKcGknmQy5nQ
     
#### Option `--keyprompt`

Requests secret identifiers at application startup that will generate the cryptographic keychain in memory. This keychain will then be used for the duration of the application and will disappear when it stops.

A useful option for not storing your keychain in a file.

    duniter direct_start --keyprompt
     
### `direct_webstart`

Same as `direct_start`, but starts with the loaded GUI.

    duniter direct_webstart

### `reset data`

Removes all *data* from the node: blockchain, identities, transactions, and so on. Does not delete the configuration.

    duniter reset data

### `reset all`

Removes all data and configuration from the node. Equivalent to having a new installation.

    duniter reset all

### `logs`

Displays the last log lines of Duniter and displays the new lines continuously.

    duniter logs
### `config`

Allows you to change one or more configuration values ​​by options.

    duniter config --option1 <value1> --option2 --option3 <value3>

Requires a restart of the node so that the new configuration is taken into account.

#### Option `--upnp`

Enables UPnP.

    duniter config --upnp

#### Option `--noupnp`

Disable UPnP.

    duniter config --noupnp

#### Option `--cpu <percentage>`

Sets the percentage of available CPU.

    duniter config --cpu 0.5

Configures CPU usage at 50%.

#### Option `--ipv4 <address>`

Configures the IPv4 network interface of the machine to which to talk.

    duniter config --ipv4 192.168.1.22

Configures listening on the network interface `192.168.1.22`.

#### Option `--ipv6 <address>`

Configures the IPv6 network interface of the machine to which to talk.

    duniter config --ipv6 "2a01:e35:8ae7:8bb0:2e0:4cff:feca:36"

Configures listening on the network interface to 2a01:e35:8ae7:8bb0:2e0:4cff:feca:36`.

#### Option `--port <number>`

Configures the port of the machine on which to interact for each interface (IPv4, IPv6).

    duniter config --port 10901

Configures listening on the `10901` machine port.

#### Option `--remote4 <address>`

Configures the remote IPv4 address of the machine.

    duniter config --ipv4 88.174.120.187

Configures the node to declare itself available at 88.174.120.187.

#### Option `--remote6 <address>`

Configures the remote IPv6 address of the machine.

    duniter config --ipv6 2a01:e35:8ae7:8bb0:2e0:4cff:feca:36

Configures the node to declare itself available at address `2a01:e35:8ae7:8bb0:2e0:4cff:feca:36`.

#### Option `--remotep <address>`

Configures the remote port of the machine.

    duniter config --remotep 10901

Configures the node to declare itself available on the `10901` port.

#### Option `--addep <specification>`

Declares a new unknown network interface interface from Duniter.

    duniter config --addep "ES_CORE_API g1.data.duniter.fr"

**Caution:** this command must be executed on a single node: all unknown interfaces must be declared on this node, at the risk of falling into an infinite loop of creation / deletion of interfaces.

#### Option `--remep <specification>`

Removes an unknown network contact interface from Duniter that was previously added.

    duniter config --remep "ES_CORE_API g1.data.duniter.fr"

**Caution:** this command must be executed on a single node: all unknown interfaces must be declared on this node, at the risk of falling into an infinite loop of creation / deletion of interfaces.

#### Option `--autoconf`

Regenerates the network configuration automatically and generates a random key pair if it does not exist.

    duniter config --autoconf

## Generate a block manually

### `gen-next`

Generates the next block from the pool data and the current block, performs the working proof for the requested difficulty and then submits the resulting block to a node.

    duniter gen-next g1.duniter.org 10901 74
    
This command generates the next block, sends it to node `g1.duniter.org: 10901` on port` 10901` and calculates the working proof with `74` trouble (footprint beginning with 4 zeros).

#### Option `--show`

Displays the calculated block * before * the proof of work and submission to the network. Controls its contents.

    duniter gen-next g1.duniter.org 10901 74 --show

#### Option `--check`

Modifies the behavior of the command: it no longer produces proof of work nor submits the block to the network. Instead, it generates the block and checks if it is acceptable by a node.

    duniter gen-next --show --check

### `gen-root`

Generates block #0 automatically, including a maximum number of members.

    Gen-root duniter.org 10901 74
    
### `gen-root-choose`

Generates block #0 by manually selecting members to include

    Gen-root duniter.org 10901 74
    ? Newcomers to add:
     ◯ john
     ◯ dude404
     ◉ sinogeek
    ❯◉ deviantime
     ◯ kernel
     ◯

## Transverse Options

These options, if used, must be *systematically* provided in future orders to maintain their application.

Because these options allow you to temporarily reset (the time of a command) a global variable of the application.

#### Option `--home`

Allows you to redefine the folder where the application data is stored. The default value for this option is `$HOME/.config/duniter/`

    duniter sync g1.duniter.org 10901 --home / tmp / duniter
    
This command will synchronize and store the result in the `/tmp/duniter/duniter_default` folder.

#### Option `--mdb`

Allows you to redefine the folder where the application data is stored. The default value for this option is `duniter_default`.

    duniter sync g1.duniter.org 10901 --mdb g-one
    
This command will synchronize and store the result in the `$HOME/.config/duniter/g-one` folder.

It is possible to combine the 2 options:

    duniter sync g1.duniter.org 10901 --home / tmp / duniter --mdb g-one
    
This command will synchronize and store the result in the `/tmp/duniter/g-one` folder.

#### Option `--keyfile`

Provides the cryptographic keychain via a YAML file.

    duniter start --keyfile /tmp/key.yml
    
With a `key.yml` file in the following format:

```Yaml
Pub: "EfJ5xHtwjxvF3Bq4GMeuKkKe5nmodQcqkvgVPZZT6gCF"
Sec: "2vyztEUMgSgcidmLPprbR5pPUUFbGnTG99mdEMPiiRD6wVAm76AvjDDp5PypzMsTvLKX8UrJ5sQbCUCmxTWRtr9d"
```

#### Options `--salt`,` --passwd`

These options allow you to use the cryptographic keychain resulting from the value of these two combined options.

    duniter start --salt abc --passwd def

#### Options `--keyN`,` --keyr`, `--keyp`

The use of `--salt` and` --passwd` presupposes other cryptographic parameters named 'N, r, p'. Their default value in Duniter is "4096,16,1".
 
The `--keyN`,` --keyr`, `--keyp` options allow you to redefine these values ​​precisely.

    duniter --salt abc --passwd def --keyN 4096 --keyr 16 --keyp 1

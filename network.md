# computer network

OSI model

- "Open Systems Interconnection" model
- a conceptual model that categorizes and standardizes the different functions in a network.
- created by the "International Organization for Standardization" (ISO)
- functions are divided into "7 layers"
- these layers work together to make the network work

OSI Model - Application Layer

- this layer is closest to the end user
- interacts with software applications, for example web browser
- http and https are layer 7 protocols
- identifying communication partners
- synchronizing communication

OSI model - Presentation Layer

- data in the application layer is in "application format"
- it needs to be "translated" to a different format to be sent over the network
- the presentation layer's job is to translate between application and network formats
- for example, encryption of data as it is sent, and decryption of data as it is received
- also translates between different application layer formats

OSI model - Session Layer

- controls dialogues (sessions) between communicating hosts
- establishes, manages and terminates connections between the local application (for example, your web browser) and the remote application

OSI model - Transport layer

- segments and reassembles data for communications between end hosts
- breaks large pieces of data into smaller segments which can be more easily sent over the network and are less likely to cause transmission problems if errors occur
- provide host-to-host communications
- data unit: segment = data + L4 header

OSI model - Network Layer

- provides connectivity between end hosts on different networks (ie outside of the LAN)
- provides logical addressing (IP addresses)
- provides path selection between source and destination
- routers operate at layer 3
- data unit: packet = data + l4 header + l3 header

OSI model - Data link layer

- provides node-to-node connectivity and data transfer (for example, PC to switch, switch to router, router to router)
- defines how data is formatted for transmission over a physical medium (for example, copper UTP cables)
- detects and (possibly) corrects Physical layer errors
- uses layer 2 addressing, separate from layer 3 addressing
- switches operate at layer 2
- data unit: frame = l2 trailer + data + l4 header + l3 header + l2 header

OSI model - physical layer

- defines physical characteristics of the medium used to transfer data between devices
- for example, voltage levels, maximum transmission distances, physical connectors, cable specifications, etc.
- digital bits are converted into electrical (for wired connections) or radio (for wireless connections) signals
- data unit: bits

TCP/IP Suite

- conceptual model and set of communications protocols used in the internet and other networks
- known as TCP/IP because those are 2 of the foundational protocols in the suite
- developed by the United States Department of Defense through DARPA (Defense Advanced Research Projects Agency)
- in use in modern networks

TCP/IP Suite layers

- Layer 4 Application
- Layer 3 Transport
- Layer 2 Internet
- Layer 1 Link

To connect to physical Cisco device use usb mini-b or rj45 cables

User exec mode

- user exec mode is very limited
- users can look at some things, but can't make any changed to the configuration
- also called user mode

something like this:
```
Router>
```

Privileged exec mode

to enable type first command
```
Router>enable
Router#
```

- provides complete access to view the device's configuration, restart the device, etc.
- cannot change the configuration, but can change the time on the device, save the configuration file, etc.

In both modes if user will type **?** in cli, it will show all available commands 

for exec mode user will get less commands than for privileged mode

to activate global configuration mode

if currently in user exec mode, type
```
router>enable
router#configure terminal
router(config)#
```
if user sees similar output, it means he is in global configuration mode

running-config / startup-config

- there are two separate configuration files kept on the device at once

Running-config = the current, active configuration file on the device. As you enter commands in the CLI, you edit the active configuration

Startup-config = the configuration file that will be loaded upon restart of the device

command
```
show running-config
```
displays the current, active configuration file

command
```
show startup-config
```
displays the saved configuration file which will be loaded if the device is restarted

command
```
write
```
saves the configuration

command
```
write memory
```
saves the configuration

command
```
copy running-config startup-config
```
saves the configuration
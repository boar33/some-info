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

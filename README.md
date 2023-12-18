# Our Network topology

![2022-03-13_23-56-21](https://user-images.githubusercontent.com/45165287/158082826-c762aa56-363c-455e-ad37-0b0e3ff6d149.png)


#### To create Network and Implement the SDN network approach
# Network Slicing: SDN Network Approach with Text-Based Chats 

## What is Network Slicing? 

Network slicing is a network architecture that creates multiple unique or independent logical and virtualized networks over a common multi-domain or physical network infrastructure. Network slices can span multiple network domains, including access, core, and transport, and be deployed across multiple operators. 

![image](https://user-images.githubusercontent.com/74248781/154529933-baba794b-e510-4e56-b052-37a2b0f22a39.png)



## Why are we using SDN in Network Slicing? 

NFV and SDN serve as a basis for network slicing by allowing both physical and virtual resources to be used to make certain services. In addition, SDN can be used to provide an overarching framework to help 5G to function across a control plane, determining the optimal route for traffic flows across the network. 

## Network Slicing using SDN 

SDN is a new architecture concept that aims to decouple the network control or traffic control and forwarding functions. This network enables the network to be intelligent and centrally controlled or programmed, 

SDN decouples the signaling and control (control layer) from user data (data or user layer). SDN deals with complex networks, improve scalability, low latency. SDN concepts are used in IoT (Internet of Things), cloud services. 

SDN controllers are used for protocol processing and controlling of the SDN switches via OpenFlow protocol. 



## SDN Architecture 

SDN architecture specifies how a networking and computing system can be developed utilising a mix of open, software-based technologies and commodity networking hardware.

![image](https://user-images.githubusercontent.com/45165287/154595067-d6ad153a-364f-4c0d-a6b6-c2cfd38266d5.png)
 

## Our Project Approach 

We are creating a network using OpenFlow control between the control layer and data layer on SDN architecture. In the data layer, 7 switches will be used to create the network topology, where 5 switches are OvS (Open Switch). And three switches will have 2 or the host's machine. And this network topology will be connected to the SDN controller via OpenFlow protocol. The SDN controller makes a connection with the Application layer. Thus, the data layer and Application layer in the Northbound interfaces will be connected through the SDN controller.  

## OpenFlow Protocol 

OpenFlow protocol is an important protocol in SDN architecture. It is used in Southbound interfaces. Flow tables are used in this protocol to handle the mechanisms of the flow of packets that come to the protocol. OpenFlow protocol supports multiple Flow tables. 

Open Flow Switch: The flow or group tables are used by OpenFlow switch to perform the packet matching and forwarding. Flow tables have many types of flow entries. OpenFlow channel establishes a c a connection between an OpenFlow switch and OpenFlow controller i.e., SDN controller. The controller maintains the switch using this protocol. Logically, OpenFlow switches are connected to each other via OpenFlow protocol. 

### Project Description
Objective:- The SDN approach used to network virtualization and containerization helps to optimise network resources and adapt networks quickly to changing applications and traffic. It creates a software-programmable infrastructure by separating the network's control and data planes.The OpenFlow Switch  environment built on the foundation of SDN must be involved. It supports a wide range of  protocol plugins as well as a wide range of services and applications.The implemented network must include multiple hosts and data centres that run on lxc containers, as well as physical network devices that support the OpenFlow protocol. Host machines must function as text-based chat clients, and the entire data centre must serve as a text-based chat server. Using the tunnelling mechanism with vxLan, each slice must communicate independently via chatting.

### Approach Followed
To implement this project, the approach has been described as follows. Firstly, an OpenFlow Switches has been developed to communicate within SDN  in a northbound interface which then enables it to communicate with Clients using OpenFlow version  protocol. Then the tunnelling mechanism using vxLan has been used. In this approach Four Open vSwitch (OVS) is used to build the core network and two other switches used for providing access to the data from one Client to other. The given figure: 5 Topology  for implementing this approach. 




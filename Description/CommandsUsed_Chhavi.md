$sudo apt install snapd

Install lxd

$sudo apt install lxd

Creating Containers

$ lxc launch ubuntu:20.4 c1
$ lxc launch ubuntu:20.4 c2

To go inside container

$lxc exec c2 bash

OVS Setup:-

To install OVS  

$sudo apt install openvswitch-support

Starting OVS
We need to start ovs service, to create virtual switches.

sudo ovs-ctl start

Creating OVS bridge

sudo ovs-vsctl add-br ovs0

To see ovs switch with the bridge in container

$sudo ovs-vsctl show

To Create a container networking bridge on each host

apt install bridge-utils
brctl addbr cont-mgmnt0 up
ip link set dev cont-mgmnt0 up

To Create virtual switches on hosts

apt-get install openvswitch-switch openvswitch-ipsec
ovs-vsctl add-br ovsbr0

For Virtual Machine1
Command to add link between c1 and switch1

sudo lxc config device add c1 eth1 nic nictype=bridged parent=switch1 name=eth1

Command to add link between c2 and switch1

sudo lxc config device add c2 eth1 nic nictype=bridged parent=switch1 name=eth1

COMMAND TO GIVE ip to c1 eth1:
sudo lxc exec lxc1 -- ip addr add 10.0.0.1/24 dev eth1

COMMAND TO GIVE ip to c2 eth1:
sudo lxc exec lxc1 -- ip addr add 10.0.0.1/24 dev eth1

COMMAND TO GIVE MAC TO ETH1 of  c1 ,c2
sudo lxc config set c1 volatile.eth1.hwaddr 00:00:00:00:00:01
sudo lxc config set c2 volatile.eth1.hwaddr 00:00:00:00:00:02

For Virtual machine2
Command to add link between c3 and switch1

sudo lxc config device add c3 eth2 nic nictype=bridged parent=switch1 name=eth2

Command to add link between c4 and switch4

sudo lxc config device add c4 eth2 nic nictype=bridged parent=switch1 name=eth2

COMMAND TO GIVE ip to c3 eth2:
sudo lxc exec c3 -- ip addr add 10.0.0.1/24 dev eth2

COMMAND TO GIVE ip to c4 eth2:
sudo lxc exec c4 -- ip addr add 10.0.0.1/24 dev eth2

COMMAND TO GIVE MAC TO ETH1 of  c3 ,c4
sudo lxc config set c3 volatile.eth1.hwaddr 00:00:00:00:00:03
sudo lxc config set c4 volatile.eth1.hwaddr 00:00:00:00:00:04

Command to check to which ethernet port of switch1 c1 is connection:

lxc config show c1










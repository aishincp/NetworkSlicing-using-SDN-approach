### version of myubuntu installed 
18.04

### To create the containers
$lxc launch ubuntu:16.04 container1

### For LXC initialization
$lxc init

### To check the list of lxc containers
$lxc list

### To check images in lxc
$lxc image list image:debian

### To show images of list
$lxc remote list

### For Bridge Configuration 
$root@ubuntu:/var/lib/lxc/ubuntu# brctl show

### To install Open vSwitch 
$ apt-get install openvswitch-switch

# Access-list-controls Project

This project demonstrates how to implement Access Control Lists (ACLs) 
on a segmented network using VLANs and Router-on-a-Stick.
## Network Structure
	•	VLAN 10 – Teachers
	•	VLAN 20 – Students
	•	VLAN 30 – Admin/IT

Each VLAN is assigned a subnet and connected to a router using subinterfaces.

## Switch Configuration
vlan 10
 name TEACHERS
vlan 20
 name STUDENTS
vlan 30
 name ADMIN

interface range f0/1 - 2
 switchport mode access
 switchport access vlan 10

interface range f0/3 - 6
 switchport mode access
 switchport access vlan 20

interface range f0/7 - 8
 switchport mode access
 switchport access vlan 30

interface f0/24
 switchport mode trunk

## ROUTER ON A STICK CONFIGURATION

interface gig0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

interface gig0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0

interface gig0/0.30
 encapsulation dot1Q 30
 ip address 192.168.30.1 255.255.255.0

 ## ACL CONFIGURATION IMAGE
 https://github.com/Martendo1/Access-list-controls-/blob/6509e7f4ead6af14d5c8df1d7aeabb0d556ae9d7/WhatsApp%20Image%202025-12-03%20at%2010.45.38_3c125a06.jpg?raw=true

 


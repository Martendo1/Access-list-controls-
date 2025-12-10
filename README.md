# Access-list-controls Project

This project demonstrates how to implement Access Control Lists (ACLs) 
on a segmented network using VLANs and Router-on-a-Stick.

# OVERVIEW
This project is about controlling who can access what inside a network using Cisko Packet Tracer
ACLs (Acess Control Lists)
My network includes 
. Teaches PCs
. Student PCs
. Admin PCs
. A router connecting the VLANS/Subnets
. A switch providing access to each VLAN

##NETWORK DESIGN

| NAME       | VLAN | SUBNET          | DEVICES                                | Gi/int         |
|-------------------|-----------------|----------------------------------------|----------------|
| Teachers          | 10   | 192.168.10.0/24 | PC0/PC1                                | Gig 0/0.10     |
| Student           | 20   | 192.168.20.0/24 | PC2, PC3, Laptop 0, Laptop 1           | Gig0/0.20      |
| Admin/IT          | 30   | 192.168.30.0/24 | PC4 (Admin pc), Server-<br>PT          | Gig0/0.30      |



| NAME      | VLAN   | SUBNET          | DEVICES                     | Gi/int |
|-----------|--------|-----------------|-----------------------------|
| Teachers  |10      | 192.168.10.0/24 | Pc0/Pc1                     | Gig 0/0.10
| Student   | 20     | 192.168.20.0/24 | Pc2, Pc3, Laptop 0,Laptop 1 | Gig0/0.20
| Admin/IT  | 30     | 192.168.30.0/24 | Pc4 (Admin pc),Server-<br>PT| Gig0/0.30

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
 ![Config](WhatsApp%20Image%202025-12-03%20at%2010.45.38_3c125a06.jpg)

 


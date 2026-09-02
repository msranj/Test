## Azure Day 2 and networking basics

Reference: https://drive.google.com/file/d/1kD2rtvtiZr8x4XIU6CDTZzfpphk976lE/view?usp=drive_link

Why was Always on introduced?
- do we need FCI (failover cluster instance): Yes
- FCI helps to failover from primary to secondary replicas.
- We can group a couple of databases in Always on AG.
- address all problems of Logshipping, Mirroring, Clusters.
- we can implement a combination of HA & DR.
- Shared storage is not required. (i.e. every replica will have its dedicated storage)
- supports automatic failover, offloading (backups & read operation)
- Multi-subnet (replicate databases to different regions)
- clusterless AG possible.
- Concept of LISTENER.
 


#### Note:
------
#### 1) how to find if the IP's given are part of Multi-subnet

for ex:

    192.168.1.3
    192.168.2.3

the above IP's are part of Multi-subnet.

#### Explanation:
------------
Every IP address (Ipv4) will have 4 Octets.

assume IP: abc.def.ghi.jkl

    here 
    1st Octet : abc
    2nd octet: def
    3rd octet: ghi
    4th octet: jkl


if only 3rd octet varies then the IP's are part of Multi-subnet.

#### 2) what are private IP's?
- it usually starts with 
    
        > 10.XX.XX.XX
    
        > 172.16.XX.XX
    
        > 192.168.XX.XX
	
#### 3) can we configure Multi-subnet between 2 different domains?
- 

#### 4) can we configure 
    > port 67038 for SQL instance?
    > port 200 for SQL instance?
- No

##### Port ranges:

    total = 67430 (2^32)

    Ranges from

    0 - 1023: Well know ports, cant use in apps
    1024 - 49151: Registered ports.
    49152 - 65536: Dynamic/ephimeral/private Ports (for Named instances we can use)

#### 5) using TCP IP protocol to understand how communication happens?

    Physical Layer: uses 0's and 1's as Devices understand only 0 & 1.

    MAC/Data : Machine/Devices addresses are in MAC addresses

    Network Layer: 

    Transport Layer: 

    Communication layer: uses PORTS.
    
#### Socket = IP + Port
























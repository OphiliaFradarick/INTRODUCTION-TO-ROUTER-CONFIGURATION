![image](https://github.com/user-attachments/assets/d7076331-d25b-4072-956d-58fa252b8c9e)
![image](https://github.com/user-attachments/assets/b8d7cb35-715d-418e-956b-ddef8130d85d)
![image](https://github.com/user-attachments/assets/050e10bd-7b08-431b-a0e0-f12351335cda)

## STATIC ROUTING PROTOCOLS
The static route information is entered from the router’s configure terminal prompt (config)#, using the ip route command, which has the following syntax:
Router(config)# ip route [destination] [subnet mask] [next hop]
 
Each static route can use a different subnet mask. This is accomplished using 
variable-length subnet masking (VLSM). For example, one static route could have 
subnet mask 255.255.255.0 and another could have subnet mask 255.255.255.252.

You can verify the routing address entry into the routing table by entering the 
command show ip route (sh ip route) from the router’s (config)# prompt

# Recursive Static Route
A recursive static route is used to identify a next hop router where packets will be sent on their path to the intended destination. A recursive static route requires two routing table lookups. First the router must check the routing table for the destination network, and then it will try to find an exit interface that points to the next hop router as configured

# Directly connected Static Route
A directly attached, or directly connected static route, uses the exit interface to forward traffic to the intended destination. This is in contrast to the recursive static route which used the next hop IP address of the router along the path to the destination. With a directly connected static route, the exit interface is included in the command. This allows the router to complete its forwarding destination in a single look up.

# Gateway of Last Resort or default static route
 The IP address of the router in a network to which data packets with unknown routes should be forwarded
 ![image](https://github.com/user-attachments/assets/ab675559-05fa-475e-8b6f-2d8a3f784a80)

# Save configuration
It is important to save your configuration changes to the router as you go. You can save changes to the router configuration by using the copy running-configuration 
startup-configuration (copy run start) command or write memory (wr m), as follows:
 RouterA# copy run start
 RouterA# wr m

(copy run start): The command for copying the running configuration to the startup configuration
write memory (wr m) : The command that saves configuration changes to memory

## Commands used to configure Static Routing
![image](https://github.com/user-attachments/assets/73d06216-45a4-4415-be0f-65f28b48c770)

## DYNAMIC ROUTING PROTOCOLS
A protocol that dynamically updates a routing table to account for loss of or changes in routes or changes in data traffic.
The use of dynamic routing protocols, which enable a router’s routing tables to be dynamically updated to account for losses of or changes in routes or changes in data traffic. The routers update their routing tables using information obtained from adjacent routers.

# Hop count
The number of routers the data packet must pass through to reach 
the destination network.

##  Distance Vector Protocol
A routing algorithm that periodically sends the entire routing table to its neighboring or adjacent router.

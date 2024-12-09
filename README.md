![image](https://github.com/user-attachments/assets/cab6c96c-a31c-49c2-a364-b1df08c0ee2f)


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
 router# show ip protocol - Displays the routing protocols that are currently running in a router
# Hop count
The number of routers the data packet must pass through to reach 
the destination network.

##  Distance Vector Protocol
A routing algorithm that periodically sends the entire routing table to its neighboring or adjacent router.

# RIP
Routing Information Protocol (RIP) is a dynamic routing protocol, which means the routers periodically exchange routes. RIP is classified as a distance vector protocol, and it uses router hop count as the metric. RIP permits a maximum of 15 hops to prevent routing loops. A routing loop occurs when a router forwards packets back to the router that sent them
![image](https://github.com/user-attachments/assets/4a6f77bd-b334-4034-b9f4-5ebda99e80a8)
The default time interval for RIP for exchanging routing tables is 30 seconds. This results in slow route convergence, and if multiple routers are sharing RIP routes, the convergence time is even longer.

# RIPv2
 The steps needed to configure RIPv2 are almost exactly the same as for configuring RIPv1. The only difference is that the version must be specified in the router rip configuration. The following example shows how to start with the RIP configuration from earlier in this chapter and enter the router’s configuration 
mode (Router(config)#) and input the command router rip to use the RIP routing protocol. The next step is to configure RIPv2 to be used with the command  version 2. (If you don’t specify the version, RIPv1 is used by default.) This is what these two steps look like:
![image](https://github.com/user-attachments/assets/1cc6cb07-7469-4a33-8b0b-16bee708c7cd)

# Link State Protocol
 A link state protocol establishes a relationship with a neighboring router. The routers exchange link state advertisements to update neighbors regarding route 
status. The link state advertisements are sent only if there is a change or loss in the network routes and the link state protocols converge to route selection quickly.

Link state protocols use hello packets to verify that communication is 
established with neighbor routers.
 The key issues related to link state protocols are summarized as follows:
 ● They find neighbors/adjacencies.
 ● They use route advertisements to build the routing table.
 ● They send hello packets.
 ● They send updates when routing changes.
 Open Shortest Path First (OSPF) is a dynamic link state routing protocol. It was 
developed by the Interior Gateway Protocol (IGP) working group for the Internet 
Engineering Task Force (IETF) specifically for use in TCP/IP networks. OSPF 
is an open (that is, not proprietary) protocol that is supported by many vendors. 
The main advantages of OSPF are rapid convergence and very low bandwidth 
consumption. When a network is completely converged, all the routers in the 
network agree on the best routes. After the initial flooding of routes in the form of 
link state advertisements (LSAs), OSPF sends route updates only when there is a 
change in the network. Every time LSAs are sent, each router must recalculate the 
routing table.

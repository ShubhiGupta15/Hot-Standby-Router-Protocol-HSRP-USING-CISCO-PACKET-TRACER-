# Hot-Standby-Router-Protocol-HSRP-Using Cisco Packet Tracer
![image](https://user-images.githubusercontent.com/79734129/116816911-98f11780-ab81-11eb-854a-f069c790cbd2.png)

WHAT IS HSRP?
1.Hot Standby Router Protocol (HSRP) is a CISCO proprietary protocol, which provides redundancy for a local subnet. In HSRP, two or more routers gives an illusion of a virtual router.
2.HSRP allows you to configure two or more routers as standby routers and only a single router as active router at a time. All the routers in a single HSRP group shares a single MAC address and IP address, which acts a default gateway to the local network. The Active router is responsible for forwarding the traffic. If it fails, the Standby router takes up all the responsibilities of the active router and forwards the traffic.

SOME IMPORTANT TERMS RELATED TO HSRP-
Virtual IP : IP address from local subnet is assigned as default gateway to all local hosts in the network.
Virtual MAC address : MAC address is generated automatically by HSRP. The first 24 bits will be default CISCO address (i.e. 0000.0c). The next 16 bits are HSRP ID (i.e. 07.ac). The next 8 bits will be the group number in hexadecimal. e.g- if the group number is 10 then the last 8 bits will be 0a. Example of virtual MAC address –
     0000.0c07.ac0a
Hello messages : Periodic messages exchanged by active and standby routers. These messages are exchanged after every 3 seconds telling the state of router.
Hold down timer : Its default value is 10 seconds i.e roughly 3 times the value of hello message. This timer tells us about the router that how much time will the standby router waits for hello message if it is not received on time. Note- If the active router fails then the standby router will become the active router.
Priority : By default, the priority value is 100. It is helpful when the active router comes back after falling down, we can change the priority of standby router (which has become the active router after the original active router is down) to less than 100 therefore it again becomes standby router.
Preempt : It is a state in which the standby router automatically becomes the active router.

WHAT ARE DIFFERENT HSRP STATES?
When in operation, HSRP devices are configured into one of many states:
Active – This is the state of the device that is actively forwarding traffic.
Init or Disabled – This is the state of a device that is not yet ready or able to participate in HSRP.
Learn – This is the state of a device that has not yet determined the virtual IP address and has not yet seen a hello message from an active device.
Listen – This is the state of a device that is receiving hello messages.
Speak – This is the state of a device that is sending and receiving hello messages.
Standby – This is the state of a device that is prepared to take over the traffic forwarding duties from the active device.

WHAT ARE ADVANTAGES AND DISADVANTAGES OF HSRP?
ADVANTAGES-
Used for backup process
No need to change default gateway every time
 No fault tolerance
DISADVANTAGE-
One of the gateways always sits idle until the active device fails. This wastes the forwarding potential of this second device; to solve this problem, utilize multiple HSRP groups.



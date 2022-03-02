# Week 5 Notes

## Location Management
### Overview
* Legacy topic in mobile computing
* Manages the mobile phone connectivity to the cell tower during user mobility
* mobile hosts - any mobile phones
* MH are served by base stations (also called access points or cell towers)
* can roam about the network
* must locate other mobile hosts to communicate with them - involves finding the base station currently serving the mobile host, **search operation**
* when a mobile host moves, it must let the system know where it is, update operation (**update operation** also called **registration**)
* must allow mobile hosts to switch btwn base stations to support roaming - **handoff operation**
* MH will be served by BS at a time
* BS coverage is one cell
* search, registration, update, handoff 
### Tradeoffs
* Location information
   * can be maintained at various granularities:
     * one cell - requires MH to update location every time it moves from one cell to another - tradeoff: more accurate location info vs a large number of updates, which may overwhelm the system
     * cell group - organize cells into groups, only update when leaving current group - tradeoff: less accurate location info, which will require paging every BS in the group, fewer updates and less load on the system
* there always be tradeoffs btwn cost of search and update operations
   * more updates = more accurate location info = less cost for search
   * fewer updates  = less accurate location info = more cost for search
### Handoffs
* handoffs btwn BSs are required to support roaming
* there isn't necessarily a one-to-one correspondence btwn handoffs and updates
* issues:
   * when to handoff?
   * selecting a new BS
   * allocation of resources such as channels
   * informing the old BS so that packets destined for MH can be forwarded
* location registrar (db) 
* Mobile controlled handoff vs network controlled handoff
* handoff may be necessary bc: mobile host is moving, current BS is overloaded, quality of communication available at BS
* choosing a new BS: based on signal strength, predicted movement of MH, resources available at BS
### Location Registrars
* Location Registrars are databases containing location information for MHs
* To get the idea, consider a system with only one LR, a **Home Location Registrar**
* Location is maintained at a single-cell granularity <br> 
![image](https://user-images.githubusercontent.com/17733481/156081169-d61834ae-9e76-4da5-8fb3-63a75f72ceab.png)
### Enhancements
* can add a timestamp and time-to-live (TTL) to registration information
   * TTL (not the same as residence time of node in cell)
     * helps in constraining the search cost - search diameters = max speed x TTL
   * Related to concept of soft state
     * hard state - explicit revocation of "state"
     * soft state - implicit revocation of "state" - makes the system more fault-tolerant - adaptive to changes in system
* single LR scheme - if ttl expires then location for mobile host is assumed out of data, can expand the search to neighboring cells when attempting to locate an MH  
### Registration Area
* partitions cells into specific groups - handoff when a cell goes from one group to another
* Advantages of RA Approach
   * reduces update cost
   * bounds the search cost (number of cells queried) - search is restricted to an RA
   * makes LM more scalable by reducing number of registrations to be processed by the HLR
   * makes LM more manageable (as compared to per-user LM schemes)
* Issues
   * granularity of RA (how to config system into multiple RAs)
     * same size (homogeneous) or different size (in terms of cells)?
     * optimization problem: how to partition the cells into RAs taking into account call + mobility pattern so as to optimize "LM cost"
### Multiple Registrars
* Forwarding pointers - when maintaining multiple location registrars, use a chain of forward pointers to track the MH
* Replication of location registrars - flat, hierarchical
* Flat - entire network is spanned over serveral location registrars of the same level (k random location registrars) - flat replication
    * avg update cost - O(k)
    * avg search cost - O(n/k)  
* Hierarchical - like a tree  
   * avg update cost - O(log n) 
   * avg search cost - O(log n) <br> ![image](https://user-images.githubusercontent.com/17733481/156268526-8fbc4ec0-3325-4cfe-a195-f34ea363c1d5.png)
* Can have a mixture of hierarchical and flat 

## Mobile Internet Protocol (IP)
### Mobile Internet Protocol (IP)
* Idea is to have unlimited range
* Replicate the wireless connection of wifi, but increase the range
* A protocol is needed which allows network connectivity across host movement
* Protocol to enable mobility must not require massive changes to router software, etc.
* Must be compatible with large installed base of IPv4 networks/hosts
* Confine changes to mobile hosts and a few support hosts which enable mobility
* Just hacking DNS won't work: DNS updates take time, hooks for normal users to update DNS won't be accepted by administrators, after DNS lookup raw IP address is used by TCP, UDP,...
* IP
   * network layer, "best-effort" packet delivery
   * support UDP and TCP (transport layer protocols)
   * IP host addresses consists of two parts: network ID and host ID
   * by design, an IP host address is tied to a home network address
   * hosts are assumed to be wired and immobile
   * intermediate routers look only at a network address
   * mobility without a change in IP address results in unrouteable packets
### Mobile Internet Protocol (IP) Basics
* Proposed by IETF (Internet Engineering Task Force) - standards development body for the Internet
* Mobile IP allows a mobile host to move about without changing its **permanent** IP address
* Each mobile host has a **home agent** on its **home network**
* **Foreign agents** on remote networks also assist
* Mobile host establishes a **care-of** address when it's away from home
* **Correspondent host** is a host that wants to send packets to the mobile host
* correspondent host sends packets to the mobile host's IP permanent address
* these packets are routed to the mobile host's home network
* Home agent forwards IP packets for mobile host to current care-of address
* Mobile host sends packets directly to correspondent, using the permanent home IP as the source IP
* 

### Mobile IP: Nuances
### Mobile IP: Inefficiencies
### Mobile IP: Remote IP
### Mobile IP: Security
### Mobile IP: Address Resolution Protocol (ARP)

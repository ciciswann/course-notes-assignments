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
* 

## Mobile Internet Protocol (IP)

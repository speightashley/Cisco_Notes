When we have different sized departments that need a different number of hosts, we can use a VLSM (Variable Length Subnet Mask).

Instead of just creating subnets that are all the same size, we can create, for example, one subnet with a /31 which can be used for a serial link between LANs that gives us 2 hosts and then a /26 which will give us 4 possible networks with a total of 62 hosts per subnet.

# Questions to consider for VLSM design

- How many locations do we have in the network?
- How many hosts in each location?
- What are the requirements for each location? (Should different departments be in different subnets?)
- What is an appropriate size for each subnet? (Leave room to grow but don't overdo it)


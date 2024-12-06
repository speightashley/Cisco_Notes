When we have different sized departments that need a different number of hosts, we can use a VLSM (Variable Length Subnet Mask).

Instead of just creating subnets that are all the same size, we can create, for example, one subnet with a /31 which can be used for a serial link between LANs that gives us 2 hosts and then a /26 which will give us 4 possible networks with a total of 62 hosts per subnet.

# Questions to consider for VLSM design

- How many locations do we have in the network?
- How many hosts in each location?
- What are the requirements for each location? (Should different departments be in different subnets?)
- What is an appropriate size for each subnet? (Leave room to grow but don't overdo it)

# Step by Step to VLSMing
1. Find the largest segment first and allocate a suitable sized subnet for it and allocate this at the start of the address space
2. Continue going down the list from largest to smallest
3. Allocate spare subnets for future growth and leave enough room in the subnets for additional hosts

![[Pasted image 20241206205108.png]]
1. We start with the largest requirements which is the engineering departments in Boston and New York.

## New York - Engineering
If we use a /27, we allowed 30 hosts on each of them which is enough.

This gives us a subnet mask of 255.255.255.224

The network address will be 200.15.10.0/27

The size of the subnet is 32 so the broadcast address will be 200.15.10.31

The hosts range from 10.1 to 10.30

## Boston - Engineering
Same as above but we need to add it to the end of the range for New York.

So the network address will be 200.15.10.32/27

Add 30 to it for the hosts and it gives us 62, add 1 for the broadcast address and it gives us 200.15.10.63. 

## New York - Sales Department (14 Hosts)

We need to use a /28 which allows us 14 hosts

Network address starts at 200.15.10.64 because of Boston Engineering

The blocks go up in 16s which allows us the 14 hosts + network and broadcast address so the next network address is 80.

Minus 1 gives us our broadcast address of .79 with valid hosts of .65 to .78



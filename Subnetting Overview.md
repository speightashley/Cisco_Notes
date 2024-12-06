# Calculating the number of networks from a CIDR notation

To calculate the number of available subnets, the formula is $2^{subnet-bits}$
For example:

If we have been given the class C 200.15.10.0/24 it has 24 bits out of 32 for the network side.

This is the same as a 255.255.255.0 because each segment is worth 8 bits. $8+8+8=24$. 8 bits is worth 255 in binary because:

8 bits in a byte:

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   |
The sum of all of the bits = 255

Now the formula for $2^{subnet-bits}$ can come into play

We have the last byte with 0 bits in it which means we can create subnets by moving the bits to the right.

Currently the last block of bytes looks like this:

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   |
If we move a bit to the right, we end up with:

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | 1   | 0   | 0   | 0   | 0   | 0   | 0   |
Using the formula, we have 2 extra bits from the 24 that we were given so we can make $2^2$ networks. That's the same as $2*2$ which is 4. 

If we had **borrowed** 4 bits from the host portion, we would be able to create $2*2*2*2$ subnets which is 16 subnets. 

Let's work with the /26 i.e the 2 borrowed bits. 
We were originally given a /24 address, we borrowed 2 bits from the host portion which gives us 4 different networks from our allocated range.

Each subnet will have:

1. **Block Size:**
    - With a `/26` mask, there are $2^{32−26}=64$ IP addresses in each subnet (including network ID and broadcast).
2. **Subnets Created:**
    - From `200.15.10.0/24`, the subnets are:
        - Subnet 1: `200.15.10.0` to `200.15.10.63`
        - Subnet 2: `200.15.10.64` to `200.15.10.127`
        - Subnet 3: `200.15.10.128` to `200.15.10.191`
        - Subnet 4: `200.15.10.192` to `200.15.10.255`


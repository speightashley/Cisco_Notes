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

We have 
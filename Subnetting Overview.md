# Calculating the number of networks from a CIDR notation

To calculate the number of available subnets, the formula is $2^{subnet-bits}$
For example:

If we have been given the class C 200.15.10.0/24 it looks like this in bits:

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   | 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   | 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   | 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | 1   | 0   | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 1   | 1   | 1   | 1   | 0   | 0   | 0   | 0   | 1   | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   |
| 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   |


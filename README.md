# Ex: 02 - Huffman - Shannon_fano
## AIM:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average codeword length, Entropy, Variance, Redundancy, Efficiency.

## TOOLS REQUIRED:
Python IDE with Numpy and Scipy.

## PROGRAM:
```
# Huffman and Shannon-Fano Coding Parameters

import numpy as np
import math

# Initialize variables
L = 0
hs = 0
p = []
lk = []

# Input number of samples
n = int(input("Enter the number of Samples: "))

# Input probabilities
for i in range(n):
    pr = float(input(f"Enter the probability of sample value {i + 1}: "))
    p.append(pr)

# Input codeword lengths
for j in range(n):
    l = float(input(f"Enter the length of sample value {j + 1}: "))
    lk.append(l)

# Average codeword length
for k in range(n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

# Entropy calculation
for k in range(n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e

hs = round(hs, 3)

# Efficiency
eff = hs / L
eff = round(eff, 3)

# Redundancy
red = round(1 - eff, 3)

# Variance
var = 0

for k in range(n):
    var1 = p[k] * (lk[k] - L) ** 2
    var = var + var1

var = round(var, 3)

# Output results
print(f"\nAverage Codeword Length is: {L}")
print(f"Entropy is: {hs}")
print(f"Efficiency is: {eff}")
print(f"Redundancy is: {red}")
print(f"Variance is: {var}")
```


## CALCULATION:


<img width="986" height="1599" alt="dc ex 2 2" src="https://github.com/user-attachments/assets/5aad58c8-971e-49ea-8084-2e9316c10328" />


<img width="972" height="1600" alt="dc ex 21" src="https://github.com/user-attachments/assets/99940217-6b40-4661-866d-753e5b30519f" />



## OUTPUT:
<img width="533" height="390" alt="Screenshot 2026-05-11 205645" src="https://github.com/user-attachments/assets/7601620a-8e58-42bf-af45-da624d892ca2" />



## RESULT:
The Huffman and Shannon-Fano of the given statistics {} using python are verified.

# Huffman-Shannon_fano
### Aim
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.
### Tools Required
Personal computer,
Google colab software.
### Program
```python
#Huffman and Shannon-Fano coding
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
### output
![image](https://github.com/user-attachments/assets/dc156e61-eceb-4a09-84a8-82fadd0f3df3)
### Calculation
![WhatsApp Image 2025-03-30 at 21 28 08_6fc93649](https://github.com/user-attachments/assets/87f8d62c-fb9d-4569-8591-9d2a209dfd3c)
![WhatsApp Image 2025-03-30 at 21 28 09_4149d6b3](https://github.com/user-attachments/assets/bc9b1a4e-0b1f-407e-9da3-bc1cf91b1b56)

### Results.
The given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25 Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484

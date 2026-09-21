### euler project question 15
easy
used python to handle big numbers

code:
```
n = 2**1000
c = 0
r =0
while(n!=0):
    r = n%10
    c = c+r
    n = n//10
print(c)
```

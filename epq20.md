### euler question 20
easy
used python coz lazy

code :
```
import math

n = math.factorial(100)
c = 0
r = 0
while(n!=0):
    r = n%10
    c=c+r
    n = n//10
print(c)
```

works
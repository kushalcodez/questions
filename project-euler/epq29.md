### euler project question 29


only thing i couldnt understand is how to use big numbers in cpp rest easy

```
# cook your dish here
values = set()
for i in range(2, 101):
    for j in range(2, 101):
        values.add(i ** j)
print(len(values))
```
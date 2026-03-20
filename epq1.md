## question 1 euler project
approach was simple ap summation and no code was written , done using phone calculator


sum of ap with first element a and last element l, number of terms = n
```
sn = (n/2) * (a+l)
```

for 3 and 5 multiples
first for 3;
sum of all multiples of 3,
n = 999/3 = 333
sn1 = 166833
then for 5; 
sum of all multiples of 5,
n = floor(999/5) = 199
sn2 = 99500,


sn1 and sn2 also include multiples of 15, so subtracting once gives us the total sum,

ie , 
sn1 has multiples of 3 which also includes multiples of 15
sn2 has multiples of 5 which also includes multiples of 15
when we add sn1 and sn2 we get the multiples of 15 two times, therefore subtracting them once gives us the true sum.


for 15;
sum of all multiples of 15,
n = floor(999/15) = 66
sn3 = 33165

sn final = sn1+sn2-sn3

====> 233168
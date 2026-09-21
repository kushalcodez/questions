### euler project question 30

easy but had to do some math to get bounds,

sum of digits to power 5 in any number <= (number of digits in that number)*9^5

and also,

since any n digit number lies in, 10^(n-1) <= k <= 10^n -1 (eg, for 3 digit number k, 100<=k<=999)

therefore there should be overlap between n(9^5) and 10^(n-1), then and only then we get a number which satisfies the condition

therefore,
for n=7 , 10^6 <= n <= 7(59049) ==> which is not possible therefore the upper bound would be 6(59049) = 354294

i took safe case 500k

code:
```
#include <bits/stdc++.h>
using namespace std;
bool sump(int k)
{
    int c = k;
    long long j = 0;
    auto s = 0;
    long long r = 0;
    while(k!=0)
    {
        r = k%10;
        j += (r*r*r*r*r);
        k = k/10;
    }
    if(j==c){
        return true;
    }
    return false;
    
}
int main() {
	// your code goes here
    auto l = 0;
    for(int i = 2; i<=500000;i++)
    {
        if(sump(i))
        {
            l+=i;
        }
    }
    cout<<l;
    return 0;
}
```

easy but the math was quite confusing, read some articles and then got to know about the bounds, earlier was taking upto 1 million(10^6 since 5+1) (was getting answer but still)
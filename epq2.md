## question 2 euler project
approach was basic, calculate fibonacci and then check for even and then summation

-> brute force recursion was failing since 4 million 
-> googled new way on how to find fibonacci

basically c = a+b;
            a = b;
            b = c;

how it works is fibonacci properties (a+b = next number, b+next number = next 2  and so on)

# code
```
#include <iostream>
using namespace std;
int main() {
     long long int k = 4000000;
    long long int p = 0;
    long long int a = 1, b = 1;

    while (b <= k) {
        if (b % 2 == 0)
            p += b;
        long long int c = a + b;
        a = b;
        b = c;
    }

    cout << p;
    return 0;
}
```

if this helps :

a         |         b(current fibonacci)
1                   1 
1                   2 (1+1) (even) p = 2;
2                   3 (1+2)
3                   5 (2+3)
5                   8 (even) p = 10
and so on




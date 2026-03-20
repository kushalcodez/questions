### question 5
thought of using recursion, since <br>
lcm(a,b) = a*b/gcd(a,b) <br>
lcm(a,b,c,d.....) = lcm(a,lcm(b,c,d.....)) <br>
and <br>
to extend, <br>

## taking an array with elements, a[0],a[1],a[2] ..... a[i].
taking k = a[0] <br>
==> lcm(a[0],a[1]....a[i]) = lcm(k,a[i])


therefore the code becomes,

```
// Online C++ compiler to run C++ program online
#include <bits/stdc++.h>
using namespace std;
int main() {
    int k;
    vector<int> vc = {1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20};
    auto a = vc[0];
    for(int i = 1; i<20;i++){
        a = (((vc[i]*a))/(gcd(vc[i],a)));
    }
    cout<<a;
   return 0;
}
```

### sources used,

stack overflow - https://stackoverflow.com/questions/147515/least-common-multiple-for-3-or-more-numbers








<b>lcm(a,b,c,d) = lcm(a,lcm(b,c,d)) = lcm(lcm(a,b),c,d) = lcm(lcm(j,c),d) = lcm(h,d) </b><br>
insane confusing math but it uses associative property of lcm
image for better understanding
![imageyo](https://media.geeksforgeeks.org/wp-content/uploads/20241127153437644842/properties---------of---------lcm---------1.webp)
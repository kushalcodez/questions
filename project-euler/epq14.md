### euler project question 14

easy question, made a function to calculate collatz series length and then called it for all the odd numbers 0-10^6-1

odd numbers only because obviously the collatz length of odd > even (even/2 = even) <br>
code :<br>
```
// Online C++ compiler to run C++ program online
#include <bits/stdc++.h>
using namespace std;
long long int collatzcountr(long long int n){
    long long int c = 1;
    while(n!=1)
    {
        if(n%2==0){
            n = n/2;
        }else{
            n = (3*n)+1;
        }
        c++;
    }
    return c;
}
int main() {
    int maxon = 0;
    int st = 0;
    int t = 0;
    for(int i = 1;i<=999999;i+=2)
    {
        t = collatzcountr(i);
        if(t>maxon){
            st= i;
            maxon = t;
        }
    }
    cout<<st<<endl;
    cout<<maxon<<endl;
    return 0;
}
```

easy question, i used int earlier and the code was overflowing :(

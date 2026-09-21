### euler project question 10

easy question, made an isprime function and then passed values and summed

code:
```
// Online C++ compiler to run C++ program online
#include <bits/stdc++.h>
using namespace std;
bool isprime(long long int n){
    int c = 1;
    for(int i = 2; i*i<=n;i++)
    {
        if(n%i==0){
            return false;
        }
    }
    return true;
}
int main() {
    long long int s=0;
    for(long long int i = 2; i<=2000000;i++)
    {
        if(isprime(i)){
            s+=i;
        }
    }
    cout<<s;
    return 0;
}
```

twas good
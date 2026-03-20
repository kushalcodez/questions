### question 3

i hated this one, tried brute force reached tle

googled optimised solution and understood something


original code (brute force, tle , mid)
```
// Online C++ compiler to run C++ program online
#include <iostream>
using namespace std;
int lp(long long int n){
    int l = -1;
    while(n%2==0){
        l = 2;
        n = n/2;
    }
    for(int i = 3; i*i <=n ; i+=2){
        while(n%i==0){
            l=2;
        }
    }
    if(n>2){
        l = n;
    }
    return l;
}
int main() {
     long long int k = 600851475143;
     long long int p = lp(k);
    cout << p;
    return 0;
}
```

new one, g4g my goat ,

-> strip n with factors of 2 and 3 step 1.
-> then use math genius such that, all primes greater than 3 are in the form of <b>6k+-1</b>


new code,
```
// Online C++ compiler to run C++ program online
#include <iostream>
using namespace std;
int lp(long long int n){
    int l = -1;
    while(n%2==0){
        l = 2;
        n = n/2;
    }
    while(n%3==0){
        l = 3;
        n = n/3;
    }
    for(int i = 5; i*i <=n ; i+=6){
        while(n%i==0){
            l=i;
            n = n/i;
        }
        while(n%(i+2)==0){
            l = i+2;
            n = n/(i+2);
        }
    }
    if(n>4){
        l = n;
    }
    return l;
}
int main() {
     long long int k = 600851475143;
     long long int p = lp(k);
    cout << p;
    return 0;
}
```
-> in the for loop we check with i and i+2, such that 6k-1 is i and 6k+1 is i+2
eg 5,7 -> 11,13 -> 17,19 and so on...

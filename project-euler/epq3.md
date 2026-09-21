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

new one,

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



#### source and idea for new solution

from reddit :- https://www.reddit.com/r/learnmath/comments/1dqhnzx/how_does_one_calculate_the_largest_prime_factor/

```

Oh, OK. Well, you first notice the number is even so its divisible by 2. It's still even so you can divide it by 2 again and it turns out a third time.

This leaves us with 9428895 and we notice the sum of the digits, 45, is divisible by 9, so the number itself is divisible by 9. Since 9 is 32 we note 3 is a prime factor, and we are left with 1047655

The result ends in 5 so you know its divisible by 5, so go ahead and divide it by 5. Note down that 5 is one of the prime factors in case it turns out to be the biggest (it's not, but we don't know that yet)

Now, you're left with 209531. Since you've factored out all 2's, 3's, and 5's, you might want to look at 7 next. I don't know a shortcut for 7, but dividing it gives us 29933, a whole number, so it works.

There IS a trick for 11, add the even numbered digits, add the odd numbered digits and subtract. If the result is 0, the number is divisible by 11. For 29933, we have 14-12=2 so its not divisble by 11.

Unfortunately, I don't know how you'd easily realize that 29933 is divisible by 37, leaving a result of 809, which is prime.

```
~ comment by some user
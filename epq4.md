### question 4
oh this question was fun

first, we know that palindrome product should be >= 6 digits (since largest duh)

and also like the code is pretty self explainatory


```
// Online C++ compiler to run C++ program online
#include <bits/stdc++.h>
using namespace std;
bool ispalin(long long int n){
    auto c = n;
    int r = 0;
    while(n !=0){
        r = r*10 + (n%10);
        n = n/10;
    }
    if(r == c){
        return true;
    }
    return false;
    }
int main() {
    vector<int> vc;
    for(int i = 999; i>=900;i--){
        if(i%11==0){                      #important
        for(int j = 999;j>=900;j--)
        {
            auto n1 = i*j;
            if(ispalin(n1)){
                vc.push_back(n1);
            }
        }
    }
    }
    cout<< *max_element(vc.begin(),vc.end());
    return 0;
}
```


### impt stuff behind code

-> palindrome in form of abccba = a + 10b + 100c + 1000c + 10000b + 100000a <br>
====> 100001a + 10010b  + 1100c = palindrome <br>
====> 11(9091a+910b+100c) = x*y <br>

this means that x or y should be a multiple of 11, and therefore the if else statement (highlighted)

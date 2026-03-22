### euler project question 9
simple if else code with for loops, got it easily

code -
```
// Online C++ compiler to run C++ program online
#include <iostream>
using namespace std;
int main() {
    int a,b,c;
    for(a = 1; a<=1000;a++){
        for(b=1;b<=1000;b++){
            for(c=1;c<=1000;c++){
                if(((a*a)+(b*b))==c*c && a+b+c==1000){
                    cout<<a<<endl;
                    cout<<b<<endl;
                    cout<<c<<endl;
                    break;
                }
            }
        }
    }
    return 0;
}
```

worked perfectly got the answer
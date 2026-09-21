### euler project question 12
created a fxn to calculate divisors (count),
using triangular formula in 2 ways,
sn = n/2 * n+1 and sn = n * (n+1)/2

also co prime n and n+1, therefore total factors = no. of factors (n or n/2) * no. of factors (n+1 or n+1/2)

code-
```
#include <iostream>
using namespace std;
int nod(int n) {
    int c = 0;
    for (int i = 1; i * i <= n; i++) {
        if (n % i == 0) {
            c++;
            if (i != n / i) c++;
        }
    }
    return c;
}
int main() {
    int prev = nod(1);
    for (int n = 2; ; n++) {
        int curr = nod(n);
        int total;
        if (n % 2 == 0)
            total = nod(n / 2) * prev;
        else
            total = prev * nod((n + 1) / 2);
        if (total >= 500) {
            long long tri = (long long)n * (n + 1) / 2;
            cout << "Triangular number: " << tri << endl;
            cout << "Divisors: " << total << endl;
            break;
        }
        prev = curr;
    }
    return 0;
}
```
![image](https://github.com/user-attachments/assets/99d7c3f2-7d2a-4ed7-a59b-7d5c2ee08e17)

Áp dụng lũy thừa nhị phân

```cpp
#include <bits/stdc++.h>

using namespace std;

using ll = long long;

int mod = 1000000007;

ll binpow(int n, int k){
    if(k == 1) return n;
    ll res = binpow(n, k / 2);
    if(k % 2 == 0){
        return (res % mod) * (res % mod) % mod;
    }
    else return ((res % mod) * (res % mod) % mod) * (n % mod) % mod; 
}

int main(){
    int n, k;
    cin >> n >> k;
    cout << binpow(n % mod, k) << endl;
    return 0;
}
```

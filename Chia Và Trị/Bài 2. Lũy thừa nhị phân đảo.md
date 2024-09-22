![image](https://github.com/user-attachments/assets/f43d94da-80e8-49e3-b3e6-30cb24445220)

```cpp
#include<bits/stdc++.h>

using namespace std;

using ll = long long;
int mod = 1e9 + 7;
ll rev (ll n){
    ll res = 0;
    while(n){
        res = res * 10 + n % 10;
        n /= 10;
    }
    return res;
}
ll kq(ll n, ll k){
    if(k == 1){
        return n;
    }
    ll res = kq(n, k / 2);
    if(k % 2 == 0){
        return (res % mod) * (res % mod) % mod;
    }else{
        return ((res % mod) * (res % mod) % mod) * (n % mod) % mod;
    }

}
int main(){
    ll n; cin >> n;
    ll m = rev(n);
    ll res  = kq(n % mod, m);   
    cout << res << endl;
    
}
```

![image](https://github.com/user-attachments/assets/bd1650a2-e809-45a4-b5c7-8f8a4f0109f3)

Bài này thì mình sử dụng nhị thức newton để làm.

Theo gợi ý thì viết * tương ứng với N đơn vị. Và ta đặt các vách ngăn để phân tích.Bài này khá giống với phân hoạch.

Ví dụ n = 4 thì ta sẽ có 3 chỗ trống. Và mỗi lần đặt vách ngăn

![image](https://github.com/user-attachments/assets/a30788f2-5dd9-4c07-8fc5-208cbe64b09c)

Áp dụng lũy thừa nhị phân thôi

```cpp
#include <bits/stdc++.h>

using namespace std;

using ll = long long;

int mod = 1000000007;

ll kq(ll n){
    if(n == 1) return 2;
    ll res = kq(n / 2);
    if(n % 2 == 0){
        return (res % mod) * (res % mod) % mod;
    }
    else return ((res % mod) * (res % mod) % mod) * 2 % mod; 
}

int main(){
    ll n; cin >> n;
    n--;
    cout << kq(n) << endl;
    return 0;
}
```

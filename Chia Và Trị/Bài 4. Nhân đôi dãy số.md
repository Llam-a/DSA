![image](https://github.com/user-attachments/assets/32f50333-949f-4c72-ac38-59975c2c2d0a)

![image](https://github.com/user-attachments/assets/381fc136-8d16-4d2a-899e-866452164908)

Đầu tiên mình có X phần tử. Một lần nhân đôi là 2X + 1.Thì mỗi tầng của mình sẽ là `2^n -1`

![image](https://github.com/user-attachments/assets/ecb932cf-c670-4651-a629-6d09b1c829c7)


Bài này có 3 trường hợp:

Trường hợp đầu tiên là nó sẽ chính là số ta mới thêm vào lần thứ N - 1 `k = pow(2, n - 1)`. Số cần tìm là n luôn.

Trường hợp 2 và 3 là nó sẽ nằm bên trái hoặc bên phải.`k < 2^n-1` thì bên trái, `k > 2^n-1` là bên phải

```cpp
#include <bits/stdc++.h>

using namespace std;

using ll = long long;

int mod = 1000000007;

int find(ll n, ll k){
    if(k == pow(2, n - 1)){
        return n; 
    }
    if(k < pow(2, n - 1)){
        return find(n - 1, k);
    }else{
        return find(n - 1, k - ll(pow(2, n - 1)));
    }
}

int main(){
    ll n,k; cin >> n >> k;
    cout << find(n, k) << endl;
    return 0;
}
```

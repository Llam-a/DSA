![image](https://github.com/user-attachments/assets/ec6d72ff-8144-4c07-8c0a-8b43993e78f1)

```cpp
#include<bits/stdc++.h>

using namespace std;

int main(){
    int n; cin >> n;
    long long res = 1;
    for(int i = 1; i <= n; i++){
      int x; cin >> x;
      res *= x % 1000000007;
      res %= 1000000007;
    }
    cout << res << endl;
}
```

![image](https://github.com/user-attachments/assets/96c52efe-ee87-4eea-862c-b1ab85ba52f0)

Làm tới đâu chia dư tới đó

```cpp
#include<bits/stdc++.h>

using namespace std;

int main(){
    int n; cin >> n;
    long long res = 0;
    for(int i = 1; i <= n; i++){
      int x; cin >> x;
      res += x % 1000000007;
      res %= 1000000007;
    }
    cout << res << endl;
}
```

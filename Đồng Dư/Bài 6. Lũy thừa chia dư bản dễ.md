![image](https://github.com/user-attachments/assets/1485eae6-2835-49e2-b90c-1b3297af1904)

Bài này mỗi lần mình lũy thừa thì mình chia dư.

```cpp
#include<bits/stdc++.h>
const int mod = 1000000007;
using namespace std;

int main(){
  int a,b; 
  cin >> a >> b;
  int res = 1;
  for(int i = 1; i <= b; i++){
      res = (res * a) % mod;
      res %= mod;
  }
  cout << res << endl;
  
}
```

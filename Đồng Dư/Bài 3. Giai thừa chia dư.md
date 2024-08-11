![image](https://github.com/user-attachments/assets/67cefdbd-ed66-4fc6-b59d-9b8349f19915)

```cpp
#include<bits/stdc++.h>

using namespace std;

int main(){
  int n; cin >> n;
  long long res = 1;
  for(int i = 1; i <= n; i++){
    res *= i % 1000000007;
    cout << res << endl;
  }
}
```

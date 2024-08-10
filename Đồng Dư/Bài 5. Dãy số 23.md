![image](https://github.com/user-attachments/assets/4def23cc-fae0-4518-9efd-c8139c106b1a)

Bài này khá giống dãy Fibonanci thôi, khác ở chỗ là sau khi tính thì mình cần chia dư

```cpp
#include<bits/stdc++.h>
const int mod = 1e9+7;
using namespace std;

int main(){
    int n;cin >> n;
    if(n == 1 || n == 2){
      cout << 1;
    }else{

    long long f1 = 1, f2 = 1, fn;
    for(int i = 3; i <= n; i++){
      fn = 2 * f1 + 3 * f2;
      fn %= mod;
      f2 = f1;
      f1 = fn;
      }
      
    cout << fn;
    }
}
```

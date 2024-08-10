![image](https://github.com/user-attachments/assets/29fe86a9-c2a9-492a-b9ae-c6c47d2ce602)

Bài này đã có gợi ý rồi, mình sẽ chia dư cho pow(10,k). Còn tính số mũ thì cho chạy vòng for thôi.

```cpp
#include<bits/stdc++.h>

using namespace std;

int main(){
  int n,m,k; cin >> n >> m >> k;
  long long res = pow(10, k);
  long long sum = 1;
  for(int i= 1; i <= m; i++){
    sum *= n;
    sum %= res;
  }
  cout << sum << endl;
}
```

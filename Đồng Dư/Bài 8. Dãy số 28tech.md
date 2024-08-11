![image](https://github.com/user-attachments/assets/2708768c-a593-4c07-9425-8c9f712535dc)

Bài này thì mình xây dụng hàm để tính thôi. Sau đó thì gọi nó ở dưới main rồi cout ra F[n] thôi

```cpp
#include<bits/stdc++.h>
long long F[1000005];
using namespace std;

void res(){
  F[1] = 2;
  F[2] = 8;
  for(int i = 3; i < 1000005; i++){
    F[i] = (2 * F[i - 1] + 8 * F[i - 2]) % 1000000007;
  }
}

int main(){
  res();
  int t; cin >> t;
  while(t--){
    int n; cin >> n;
    cout << F[n] << endl;
  }
}
```

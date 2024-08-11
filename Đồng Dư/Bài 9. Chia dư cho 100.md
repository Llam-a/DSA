![image](https://github.com/user-attachments/assets/d79f9ce4-df94-4a74-9fce-64693cb5469e)

Thay vì ta sẽ tính như công thức, thì mình có thể chuyển sang (a % 100)^b % 100. Mà a % 100 là 28. 

Thì sẽ là 28 % 100 * 28 % 100 *....

```cpp
#include<bits/stdc++.h>

using namespace std;

int main(){
  int n; cin >> n;
  long long res = 1;
  for(int i = 1; i <= n; i++){
    res *= 28;
    res %= 1000;
  }
  cout << res % 100 << endl;
}
```

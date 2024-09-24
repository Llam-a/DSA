![image](https://github.com/user-attachments/assets/971ce0a1-694d-4438-97d9-f4f7ab712070)

![image](https://github.com/user-attachments/assets/e6c501c4-ddf0-46d7-8a68-629d09626dfb)

```cpp
#include <bits/stdc++.h>

using namespace std;

using ll = long long;

int diff(int a[], int b[], int n){
    for(int i = 0; i < n - 1; i++){
        if(a[i] != b[i]) return i + 1;
    }
    return n;
}

int main(){    
    int n; cin >> n;
    int a[n], b[n - 1];
    for(int i = 0; i < n; i++){
        cin >> a[i];
    }
    for(int i = 0; i < n - 1; i++){
        cin >> b[i];
    }
    cout << diff(a, b, n) << endl;
    return 0;
}
```

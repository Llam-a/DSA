![image](https://github.com/user-attachments/assets/d56001d2-e336-42cb-bef4-4fbd96138e6d)

![image](https://github.com/user-attachments/assets/f5c590c3-1e3f-4719-95f9-993e81057560)

```cpp
#include <bits/stdc++.h>

using namespace std;

using ll = long long;


int main(){
    int n, m, h; cin >> n >> m >> h;
    int a[n], b[m], c[n + m + 1];
    for(int i = 0; i < n; i++){
        cin >> a[i];
    }
    for(int i = 0; i < m; i++){
        cin >> b[i];
    }
    int i = 0, j = 0, k = 0;
    while(i < n && j < m){
        if(a[i] <= b[j]){
            c[k] = a[i];
            i++; k++;
        }
        else{
            c[k] = b[j];
            j++; k++;
        }
    }
    while(i < n){
        c[k] = a[i];
        i++; k++;
    }
    while(j < m){
        c[k] = b[j];
        j++; k++;
    }
    cout << c[h - 1] << endl;
    return 0;
}
```

![image](https://github.com/user-attachments/assets/9ab4071d-fbda-4305-8294-d92ce382b138)

![image](https://github.com/user-attachments/assets/251cd597-5fb7-48b8-9b42-a828ff78c0db)

```cpp
#include<bits/stdc++.h>

using namespace std;

using ll = long long;

ll kq(int a[], int l, int r, int x){
    if(l > r ) return -1;
    ll mid = (l + r) / 2;
    if(a[mid] <= x){
        int tmp = kq(a, mid + 1, r, x);
        if(tmp != -1){
            return tmp;
        }else{
            return mid;
        }
    }
    return kq(a,l, mid -1, x);
}
int main(){
    int n,x;cin >> n >> x;
    int a[n];
    for(int &x : a){
        cin >> x;
    }
    int res =  kq(a, 0, n - 1, x);
    if(res != -1){
        cout << a[res] << endl;
    }else{
        cout << -1;
    }
}
```

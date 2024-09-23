![image](https://github.com/user-attachments/assets/add7232d-e3ab-4ba6-a842-6ed1a0aa85cb)

![image](https://github.com/user-attachments/assets/fca50392-b7e8-40ce-aa79-98038085ddd9)

```cpp
#include<bits/stdc++.h>

using namespace std;

using ll = long long;
ll cross_sum(int a[], int l, int mid, int r){
    ll left_sum = 0, max_left = 0;
    ll right_sum = 0, max_right = 0;

    for(int i = mid; i >= l; i--){
        left_sum += a[i];
        max_left = max(left_sum, max_left);
    }
    for(int i = mid + 1; i <= r; i++){
        right_sum += a[i];
        max_right = max(right_sum, max_right);
    }
    return max_right + max_left;
}
ll kq(int a[], int l, int r){
    if(l == r){
        return a[l];
    }
    ll mid = (l + r) / 2;
    return max({
        kq(a, l, mid),
        kq(a, mid + 1, r),
        cross_sum(a,l,mid,r),
    });
}
int main(){
    int n;cin >> n;
    int a[n];
    for(int &x : a){
        cin >> x;
    }
    cout << kq(a, 0, n - 1);
}
```

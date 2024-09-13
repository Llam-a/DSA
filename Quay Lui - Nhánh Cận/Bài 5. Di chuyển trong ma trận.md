![image](https://github.com/user-attachments/assets/2b45f4a1-7530-41ed-b926-4f65f37b0606)

```cpp
#include<bits/stdc++.h>

using namespace std;
int n,m,a[100][100],ans = 0;
void nhap(){
    cin >> n >> m;
    for(int i = 1; i <= n; i++){
        for(int j = 1; j <= m; j++){
            cin >> a[i][j];
        }
    }
}
void Try(int i , int j){
    if(i == n && j == m){
        ++ans;
        return;
    }
    if(i + 1 <= n){
        Try(i + 1, j);

    }
    if(j + 1 <= m){
        Try(i, j + 1);
    }
}
int main(){
    nhap();
    Try(1,1);
    cout << ans;
}
```

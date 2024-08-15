![image](https://github.com/user-attachments/assets/175aa063-0802-481d-b122-b16eec1ede46)

```
Ví dụ :
Input 01
12 4
8 9 10 11
Output 01
5
```
Mình vẫn sử dụng thuật toán sinh xâu tập con kế tiếp thôi.

Tạo 1 vector để lưu cấu hình đề cho.Tiếp theo, tạo 1 vector<vector> để lưu các tập con sinh ra.Rồi mình chạy while(final == 0), tạo vector chứa tập con sinh ra, rồi push nó vào vector<vector>.

Sau đó thì chạy for, kèm theo là biến đếm mỗi lần chạy.
```cpp
#include<bits/stdc++.h>

using namespace std;

int n,k,a[100],final = 0;
void ktao(){
    for(int i = 1; i <= k; i++){
        a[i] = i;
    }
}
void sinh(){
    int i = k;
    while(i >= 1 && a[i] == n - k + i){
      i--;
    }
    if(i == 0){
      final = 1;
    }else{
      a[i]++;
      for(int j = i + 1; j <= k; j++){
        a[j] = a[j - 1] + 1;
      }
    }
}
int main(){
    cin >> n >> k;
    vector<int> x(k);
    for(int i = 0; i < k; i++){
        cin >> x[i];
    }
    ktao();
    vector<vector<int>> v;
    while(final == 0){
        vector<int> tmp(a + 1, a + k + 1);
        v.push_back(tmp);
        sinh();
    }
    int cnt = 0;
    for(int i = v.size() - 1; i >= 0; i--){
        ++cnt;
        if(v[i] == x){
          cout << cnt << endl;
          return 0;
        }
    }
}
```

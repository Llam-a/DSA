![image](https://github.com/user-attachments/assets/89f2f379-080e-454d-96ad-3455c23fc090)

Bài này giống bài 2, khác là mình tự khởi tạo cấu hình đầu rồi chạy hết thôi

```cpp
#include<bits/stdc++.h>

using namespace std;
int n,k,a[1005],final = 0;
void ktao(){
  for(int i = 1;i <= k; i++){
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
      a[j] = a[j-1] + 1;
    }
  }
}
int main(){
    cin >> n >> k;
    ktao();
    while(final == 0){
      for(int i = 1; i <= k; i++){
        cout << a[i];
      }
      cout << endl;
      sinh(); 
    }
}
```

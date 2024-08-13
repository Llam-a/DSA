![image](https://github.com/user-attachments/assets/bc7e85e7-d640-4ae2-8caa-af61a84f53b5)

Bài này thì tương tự bài 1, nhưng mà thay vì in 1 và 0 thì bây giờ in B và A. Cấu hình đấu tiên là BBB thì chắc chắn là B là bit 0 còn A là bit 1.
Thêm nữa, ta phải tự sinh cấu hình đầu tiên.

```
#include<bits/stdc++.h>

using namespace std;

int n,a[100],final = 0;
void ktao(){
  for(int i = 1; i <= n; i++){
    a[i] = 0;// 000
  }
}
void sinh(){
  int i = n;
  while(i >= 1 && a[i] == 1){
    a[i] = 0;
    i--;
  }
  if(i == 0){
    final = 1;
  }else{
    a[i] = 1;
  }
}
int main(){
  cin >> n;
  ktao(); // cấu hình đầu tiên
  while(final == 0){
    for(int i = 1; i <= n; i++){
      if(a[i] == 0){
        cout << "B";
      }else{
        cout << "A";
      }
    }
    cout << endl;
    sinh();// sinh xâu kế tiếp
  }
}
```

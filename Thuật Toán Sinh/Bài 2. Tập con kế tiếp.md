![image](https://github.com/user-attachments/assets/2af5e3a9-b579-4b1c-a506-e10f871cf97c)

Để sinh tập con kế tiếp, ta cần xét từ cuối của tập đề bài cho với cấu hình cuối cùng. Nếu tại vị trí xét đã đạt mức(n - k + i) là mức mà nó có thể đạt được thì pass còn không thì dừng. Sau đó sẽ tăng lên 1 tại vị trí chưa đạt mức, rồi các vị trí tiếp theo tăng theo số vừa tăng.

```
n = 5; k = 8

1 3 6 7 8 | 4 5 6 7 8

thì ở đây vị trí 2 chưa đạt mức tối đa là 5 nên sẽ tăng lên 1, còn các vị trí còn lại theo số vừa tăng lên 1

1 4 5 6 7

Ta phải tăng các số sau, vì tập con tăng dần, thằng đằng sau luôn bé hơn đằng trước
```

```cpp
#include<bits/stdc++.h>

int a[10000],k,n,final = 0;

using namespace std;
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
  for(int i = 1;i <= k; i++){
    cin >> a[i];
  }
  sinh();
  if(final == 1){
    for(int i = 1; i <= k; i++){
      cout << i << " ";
    }
  }else{
    for(int i = 1; i <= k; i++){
      cout << a[i] << " ";
    }
  }
}
```


![image](https://github.com/user-attachments/assets/89f2f379-080e-454d-96ad-3455c23fc090)

Cách làm bài này là mình sẽ tìm số lớn hơn mà nhỏ nhất.Ta bắt đầu duyệt từ cuối a[n - 1], tìm a[i] < a[i + 1], rồi xét tiếp trong khoảng số nào lớn hơn số a[i] đầu tiên, sau đó đổi chổ 2 số đó, kế tiếp là mình reverse cái số trong khoảng đó. Ví dụ:

```
3 1 2 6 9 8 7 5 4

Bây giờ bắt đầu từ 5, tiếp tục xét thì tới số 6, ta thấy là 6 < 9. Bởi vì điều kiện vòng while là a[i] > a[i + 1] nên chắc chắn dãy mà mình xét, hay xét qua rồi là 1 dãy tăng dần bắt đầu từ cuối, nên tiếp tục duyệt thì thấy số 7 là số lơn hơn 6 đầu tiên 

3 1 2 7 9 8 6 5 4

Cuối cùng là reverse từ số 7 đến cuối, vì mình tìm số lớn hơn nhỏ nhất mà

3 1 2 7 4 5 6 8 9

```
```cpp
#include<bits/stdc++.h>

using namespace std;
int n,a[10005], final = 0;
void ktao(){
    for(int i = 1; i <= n; i++){
      a[i] = i;
    }
}

void sinh(){
    int i = n - 1;
    while(i >= 1 && a[i] > a[i + 1]){
      --i;
    }
    if(i == 0){
        final = 1;
    }else{
        int j = n;
        while(a[i] > a[j]){
          --j;
        }
        swap(a[i], a[j]);
        reverse(a + i + 1, a + n + 1);
    }
}
int main(){
    cin >> n;
    for(int i = 1; i <= n; i++){
      cin >> a[i];
    }
    sinh();
    if(final == 1){
      for(int i = 1; i <= n; i++) cout << i << " ";
    }else{
      for(int i = 1; i <= n; i++) cout << a[i] << " ";
    }
}
```



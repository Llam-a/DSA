![image](https://github.com/user-attachments/assets/5571b5e4-5863-4dec-8a22-9b879c2bdac1)

Để sinh xâu kế tiếp của xâu nhị phân thì ta bắt đầu duyệt từ cuối, bit 1 thì đổi thành bit 0, nhưng khi gặp bit 0 thì dừng và đổi thành bit 1, không duyệt tiếp nữa.

```cpp
#include<bits/stdc++.h>

using namespace std;

string s;
int final = 0;
int main(){
  cin >> s;
  int n = s.size() - 1;// vì trong string bắt đầu từ 0 đến s.size() - 1
  int i = n;
  while(i >= 0 && s[i] == '1'){
    s[i] = '0';
    i--;
  }
  if(i == -1){
    cout << s << endl;
  }else{
    s[i] = '1';
    cout << s << endl;
  }
}
```

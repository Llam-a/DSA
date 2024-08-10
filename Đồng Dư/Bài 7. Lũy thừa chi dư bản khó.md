![image](https://github.com/user-attachments/assets/dc5fa4c2-2994-478b-b082-a6182c5556e0)

Bài này mình dùng lũy thừa nhị phân để làm

![image](https://github.com/user-attachments/assets/8d6419e4-6abf-4073-af84-2671cab72214)

Ví dụ như trên thì 2^25 = 2^12 * 2^6 * 2^3 * 2^1 * 2^0.

Ý tưởng là mình sẽ sử dụng đệ quy để chẻ đôi như trên.Sau khi chạy tới mũ là 0 thì là = 1 sau đó thì tính lũy thừa trước. Kèm theo là kiểm tra số mũ rồi áp dụng công thức, đồng thời chia dư
Ban đầu nó sẽ chẻ đôi tới khi b = 1 return 1, khi đó thì thằng tmp trong cái hàm powmod(2,1) thì nó mới bắt đầu xuống dòng if để tính, tương tự những lần tiếp theo 
```cpp
#include<bits/stdc++.h>

using namespace std;
using ll = long long;
const int mod = 1000000007;
long long powmod(long long a, long long b, long long c){
  if(b == 0){
    return 1;
  }
  long long tmp = powmod(a, b / 2, c); // vòng đệ quy để lưu vào tmp
  if(b % 2 == 0){
    return (tmp % c) * (tmp % c) % c;// vd: 2^14= 2^7 * 2^7
  }else{
    return (tmp % c) * (tmp % c) % c * (a % c) % c;// vd: 2^15 = 2^7 * 2^7 * 2
  }
}
/* a = 2, b = 25
4096 * 4096 * 2 = 2^25
powmod(2,25) -> powmod(2,12) = 4096
powmod(2,12) -> powmod(2,6) = 64
powmod(2,6) -> powmod(2,3) = 8
powmod(2,3) -> powmod(2,1) = 2
powmod(2,1) -> powmod(2,0) = 1 => tmp : powmod(2,1) = 1 => return 1 * 1 * 2 = 2
*/
int main(){
  int a,b; cin >> a >> b;
  cout << powmod(a % 1000000007, b, 1000000007);
}
```

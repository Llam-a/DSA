![image](https://github.com/user-attachments/assets/803cea64-7542-4fa1-9869-e93a89faecfe)

```cpp
#include<bits/stdc++.h>

using namespace std;
int n,k,s;
int x[1000], sum = 0,ans = 0;
void nhap(){
    cin >> n >> k >> s;
}
void Try(int i, int index){
    for(int j = index; j <= n; j++){
        x[i] = j;
        sum += j;
        if(sum == s && i == k){
            ++ans;
        }else if(sum < s && i < k){
            Try(i + 1, j + 1);
        }
        sum -= j;
    }
}
int main(){
    nhap();
    Try(1,1);
    cout << ans;
    
}
```

Biến i: đại diện cho vị trí phần tử thứ i trong tập hợp.

Biến index: là giá trị bắt đầu để chọn phần tử tiếp theo (tránh lặp lại phần tử đã chọn).

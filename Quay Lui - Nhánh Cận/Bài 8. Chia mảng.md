![image](https://github.com/user-attachments/assets/9335af1c-7a9a-4ebe-aede-0ad5e7947b9d)

![image](https://github.com/user-attachments/assets/a5f75c80-15ee-4969-b7aa-3994e84ef7bd)

Bài này yêu cầu ta in ra 1 nếu có thể có k tập hợp có tổng bằng nhau, in ra 0 thì ngược lại.

Đầu tiên,thì mình cần tìm tổng mà các tập con có thể có khi chia ra là.

Sau đó thì cứ quay lui như bình thượng, ++ nếu có tập hợp có tổng bằng tổng tìm từ trước.
```cpp
#include <bits/stdc++.h>

using namespace std;

using ll = long long;

int n, k, a[1005], used[1005], sum = 0, tong = 0, cnt = 0;

void input(){
    cin >> n >> k;
    for(int i = 1; i <= n; i++){
        cin >> a[i];
        sum += a[i];
    }
    sum /= k;
}

void BT(int i, int start){
    for(int j = start; j <= n; j++){
            tong += a[j];
            if(tong == sum){
                cnt++;
            }
            else if(tong < sum){
                BT(i + 1, j + 1);
            }
            tong -= a[j];
    }
}
int main(){
    input();
    BT(1, 1);
    if(cnt == k) cout << 1 << endl;
    else cout << 0 << endl;
    return 0;
}
```

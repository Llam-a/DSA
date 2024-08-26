![image](https://github.com/user-attachments/assets/4dfa91f1-3836-472e-84f5-c43b628ddd5d)

```
Ví dụ :
Input 01
11 3
0 0 0 0 1 0 1 0 0 0 1
Output 01
1
```
Bài này thì dễ, đầu tiên là đi tính tổng, bởi vì dãy 0 và 1 thôi, nên khi tình tổng thì sẽ ra được tổng số cây sống, nếu số cây sống mà < k thì kết thúc cout -1

Sau đó đi đếm số cây sống liên tiếp - tổng số cây sống trong cửa sổ đầu tiên.Rồi gán nó cho 1 biến khác

Chạy vòng for mới từ a[k] đến a[n-1], ta thêm nó vào cửa sổ hiện tại (cr_cnt += a[i]), đồng thời loại bỏ phần tử đầu tiên của cửa sổ cũ (cr_cnt -= a[i - k]).Đồng thời sau mỗi lần cập nhật cửa sổ, ta so sánh cr_cnt hiện tại với max_cnt và cập nhật max_cnt nếu cần.

Kết quả: Để tạo ra một dãy liên tiếp gồm k cây sống, số lần di chuyển ít nhất cần thiết là k - max_cnt, trong đó max_cnt là số cây sống liên tiếp lớn nhất tìm được.


```cpp
#include<bits/stdc++.h>

using namespace std;

int main(){
    int n,k;cin >> n >> k;
    int sum = 0;
    int a[n];
    for(int &x : a){
        cin >> x;
        sum += x;
    }
    if(sum < k){
        cout << -1;
        return 0;
    }
    int cr_cnt = 0;
    for(int i = 0; i < k; i++){
        cr_cnt += a[i]; // dem;
    }
    int max_cnt = cr_cnt;
    for(int i = k; i < n; i++){
        cr_cnt += a[i];
        cr_cnt -= a[i - k];
        max_cnt = max(max_cnt, cr_cnt);
    }
    cout << k - max_cnt << endl;
}
```

![image](https://github.com/user-attachments/assets/9d70b59f-2300-4f2b-9f9a-6325d215bcad)

Bài này thì mình sẽ lưu vào mảng, sau đó thì tạo unordered_set, rồi duyệt mảng tìm tìm a[i] đã có trong set chưa, có thì cout YES.Không có thì mình insert vào set, nếu chỉ số của phần tử hiện tại lớn hơn hoặc bằng K, loại bỏ phần tử đã vượt quá khoảng cách K trong set.Nếu duyệt hết mảng mà không thấy phần tử thích hợp thì cout ra NO

```cpp
#include<bits/stdc++.h>

using namespace std;

int main(){
    int n,k;cin >> n >> k;
    vector<int> v(n);
    for(int i = 0; i < n; i++){
        cin >> v[i];
    }
    unordered_set<int> window;

    for(int i = 0; i < n; i++){
        if(window.find(i) != window.end()){
            cout << "YES";
            return 0;
        }
        window.insert(v[i]);
//đảm bảo rằng các phần tử nằm ngoài khoảng cách K sẽ bị loại bỏ khỏi unordered_set
        if(i >= k){
            window.erase(v[i]);
        }
    }

    cout << "NO";
    return 0;
}
```

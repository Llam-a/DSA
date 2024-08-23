![image](https://github.com/user-attachments/assets/435cc97d-1cdd-4a84-9100-90e38d77dcc8)

Để giải quyết bài toán này, chúng ta sẽ sử dụng kỹ thuật Sliding Window (cửa sổ trượt) để tìm xâu con dài nhất mà không có ký tự nào bị lặp lại.

# Ý tưởng:
- Ta sẽ sử dụng hai con trỏ left và right để xác định cửa sổ trượt.

- Khi mở rộng cửa sổ bằng cách di chuyển con trỏ right, ta sẽ kiểm tra xem ký tự tại vị trí right đã có trong cửa sổ chưa.

- Nếu ký tự chưa xuất hiện trong cửa sổ, ta tiếp tục mở rộng cửa sổ.

- Nếu ký tự đã xuất hiện, ta thu hẹp cửa sổ bằng cách di chuyển con trỏ left để loại bỏ các ký tự cho đến khi xâu con trở thành hợp lệ (không chứa ký tự trùng lặp).

- Với mỗi xâu con hợp lệ, ta tính toán độ dài và cập nhật độ dài dài nhất tìm được.

```cpp
#include<bits/stdc++.h>

using namespace std;
int maxstring(string s){
    set<char> se;
    int l = 0, r = 0;
    int max_length = 0;
    
    while(r < s.size()){
        char r_char = s[r];

        while(se.find(r_char) != se.end()){
            se.erase(s[l]);
            l++;
        }
        se.insert(r_char);
        max_length = max(max_length, r - l + 1);

        r++;
    }
    return max_length;
}
int main(){
    string s; cin >> s;
    int res = maxstring(s);
    cout << res << endl;
}
```

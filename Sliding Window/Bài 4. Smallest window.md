![image](https://github.com/user-attachments/assets/b8d3b983-c7f3-4422-8d59-3f378d153b5d)

Bài này mình sử dụng hai con trỏ để mở rộng và thu hẹp

Ban đầu phải xác định có bao nhiêu kí tự khác nhau, sau đó tạo map để xem kí tự nào đã xuất hiện chưa.

Tiếp theo là mở rộng,duyệt từng kí tự của chuỗi cho đến khi đủ kí tự khác nhau.Sau khi đủ kí tự khác nhau, ta tiến hành thu hẹp nó.Xóa từng kí tự,nếu xóa xong mà kí tự đó trong mảng còn 0 thì trừ đi các kí tự khác nhau và tiếp tục mở rộng để tìm chuỗi ngắn nhất có đầy đủ khác nhau.

Bởi vì đề là chuỗi ngắn nhất nên ta cần phải chạy hết chuỗi, để xác định được hết.

```cpp
#include<bits/stdc++.h>

using namespace std;
int minstring(string s){
    set<char> se(s.begin(), s.end());
    map<char, int> mp;
    int l = 0, r = 0;
    int min_length = INT_MAX;
    int cr_cnt = 0;

    while(r < s.size()){
        char r_char = s[r];
        mp[r_char]++;

        if(mp[r_char] == 1){
            cr_cnt++;
        }
        while(cr_cnt == se.size()){
        min_length = min(min_length,r - l + 1);
        char l_char = s[l];
        mp[l_char]--;
        if(mp[l_char] == 0){
            cr_cnt--;
        }
        ++l;
    }
    ++r;
    }
    return min_length;
}
int main(){
    string s;cin >> s;
    int res = minstring(s);
    cout << res << endl;
}
```

![image](https://github.com/user-attachments/assets/174558cb-58ca-451a-982e-dda52a50ea2d)

Để giải bài toán này, chúng ta có thể sử dụng thuật toán cửa sổ trượt (sliding window) để tìm xâu con nhỏ nhất của S chứa đầy đủ mọi kí tự của T. Ý tưởng chính là duy trì một cửa sổ có thể mở rộng và thu nhỏ để bao gồm tất cả các ký tự trong T một cách tối thiểu nhất.

# Chi tiết giải thuật:

## Khởi tạo bộ đếm cho xâu T: Sử dụng một mảng đếm (hoặc map) để lưu trữ tần số xuất hiện của mỗi ký tự trong T.

## Thuật toán cửa sổ trượt:

- Duy trì một cửa sổ trên xâu S.

- Mở rộng cửa sổ đến khi nào cửa sổ chứa đủ các ký tự của T.

- Khi cửa sổ đã chứa đủ, cố gắng thu hẹp nó để tìm ra cửa sổ nhỏ nhất chứa đủ các ký tự của T.

## Kết quả:

- Lưu trữ cửa sổ nhỏ nhất tìm được và in ra.
- Nếu không tìm được xâu con nào thoả mãn, in ra -1.

```cpp
#include<bits/stdc++.h>

using namespace std;

string cuaso(string s, string t){
    unordered_map<char, int> t_freq,res_freq;

    for(char c : t){
        t_freq[c]++;
    }

    int required = t_freq.size();
    int cr_cnt = 0;

    int l = 0, r = 0;
    int min_length = INT_MAX;
    int start = 0;

    while(r < s.size()){
        char c = s[r];
        res_freq[c]++;

        if(t_freq.find(c) != t_freq.end() && res_freq[c] == t_freq[c]){
            ++cr_cnt;
        }

        while(l <= r && cr_cnt == required){
            if(r - l + 1 < min_length){
                min_length = r - l + 1;
                start = l;
            }
            
            char left_char = s[l];
            res_freq[left_char]--;

            if(t_freq.find(left_char) != t_freq.end() && res_freq[left_char] < t_freq[left_char]){
                cr_cnt--;
            }

            ++l;
        }
        ++r;
    }
    return (min_length == INT_MAX) ? "-1" :  s.substr(start,min_length);

}

int main(){
    string s,t; cin >> s >> t;
    string res = cuaso(s,t);
    cout << res << endl;
}
```

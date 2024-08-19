![image](https://github.com/user-attachments/assets/a97de6b9-e0df-4833-afca-f952be4e0f70)

Bài này mình sinh hoán vị kế tiếp

Lưu ý là để yêu cầu là theo thứ tự từ điển nữa nên mình phải sort

```cpp
#include<bits/stdc++.h>

using namespace std;

int main(){
    int n; cin >> n;
    vector<string> s(n);
    for(int i = 0; i < n; i++){
        cin >> s[i];
    }
    sort(s.begin(), s.end());

    do{
        for(int i = 0; i < s.size(); i++){
            cout << s[i] << " ";
        }
        cout << endl;
    }while(next_permutation(s.begin(), s.end()));
    return 0;
}
```

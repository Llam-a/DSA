![image](https://github.com/user-attachments/assets/2825f964-10b0-44b0-b5e2-d34bcd2c81a5)

```
Ví dụ :
Input 01
3
Output 01
321
312
231
213
132
123
```

Bài này là thuộc sinh hoán vị

```cpp
#include<bits/stdc++.h>

using namespace std;
int a[1000], n, final = 0;

void ktao() {
    for (int i = 1; i <= n; i++) {
        a[i] = i;
    }
}

void sinh() {
    int i = n - 1;
    while (i >= 1 && a[i] > a[i + 1]) {
        i--;
    }
    if (i == 0) {
        final = 1;
    } else {
        int j = n;
        while (a[i] > a[j]) j--;
        swap(a[i], a[j]);
        reverse(a + i + 1, a + n + 1);
    }
}

int main() {
    cin >> n;
    ktao();
    vector<vector<int>> v;
    while (final == 0) {
        vector<int> tmp(a + 1, a + n + 1);
        v.push_back(tmp);
        sinh();
    }

    for (int i = v.size() - 1; i >= 0; i--) {
        for (int j = 0; j < v[i].size(); j++) {
            cout << v[i][j];
        }
        cout << endl;
    }
}
```
```

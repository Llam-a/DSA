![image](https://github.com/user-attachments/assets/7f6f032a-c7ce-4033-bff0-9821543cdfbc)

![image](https://github.com/user-attachments/assets/49813fda-1d8e-4e3b-995c-b18aa1b1b94a)

```cpp
#include<bits/stdc++.h>

using namespace std;
int n, a[100][100];
string s;
void Try(int i, int j){
    if(i == n && j == n){
        cout << s << endl;
        return;
    }
    if(i + 1 <= n && a[i + 1][j] == 1){
        s += "D";
        Try(i + 1, j);
        s.pop_back();
    }
    if(j + 1 <= n && a[i][j + 1] == 1){
        s += "R";
        Try(i, j + 1);
        s.pop_back();
    }
}
int main(){
    cin >> n;
    for(int i = 1; i <= n; i++){
        for(int j = 1; j <= n; j++){
            cin >> a[i][j];
        }
    }
    Try(1,1);
}
```

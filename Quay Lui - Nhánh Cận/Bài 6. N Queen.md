![image](https://github.com/user-attachments/assets/f361523c-346a-4d40-9f3a-467758b440ce)

![image](https://github.com/user-attachments/assets/e333648a-4391-488e-b2c8-db5bab148f2c)

Cây đệ quy cho bài toán này

![image](https://github.com/user-attachments/assets/92b149d0-1431-4dad-9d64-55cf88c5d95e)

[Reference](https://www.geeksforgeeks.org/n-queen-problem-using-branch-and-bound/)

Thì mình sẽ đánh dấu đường đi của con hậu gồm vị trí của nó đang đứng là x[i] = j, và đường chéo xuôi và ngược.Sau đó thì reset lại để thử những đệ quy khác.

```cpp
#include<bits/stdc++.h>

using namespace std;

int n,x[1000],cnt= 0;
int cot[100], xuoi[100], nguoc[100];

void Try(int i){
    for(int j = 1; j <= n; j++){
        if(cot[j] == 0 && xuoi[i - j + n] == 0 && nguoc[i + j - 1] == 0){
            x[i] = j;
            cot[j] = xuoi[i - j + n] = nguoc[i + j - 1] = 1;
            if(i == n){
                ++cnt;
            }else{
                Try(i + 1);
            }
            cot[j] = xuoi[i - j + n] = nguoc[i + j - 1] = 0;
        }
    }
}
int main(){
    cin >> n;
    Try(1);
    cout << cnt << endl;
}
```

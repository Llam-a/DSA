![image](https://github.com/user-attachments/assets/0cd297ab-5c87-4d74-a10b-23d8af6fc5c8)

![image](https://github.com/user-attachments/assets/ec7803c5-7d97-4f26-93b8-6fd253275dc5)

Bài này khá giống bài 1

```cpp
#include<bits/stdc++.h>

using namespace std;
int x[1000],n,k,a[100];
void nhap(){
    cin >> n >> k;
    for(int i = 1; i <= n; i++){
        cin >> a[i];
    }
    sort(a + 1, a + n + 1);
}
void Try(int i, int init, int sum){
    for(int j = init; j <= n; j++){
        x[i] = a[j];
        sum += a[j];
        if(sum == k){
            cout << "[";
            for(int l = 1; l <= i; l++){
                cout << x[l];
                if(l == i){
                    cout << "]\n";
                }else{
                    cout << " ";
                }
            }
        }else if(sum < k){
            Try(i + 1, j + 1, sum);
        }
        sum -= a[j];
    }
}
int main(){
    nhap();
    Try(1,1,0);
}
```


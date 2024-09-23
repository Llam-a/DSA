![image](https://github.com/user-attachments/assets/cf3a6ba9-e992-482b-b12e-1a2fd8a3c3a3)

```cpp
#include<bits/stdc++.h>

using namespace std;
long long F[100];
char find(long long n, long long k){
    if(n == 1){
        return 'A';
    }
    if(n == 2){
        return 'B';
    }
    if(k <= F[n - 2]){
        return find(n - 2, k);
    }else{
        return find(n - 1, k - F[n - 2]);
    }

}
int main(){
    F[0] = 0; F[1] = 1;
    for(int i = 2; i <= 92; i++){
        F[i] = F[i - 1] + F[i - 2];
    }
    long long n,k;cin >> n >> k;
    cout << find(n,k) << endl;
}
```

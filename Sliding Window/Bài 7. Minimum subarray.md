![image](https://github.com/user-attachments/assets/978fe8b9-c842-4825-ac2c-9aec4f853d13)

```cpp
#include<bits/stdc++.h>

using namespace std;

int main(){
    int n,k;cin >> n >> k;
    vector<int> a(n);
    for(int i = 0; i < n; i++){
        cin >> a[i];
    }
    int current_sum = 0;
    int start = 0;
    int min_length = INT_MAX;
    int best_start = -1, best_end = -1;

    for(int end = 0; end < n; end++){
        current_sum += a[end];

        while(current_sum >= k){
            if(end - start + 1 < min_length){
                min_length = end - start + 1;
                best_start = start;
                best_end = end;
            }
            // thu gọn cửa sổ để tìm dãy con ngắn hơn
            current_sum -= a[start];
            start++;
        }
    }
    if(best_start == -1){
        cout << -1 << endl;
    }else{
        for(int i = best_start; i <= best_end; i++){
            cout << a[i] << " ";
        }
        cout << endl;
    }
    

}
```

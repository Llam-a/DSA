![image](https://github.com/user-attachments/assets/83bfb89c-9d73-484b-8345-793046527dc0)

```
Ví dụ :
Input 01
59 4
72 39 5 74 29 83 63 67 69 10 50 86 32 66 96 100 47 32 41 96 9 7 58 97 87 26 21 23 100 52 31 76 43 74 17 72 104 40 99 8 16 27 38 78 69 46 16 58 73 52 49 67 62 42 64 28 46 34 83
Output 01
315
72 104 40 99
```

Bài này dùng cửa sổ trượt là được

```cpp
#include <iostream>
#include <vector>
#include <limits.h>

using namespace std;

int main() {
    int N, K;
    cin >> N >> K;

    vector<int> A(N);

    for (int i = 0; i < N; i++) {
        cin >> A[i];
    }

    // Tính tổng của K phần tử đầu tiên
    long long current_sum = 0;
    for (int i = 0; i < K; i++) {
        current_sum += A[i];
    }

    long long max_sum = current_sum;
    int start_index = 0;

    // Sử dụng kỹ thuật Sliding Window để tìm tổng lớn nhất của dãy con K phần tử
    for (int i = K; i < N; i++) {
        current_sum += A[i] - A[i - K]; // Trượt cửa sổ
        if (current_sum > max_sum) {
            max_sum = current_sum;
            start_index = i - K + 1;
        }
    }

    // In ra kết quả
    cout << max_sum << endl;
    for (int i = start_index; i < start_index + K; i++) {
        cout << A[i] << " ";
    }
    cout << endl;

    return 0;
}
```

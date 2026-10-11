#include <iostream>
using namespace std;

int divisorSum(int n) {
    int sum = 0;

    for (int i = 1; i < n; i++) {
        if (n % i == 0) {
            sum += i;
        }
    }

    return sum;
}

int main() {
    int L, R;

    while (cin >> L >> R) {
        if (L == 0 && R == 0)
            break;

        int count = 0;

        for (int i = L; i <= R; i++) {
            int a = divisorSum(i);
            int b = divisorSum(a);

            if (a > i && a <= R && a >= L && b == i) {
                count++;
            }
        }

        cout << count << endl;
    }

    return 0;
}

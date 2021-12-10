# 再帰関数

## 再帰関数

### 例題 1. 階乗

````C
#include <stdio.h>

int factorial(int n);

int main(void) {
  int n;
  printf("input n : ");
  scanf("%d", &n);

  printf("%d! = %d\n", n, factorial(n));

  return 0;
}

int factorial(int n) {
  if (n == 0) {
    return 1;
  } else {
    return n * factorial(n - 1);
  }
}
````

[実行例]

````
input n : 10
10! = 3628800

````

### 2つの負でない整数の最大公約数を再帰により求める

````
#include <stdio.h>

int gcd(int m, int n);

int main(void) {
  int m = 24;
  int n = 18;

  int gcd_answer = gcd(m, n);
  printf("gcd(%d, %d) = %d\n", m, n, gcd_answer);

  return 0;
}

int gcd(int m, int n) {
  printf("<gcd(%d, %d) is called>\n", m, n);

  if (n == 0) {
    return m;
  } else {
    return gcd(n, m % n);
  }
}
````

[実行例]
````
<gcd(24, 18) is called>
<gcd(18, 6) is called>
<gcd(6, 0) is called>
gcd(24, 18) = 6

````

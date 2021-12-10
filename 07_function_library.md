
## 数学関数 math.h

math.h をインクルードし、数学関数を用いる時は
コンパイル時にリンクオプション -lm が必要となる(場合がある)。

````
$ gcc -o sqrt sqrt.c -lm
````

### 例題1. 平方根

````C
#include <stdio.h>
#include <math.h>

int main(void) {
  for (double x = 0.0; x < 5.1; x += 0.5) {
    printf("sqrt(%6.3lf) = %6.3lf\n", x, sqrt(x));
  }
  return 0;
}
````

[実行例]
````
sqrt( 1.000) =  1.000
sqrt( 1.500) =  1.225
sqrt( 2.000) =  1.414
sqrt( 2.500) =  1.581
sqrt( 3.000) =  1.732
sqrt( 3.500) =  1.871
sqrt( 4.000) =  2.000
sqrt( 4.500) =  2.121
sqrt( 5.000) =  2.236

````

### 例題2. 三角関数

````C
#include <stdio.h>
#include <math.h>

int main(void) {

  printf("    degree,    radian,       cos\n");
  printf("--------------------------------\n");
  
  for (double theta_degree = -180.0; theta_degree < 180.1; theta_degree += 30.0) {
    double theta_radian = 2 * M_PI * (theta_degree / 360);
    printf("%10.4lf,%10.4lf,%10.4lf\n", theta_degree, theta_radian, cos(theta_radian));
  }

  return 0;
}
````

[実行例]
````
    degree,    radian,       cos
--------------------------------
 -180.0000,   -3.1416,   -1.0000
 -150.0000,   -2.6180,   -0.8660
 -120.0000,   -2.0944,   -0.5000
  -90.0000,   -1.5708,    0.0000
  -60.0000,   -1.0472,    0.5000
  -30.0000,   -0.5236,    0.8660
    0.0000,    0.0000,    1.0000
   30.0000,    0.5236,    0.8660
   60.0000,    1.0472,    0.5000
   90.0000,    1.5708,    0.0000
  120.0000,    2.0944,   -0.5000
  150.0000,    2.6180,   -0.8660
  180.0000,    3.1416,   -1.0000

````

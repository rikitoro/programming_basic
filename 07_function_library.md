
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


````C
#include <stdio.h>
#include <string.h>

int main(void) {
  char first_part[100] = "The quick brown fox ";
  char last_part[100] = "jumps over the lazy dog";

  printf("%s/ %d letters\n", first_part, strlen(first_part));
  printf("%s/ %d letters\n", last_part, strlen(last_part));

  strcat(first_part, last_part);

  printf("%s/ %d letters\n", first_part, strlen(first_part));
  printf("%s/ %d letters\n", last_part, strlen(last_part));

  return 0;
}
````

[実行例]
````
The quick brown fox / 20 letters
jumps over the lazy dog/ 23 letters
The quick brown fox jumps over the lazy dog/ 43 letters
jumps over the lazy dog/ 23 letters

````

````C
#include <stdio.h>

int main(int argc, char *argv[]) {

  printf("argc = %d\n", argc);

  for (int i = 0; i < argc; ++i){
    printf("argv[%d] = %s\n", i, argv[i]);
  }
  
  return 0;
}
````

[実行例] この例では実行ファイル名を a.out とした。
````
$ ./a.out hello cats 22 3.14
argc = 5
argv[0] = \a.out
argv[1] = hello
argv[2] = cats
argv[3] = 22
argv[4] = 3.14

````


````C
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char *argv[]) {
  if (argc < 3) {
    printf("Specify two integer-valued command line arguments.\n");
    printf("USAGE: ./a.out 31 41\n");
    exit(1);
  }

  int num1  = atoi(argv[1]);
  int num2  = atoi(argv[2]);

  printf(" %d + %d = %d\n", num1, num2, num1 + num2);

  return 0;
}
````

[実行例]
````
$ ./a.exe 27 18
 27 + 18 = 45

````

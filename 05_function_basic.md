## 例題 1. 入力された整数値の二乗を計算して返す関数

````C
#include <stdio.h>

int square(int n);

int main(void) {

  int result;
  
  result = square(3);
  printf("square(3) = %d", result);
  
  for (int i = -3; i < 4; ++i) {
      result = square(i);
      printf("square(%d) = %d", i, result);
  }
  
  return 0;
}

int square(int n) {
  return n * n;
}
````

実行例:
````
square(10) = 9
square(-3) = 9
square(-2) = 4
square(-1) = 1
square(0) = 0
square(1) = 1
square(2) = 4
square(3) = 9
````

---

## 例題 2. 半径が与えられると円の面積を計算して返す関数

````C
#include <stdio.h>

#define PI 3.14

double area_of_circle(double radius);

int main(void) {

  double r;
  
  scanf("%lf", &r);
  printf("Area of circle with radius %.2f : %.2f \n", r, area_of_circle(r));
  return 0;
}

double area_of_circle(double radius) {
  double area = PI * radius * radius;
  return area;
}
````

実行例：
````
>5.0
Area of circle with radius 5.00 : 78.50 
````

---

### 例題 3 Hello! How are you? と表示する手続き(void 関数)


````
#include <stdio.h>

void hello(void);

int main(void) {

  hello();

  return 0;
}


void hello(void) {
  printf("Hello!\n");
  printf("How are you?\n");
}
````

実行例:
````
Hello!
How are you?
````

### 例題 4. m, nを入力すると、n行m列の長方形領域を * で埋める手続き(void 関数)

```C
#include <stdio.h>

void draw_rectangle(int m, int n);

int main(void) {

  int m, n;

  scanf("%d",&m);
  scanf("%d",&n);

  draw_rectangle(m, n);

  return 0;
}


void draw_rectangle(int m, int n) {
  for (int i = 0; i < m; ++i) {
    for (int j = 0; j < n; ++j) {
      printf("*");
    }
    printf("\n");
  }
}
````

実行例：
````
>5
>8
********
********
********
********
********
````

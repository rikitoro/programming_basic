## 例題 1.

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

## 例題 2.

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


````
>5.0
Area of circle with radius 5.00 : 78.50 
````

---

### 例題 3.
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

````
>5
>8
********
********
********
********
********
````

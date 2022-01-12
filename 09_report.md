レポート課題参考用

````C
#include <stdio.h>
#define N 10
#define M 20

double summation(double x[], int n);

int main() {
  double x[N] = {
     0.388020, -2.330276, 0.745467, -0.351828, 0.929643,
    -0.391519,  0.345324, 1.949394,  0.108415, 0.112288 };
  double y[M] = {
    5.473349, -0.931143, -1.543251,  6.510520,  6.115552,
    2.703508, 11.378085, -1.039719, -6.118450,  7.511876,
    3.384840,  8.700659,  4.757697,  3.529336, -0.951917,
    1.798911, 10.200031,  3.218543,  3.203289,  0.096445 };

  printf("sum of x: %lf\n", summation(x, N));
  printf("sum of y: %lf\n", summation(y, M));

  return 0;
}


double summation(double x[], int n) {
  double sum = 0.0;
  for (int i = 0; i < n; ++i) {
    sum += x[i];
  }
  return sum;
}
````

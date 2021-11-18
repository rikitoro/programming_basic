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
}

int square(int n) {
  return n * n;
}
````

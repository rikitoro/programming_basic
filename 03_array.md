````c
#include <stdio.h>

#define MAX_NUM 100

int main()
{
  int score[MAX_NUM];
  int num;
  
  // input number of students
  scanf("%d", &num);
  // input score of students
  for (int i = 0; i < num; ++i) {
    scanf("%d", &score[i]);
  }
  
  // output scores in reverse order
  printf("\n*reverse order*\n");
  for (int i = num - 1; i >= 0; --i) {
    printf("%d ", score[i]);
  }
  printf("\n");
    
    
  return 0;
}
````

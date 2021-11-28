## 例題 1. 変数の参照を渡すとその変数に 42 を加算する関数

````C
#include <stdio.h>

void add_42(int* x);

int main(void) {
  int num = 100;

  printf("num = %d\n", num);

  add_42(&num);  

  printf("add_42(&num) was called.\n");
  printf("num = %d\n", num);

  return 0;
}

void add_42(int* x) {
  *x += 42;
}
````

実行例:
````
num = 100
add_42(&num) was called.
num = 142
````

---

## 例題 2. 2つの変数の参照を渡すと、変数の値を入れ替える関数

````C
#include <stdio.h>

void swap(int* x, int* y);

int main(void) {

  int x = 3, y = 4;

  printf("x = %d, y = %d\n", x, y);

  swap(&x, &y);

  printf("swap(&x, &y) was called\n");
  printf("x = %d, y = %d\n", x, y);

  return 0;
}

void swap(int* x, int* y){
  int tmp;

  tmp = *x;
  *x = *y;
  *y = tmp;
}
````

実行例:
````
x = 3, y = 4
swap(&x, &y) was called
x = 4, y = 3
````

---

## 例題 3. 実数型の配列とその配列の要素数を渡すと、平均値を計算して返す関数

````C
#include <stdio.h>

#define N 10 // array size

double average(double* xs, int n);
// double average(double xs[], int n);

int main(void) {
  double score[N] = {
    3.1, 4.1, 5.9, 2.6, 5.3,
    5.8, 9.7, 9.3, 2.3, 8.4
  };
  double average_score;

  average_score = average(score, N);
  printf("average score : %6.2f", average_score);

  return 0;
}

double average(double* xs, int n) {
  double sum = 0.0;
  for (int i = 0; i < n; i++){
    sum += xs[i];
  }
  
  return sum / n;
}
````

実行例:
````
average score :   5.65
````

----

## 課題 1. 配列の最大要素を返す関数

実数型の配列 xs 配列の要素数 n を渡すと、配列の要素中で最大の値を求めて返す関数
`double max(double* xs, int n)` を作成し、その動作を確認せよ。

以下は動作確認のための検証用プログラムとその実行例である。

検証用プログラム:
````C
#include <stdio.h>

#define N 10 // array size

double max(double* xs, int n);

int main(void) {
  double score[N] = {
    3.1, 4.1, 5.9, 2.6, 5.3,
    5.8, 9.7, 9.3, 2.3, 8.4
  };

  printf("max score : %6.2f", max(score, N));

  return 0;
}

// implement max(double* xs, int n);
````

実行例:
````
max score :   9.70
````

## 例題 1. 変数の参照を渡すとその変数に 42 を加算する関数

````C
#include <stdio.h>

void add_42(int* x); // int型の変数の参照を受け取る(int型の変数の参照の型は int* と指定する)

int main(void) {
  int num = 100; // int型の変数 num

  printf("num = %d\n", num);

  add_42(&num); // 変数 num の参照を渡す。変数 num の参照は &num と表す。

  printf("add_42(&num) was called.\n");
  printf("num = %d\n", num);

  return 0;
}

void add_42(int* x) { // int型の変数の参照 x を受け取る
  *x += 42; // 参照 x が示す変数(値)自体は *x で表す。(*x で int 型の変数だと考えるとよい)
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

  int x = 3, x = 4; // int型の変数 x, y

  printf("x = %d, x = %d\n", x, x);

  swap(&u, &v); // int型の変数 x, y への参照は &x, &y で表す。

  printf("swap(&x, &y) was called\n");
  printf("x = %d, y = %d\n", x, y);

  return 0;
}

void swap(int* x, int* y){ // int型の参照 x, yを受け取る。
  int tmp;

  tmp = *x; // 参照 x が示す変数(値)自体は *x で表す。
  *x = *y;
  *y = tmp;
}
````

実行例:
````
x = 3, y = 4
swap(&u, &v) was called
x = 4, y = 3
````

---

## 例題 3. 実数型の配列とその配列の要素数を渡すと、平均値を計算して返す関数

````C
#include <stdio.h>

#define N 10 // array size

double average(double* xs, int n);　     // double型の配列を受け取るときは double* 型を指定する  
// double average(double xs[], int n);   // このように指定してもよい

int main(void) {
  double score[N] = {
    3.1, 4.1, 5.9, 2.6, 5.3,
    5.8, 9.7, 9.3, 2.3, 8.4
  };
  double average_score;

  average_score = average(score, N); // 配列を渡すときは配列名を用いる
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

## 複数ファイルのコンパイル

関数 prod を定義したソースファイル: prod.c
````C
int prod(int x[], int n) {
  int result = 1;
  for (int i = 0; i < n; ++i) {
    result *= x[i];
  }
  return result;
}
````

関数 prod のプロトタイプ宣言を行うヘッダファイル: prod.h
````h
#pragma once  // ヘッダファイルが1回だけインクルードされるようにする

int prod(int x[], int n);
````

関数 prod を呼び出すコースコード: main.c
````C
#include <stdio.h>
#include "prod.h" // ヘッダファイルをインクルードする

#define N 5

int main() {
  int data[N] = {3, 1, 4, 1, 5};
  printf("%d\n", prod(data, 1));
  printf("%d\n", prod(data, 2));
  printf("%d\n", prod(data, 3));
  printf("%d\n", prod(data, 4));
  printf("%d\n", prod(data, 5));
}
````

コンパイル方法 ソースコードファイル prod.c と main.c を指定する(ヘッダファイルは指定しない)
````
$ gcc -o test main.c prod.c
````

実行例
````
$ ./test
3
3
12
12
60
````

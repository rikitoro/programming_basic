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

コンパイル方法 その1 : 
````
$ gcc -o test main.c prod.c
$ ls
main.c prod.c prod.h test
$ ./test
3
3
12
12
60
````

実行例 その2 : 
-c オプションでオブジェクトファイル(main.o, prod.o)を作ってから
それらをリンクし実行可能ファイルを作成する。
````
$ gcc -c main.c prod.c
$ ls
main.c  main.o  prod.c  prod.h  prod.o
$ gcc -o test main.o prod.o
$ ls
main.c  main.o  prod.c  prod.h  prod.o  test
$ ./test
3
3
12
12
60
````

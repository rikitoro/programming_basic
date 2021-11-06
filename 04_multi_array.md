### 例題1 多次元配列の初期化と表示

````multi_array.c
#include <stdio.h>

#define M 3
#define N 5

int main(void) {
  // initialize multi array data
  int data[M][N] = {
    {11, 12, 13, 14, 15}, // data[0][0]~data[0][4]
    {21, 22, 23, 24, 25}, // data[1][0]~data[1][4]
    {31, 32, 33, 34, 35}  // data[2][0]~data[2][4]
  };

  // output data
  printf("data:\n");
  for (int i = 0; i < M; ++i) {
    for (int j = 0; j < N; ++j) {
      printf("%4d ", data[i][j]);
    }
    printf("\n");
  }

  // output data (transpose)
  printf("transposed data:\n");
  for (int j = 0; j < N; ++j) {
    for (int i = 0; i < M; ++i) {
      printf("%4d ", data[i][j]);
    }
    printf("\n");
  }

}
````

````
data:
  11   12   13   14   15
  21   22   23   24   25
  31   32   33   34   35
transposed data:
  11   21   31
  12   22   32
  13   23   33
  14   24   34
  15   25   35
````

### 例題2. 行列の加算

```` matrix_sum.c
#include <stdio.h>

#define N 5

int main(void) {
  double a[N][N];
  double b[N][N];
  double c[N][N]; // c = a + b

  // input matrix a
  for (int i = 0; i < N; ++i){
    for (int j = 0; j < N; ++j) {
      scanf("%lf", &a[i][j]);
    }
  }

  // input matrix b
  for (int i = 0; i < N; ++i){
    for (int j = 0; j < N; ++j) {
      scanf("%lf", &b[i][j]);
    }
  }

  // calculate matrix sum a + b
  for (int i = 0; i < N; ++i) {
    for (int j = 0; j < N; ++j) {
      c[i][j] = a[i][j] + b[i][j];
    }
  }

  // output matrix sum a + b
  for (int i = 0; i < N; ++i) {
    for (int j = 0; j < N; ++j) {
      printf("%6.2f ", c[i][j]);
    }
    printf("\n");
  }

}
````

```` input_matrix_a_b.dat
1.1 1.2 1.3 1.4 1.5
2.1 2.2 2.3 2.4 2.5
3.1 3.2 3.3 3.4 3.5
4.1 4.2 4.3 4.4 4.5
5.1 5.2 5.3 5.4 5.5
 1.1  0.0  0.0  0.0 -1.5
 0.0  2.2  0.0 -2.4  0.0
 0.0  0.0  0.0  0.0  0.0
 0.0 -4.2  0.0  4.4  0.0
-5.1  0.0  0.0  0.0  5.5
````

````
$ ./matrix_sum < input_matrix_a_b.dat
  2.20   1.20   1.30   1.40   0.00
  2.10   4.40   2.30   0.00   2.50
  3.10   3.20   3.30   3.40   3.50
  4.10   0.00   4.30   8.80   4.50
  0.00   5.20   5.30   5.40  11.00
````


### 課題1. 行列とベクトルの積

5行5列の実行列 A (5次の正方行列)と5行1列の実行列 b (5次の列ベクトル)を与えたとき、A と b の行列積 c = A b を計算し(c は5行1列の実行列)、計算結果 c を標準出力へ出力するプログラムを作成せよ。
ただし、行列 A と b の各要素は以下のように標準入力から入力されるものとする。
- まず、行列 A の各要素を A(1,1), A(1,2), .., A(1,5), A(2,1), A(2, 2), .. A(2, 5), A(3,1), .., A(5,5) という順で与える。ここで、行列 A の i行j列の要素を　A(i,j) (i, j = 1, ..,5) と表記した。
- 次に行列(列ベクトル) bの各要素を b(1), b(2), .., b(5) の順で与える。ここで b の i行1列の要素を b(i) (i = 1, ..,5) と表記した。
なお、計算結果 c の各要素は小数点第二位の桁まで表示すること。

動作例：

入力データ用のテキストファイル matrixAb.dat : 1行目から5行目までは行列 A として入力する各要素の値、5行目から10行目は b として入力する各要素の値を示している。
````
-11.67   -0.53   -8.42    1.41  16.78
  6.36   -0.30   -6.09   -1.93   7.89
  0.14   -1.97   -5.08   -6.27  10.85
  9.11   -0.68   -1.67    3.51   0.40
 -2.74   -3.24    1.34   17.80  -0.23
  1.21
  2.21
  1.83
 -6.47
  1.43
````

実行例：プログラムの実行ファイル名を matmul としている。
````
$ ./matmul < matrixAb.dat
  -15.83
   19.66
   42.60
  -15.67
 -123.52
````

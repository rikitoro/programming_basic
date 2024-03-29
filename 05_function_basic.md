## 例題 1. 入力された整数値の二乗を計算して返す関数

````C
#include <stdio.h>

// 関数プロトタイプ
int square(int n); // 関数の返す型、関数名、引数の型(と引数)を宣言する


int main(void) {

  int result;
  
  result = square(10); // 引数に int 型の値 10 を渡して関数を呼び出す。
                       // 関数の返り値を result で受け取っている。
  printf("square(10) = %d", result);
  
  for (int i = -3; i < 4; ++i) {
      result = square(i); // 引数に int 型の変数 i の値を渡して関数を呼び出す。
      printf("square(%d) = %d", i, result);
  }
  
  return 0;
}

// 関数の定義
int square(int n) { // int型の値 n を受け取り, int型の値を返す関数
  return n * n;     // 受け取った値の二乗を返す。
}

````

実行例:
````
square(10) = 100
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

// マクロ:　コンパイル時(プリプロセス)にプログラム中の変数 PI が
// すべて 3.14 に置き換えられる。
#define PI 3.14

// 関数プロトタイプ宣言
double area_of_circle(double radius); // double 型の値を受け取り、double型の値を返す関数

int main(void) {

  double r;
  
  scanf("%lf", &r);
  printf("Area of circle with radius %.2f : %.2f \n", r, area_of_circle(r));
  return 0;
}

double area_of_circle(double radius) { // double 型の値 radius を受け取る
  double area = PI * radius * radius;
  return area; // double 型の値 area を返す
}
````

実行例：
````
>5.0
Area of circle with radius 5.00 : 78.50 
````

---
## 例題 3. 42 よりも大きな整数値を渡すと 1 を返し、そうでない場合は 0 を返す関数

````C
#include <stdio.h>

int greater_than_42(int x);

int main(void) {

  for (int score = 40; score <= 45; ++score) {
    printf("greater_than_42(%d) = %d\n", score, greater_than_42(score));
  }
  
}

int greater_than_42(int x) {
  if (x > 42) {
    return 1;
  } else {
    return 0;
  } 
}
````

実行例:
````
greater_than_42(40) = 0
greater_than_42(41) = 0
greater_than_42(42) = 0
greater_than_42(43) = 1
greater_than_42(44) = 1
greater_than_42(45) = 1
````

---

## 例題 4. Hello! How are you? と表示する手続き(void 関数)


````C
#include <stdio.h>

void hello(void); // 引数を受け取らず、値を返さない関数

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

## 例題 5. m, nを入力すると、n行m列の長方形領域を * で埋める手続き(void 関数)

```C
#include <stdio.h>

void draw_rectangle_area(int m, int n); // int型の値 m, n を受け取り、値を返さない関数

int main(void) {

  int m, n;

  scanf("%d",&m);
  scanf("%d",&n);

  draw_rectangle_area(m, n);

  return 0;
}


void draw_rectangle_area(int m, int n) {
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

---

## 課題 1. n から m までの和を計算する関数

2つの整数 $n, m$ を引数に与えると、
$n \le m$ の場合は $n$ から $m$ までの和 $S = \displaystyle{\sum_{k=n}^{m} k}$ を返し、
$n > m$ の場合は0を返す関数`int sum(int n, int m)` を作成しその動作を確認せよ。

## 課題 2. テストの点数の評価への変換
次の表はあるテストの点数とその評価の関係を示したものである。

| 点数 | 評価 |
| ---- | ---- |
| 80点以上 | A |
| 80点未満かつ60点以上 | B |
| 60点未満 | C |

テストの点数(整数値) score を渡すと、その評価をあらわす文字('A', 'B', 'C')を返す関数 
`char grade(int score)` を作成し、その動作を確認せよ。

以下は動作確認用の検証用プログラムとその実行例である。

検証用プログラム:
````C
#include <stdio.h>

char grade(int score);

int main(void) {

  printf("grade(95) : %c\n", grade(95));
  printf("grade(80) : %c\n", grade(80));
  printf("grade(79) : %c\n", grade(79));
  printf("grade(72) : %c\n", grade(72));
  printf("grade(60) : %c\n", grade(60));
  printf("grade(59) : %c\n", grade(59));
  printf("grade(20) : %c\n", grade(20));
  
  return 0;
}

// implement grade(int score), here
````

実行例:
````
grade(95) : A
grade(80) : A
grade(79) : B
grade(72) : B
grade(60) : B
grade(59) : C
grade(20) : C
````

## 課題3. m, nを入力すると、n行m列の長方形領域の枠を描画する手続き

2つの整数 m, n を入力すると n行m列の長方形領域の枠を * で描画する手続き
`void draw_rectangle(int m, int n)` を作成しその動作を確認せよ。

実行例：
````
>5
>8
********
*      *
*      *
*      *
********
````

---

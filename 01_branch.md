# 条件分岐(復習)

### 課題1 : 入場料金の計算
架空のS水族館の入場料金は、入場者の年齢に応じて表1のように決められる。

[表1: S水族館入場料金]

| 年齢 | 入場料金 |
---|---
| 18歳未満 | 600円 |
| 18歳以上かつ60歳未満 | 1200円 |
| 60歳以上 | 800円 |

入場者の年齢を整数値で入力すると対応する入場料金を表示するプログラムを作成せよ。
ただし、年齢の値は必ず0以上の整数値が入力されるものとして、不正な値のチェックを行う必要はない。

以下に動作例を示す。
(先頭に>が付いた行は標準入力を表すものとする)

[動作例:1]
````
> 24
Fee: 1200 Yen
````

[動作例:2]
````
> 60
Fee: 800 Yen
````

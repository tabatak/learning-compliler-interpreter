# 仮想マシンのメモリ管理

## 7.1 メモリの構成
今回必要になるメモリは、以下の通り。それぞれ配列として確保する。
- オブジェクトプログラム領域
- オペランドスタック領域
- ユーザーメモリ領域
- 記号表領域

## 7.2 記号表領域
## 7.3 オブジェクトプログラム領域
## 7.4 オペランドスタック領域
push(), pop()関数の代わりに以下のマクロを定義。
```
#define PUSH(dt)  stack[++stp]=dt
#define POP()     stack[stp--]
```

## 7.5 ユーザーメモリ領域
静的領域（文字列リテラルや大域変数）は、0番地から高位番地側に成長するように格納。
静的領域の確保は、コンパイル時に行われる。

実行時スタック領域（局所変数など）は、最上位番地から0番地側に成長するように格納。
関数を実行するときに利用するメモリを、スタック領域に確保。
現在実行中の関数が確保したメモリ（フレームと呼ぶ）の絵sン党はbaseReg変数で管理。

# 2020年度 非手続き型言語 期末レポート

今田将也
09430509

## 問題1　パスカルの三角形の i 段目をリストとして返す関数 pascaltri を ML で書け．

### 解答のソースコード その１

まず1段目と各段の両端に1を置き，そしてその他の数は左上と右上の数の和を置く場合

```
exception NoZero;

fun calc (x::y::xs) = x + y::calc(y::xs)
|   calc (x::nil) = [x]
;

fun pascaltri 0 = raise NoZero
|   pascaltri 1 = [1]
|   pascaltri n = if n<0 then raise NoZero else 1 :: calc( pascaltri(n-1) )
;
```

### 出力結果その１

```
- pascaltri 1;
val it = [1] : int list    
- pascaltri 2;
val it = [1,1] : int list  
- pascaltri 3;
val it = [1,2,1] : int list
- pascaltri 4;
val it = [1,3,3,1] : int list
- pascaltri 5;
val it = [1,4,6,4,1] : int list
- pascaltri 6;
val it = [1,5,10,10,5,1] : int list
- pascaltri 7;
val it = [1,6,15,20,15,6,1] : int list
- pascaltri 8;
val it = [1,7,21,35,35,21,7,1] : int list
- pascaltri 9;
val it = [1,8,28,56,70,56,28,8,1] : int list
```

### 解答のソースコード その2

組み合わせを用いる場合．解答のソースコードその１では，例えば，４段目を求める場合，１～３段目も求める必要がある．
しかし，こちらだと，該当の段のみの組み合わせを求めるのでこちらのほうが処理としては簡単なはずである．

```
exception NoZero;

fun expand (0) = [0]
|   expand (n) = n::expand (n - 1)
;

fun comb(n,m)=
if m=0 orelse n=m then 1
else comb(n-1,m)+comb(n-1,m-1)
;

fun combmap(n,x::xs) = comb(n,x)::combmap(n,xs)
|   combmap(_,nil) = nil
;

fun pascaltri(n) = if n<1 then raise NoZero else combmap(n-1,expand(n-1));
```

### 出力結果その２

```
- pascaltri 1;
val it = [1] : int list
- pascaltri 2;
val it = [1,1] : int list
- pascaltri 3;
val it = [1,2,1] : int list
- pascaltri 4;
val it = [1,3,3,1] : int list
- pascaltri 5;
val it = [1,4,6,4,1] : int list
- pascaltri 6;
val it = [1,5,10,10,5,1] : int list
- pascaltri 7;
val it = [1,6,15,20,15,6,1] : int list
- pascaltri 8;
val it = [1,7,21,35,35,21,7,1] : int list
- pascaltri 9;
val it = [1,8,28,56,70,56,28,8,1] : int list
```

## 問題２ 遅延評価についてそれが何でどういう利点があるかを説明せよ．具体例を挙げて説明するのが望ましい．

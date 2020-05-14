# 非手続き型言語　２回目課題
<div style="text-align:right;">09430509 今田将也</div>

## 関数combの作成
解答のソースコード

```
fun comb(n,m)=
 if m=0 orelse n=m then 1
 else comb(n-1,m)+comb(n-1,m-1);

comb(5,2);
comb(10,1);
comb(100,100);
```

出力

```
- use "comb14.txt";    
[opening comb14.txt]
val comb = fn : int * int -> int
val it = 10 : int
val it = 10 : int
val it = 1 : int
val it = () : unit
```

## 課題3.2.1 d)
解答のソースコード

```
fun listlength(L)=
if L=[] then 0
else 1 + listlength(tl(L));

listlength([1,2,3,4,5,6,7,8,9,10]);
listlength([]);
```

出力

```
- use "kadai321d.txt";
[opening kadai321d.txt]
kadai321d.txt:2.5 Warning: calling polyEqual
val listlength = fn : ''a list -> int
val it = 10 : int
val it = 0 : int
val it = () : unit
```

## 課題3.2.1 e)
解答のソースコード

```
fun exponents(x:real,i)=
if i = 0 then 1.0
else x * exponents(x,i-1);

exponents(1.7,3);
exponents(5.0,3);
exponents(10.0,0);
exponents(7.3,1);
```

出力

```
- use "kadai321e.txt"; 
[opening kadai321e.txt]
val exponents = fn : real * int -> real
val it = 4.913 : real
val it = 125.0 : real
val it = 1.0 : real
val it = 7.3 : real
val it = () : unit
```

## 課題3.2.1 f)
解答のソースコード

```
fun listmax([n:int]) = n
    | listmax(L) =
        let
            fun max(x, y) = if x>y then x
                            else y
        in
            max(hd(L),listmax(tl(L)))
        end;
listmax([1,7,3,5,2,9,5]);
listmax([7]);
```

出力

```
- use "kadai321f.txt"; 
[opening kadai321f.txt]
val listmax = fn : int list -> int
val it = 9 : int
val it = 7 : int
val it = () : unit
```
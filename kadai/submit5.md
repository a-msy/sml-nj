# 第5回課題
09430509 今田将也

## ML5-1 のスライドにあった関数rev, 関数rev1 を局所環境を用いて一つの関数として作成
解答のソースコード

```
fun rev(L) =
let
    fun rev1 (M,[]) = M
    |   rev1 (M,x::xs) = rev1(x::M,xs)
in
    rev1([],L)
end;

rev([1,2,3]);
```

出力

```
- use "rev";
[opening rev]
val rev = fn : 'a list -> 'a list
val it = [3,2,1] : int list      
val it = () : unit
```

## 演習問題3.5.2

解答のソースコード

```
fun cat (nil, M) = M
  | cat (x::xs, M) = x::cat(xs, M)
;
fun cycle (L, i) = 
    let
        fun cycle1 (L, y, 0) = cat(L, rev(y))
        | cycle1 (x::xs, y, i) = cycle1(xs, x::y, i-1)
    in
        cycle1 (L, nil, i)
    end
;
cycle([1,2,3,4,5],3);
```

出力

```
- use "kadai352"; 
[opening kadai352]
val cat = fn : 'a list * 'a list -> 'a list    
kadai352:7.13-8.55 Warning: match nonexhaustive
          (L,y,0) => ...
          (x :: xs,y,i) => ...

val cycle = fn : 'a list * int -> 'a list
val it = [4,5,1,2,3] : int list
val it = () : unit
```

## ML5-2 のスライドにある1からnまでの総和を求める末尾再帰の関数

解答のソースコード

```
fun sum (n) =
  let
    fun loop (s,0) = s
      | loop (s,i) = loop(s + i, i - 1)
  in
    loop(0,n)
  end;

sum(5);
sum(100);
```

出力

```
- use "tailsum";  
[opening tailsum]
val sum = fn : int -> int
val it = 15 : int
val it = 5050 : int
val it = () : unit
```

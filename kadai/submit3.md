# 非手続き型言語　３回目課題
<div style="text-align:right;">09430509 今田将也</div>

## 関数mygcdの作成
解答のソースコード

```
fun mygcd(a, 0)= a
|
    mygcd(a, b)= mygcd(b, a mod b)
;

mygcd(35, 45);
mygcd(11, 3);
```

出力

```
- use "mygcd";      
[opening mygcd]
val mygcd = fn : int * int -> int
val it = 5 : int
val it = 1 : int
val it = () : unit
```

## 課題３．３．２
解答のソースコード

```
fun swap(a::nil)  = [a]
|   swap(a::b::cs) = b::a::swap(cs)
|   swap(nil) = nil
;

swap([1,2,3,4,5,6,7]);
swap([1,2,3,4,5]);
```

出力

```
- use "kadai332";
[opening kadai332]
val swap = fn : 'a list -> 'a list
val it = [2,1,4,3,6,5,7] : int list
val it = [2,1,4,3,5] : int list
val it = [2,1] : int list
val it = () : unit
```

## 課題３．３．３
解答のソースコード

```
fun listdel (nil,i) = nil
|   listdel (a::bs, 1) = bs
|   listdel (a::bs, i) = a::listdel(bs,i-1)
;

listdel([1,2,3,4,5,6],3);
listdel([1],1);
listdel([1,2,3,4,5,6],99);
listdel([1],99);
```

出力

```
- use "kadai333"; 
[opening kadai333]
val listdel = fn : 'a list * int -> 'a list
val it = [1,2,4,5,6] : int list
val it = [] : int list
val it = [1,2,3,4,5,6] : int list
val it = [1] : int list
val it = () : unit
```

## 課題３．３．１１ a)
解答のソースコード

```
fun member(x, S) =
let
    fun check(x, a::bs) = 
        if x=a then true 
        else check(x,bs)
        | check(x,[]) = false
in
    check(x, S)
end;

member(3,[1,2,3,4,5,6]);
member(4,[3,4,1,2,5,6]);
member(99,[1,2,3,4,5,6,7]);
```

出力

```
- use "kadai3311a";
[opening kadai3311a]
kadai3311a:4.13 Warning: calling polyEqual
val member = fn : ''a * ''a list -> bool
val it = true : bool
val it = true : bool
val it = false : bool
val it = () : unit
```

## 課題３．３．１１ b)
解答のソースコード

```
fun delete(x, S)=
let
    fun check(x, a::bs) =
        if x=a then bs
        else a::check(x,bs)
        |
            check(x,nil) = nil
in
    check(x, S)
end;

delete(3,[1,3,2,6,5,4,7]);
delete(3,[2,1,3,5,3,6,7]);
delete(99,[1,2,3,4,5,6,7]);
```

出力

```
- use "kadai3311b"; 
[opening kadai3311b]
kadai3311b:4.13 Warning: calling polyEqual
val delete = fn : ''a * ''a list -> ''a list
val it = [1,2,6,5,4,7] : int list
val it = [2,1,5,3,6,7] : int list
val it = [1,2,3,4,5,6,7] : int list
val it = () : unit
```

## 課題３．３．１１ c)
解答のソースコード

```
fun insert(x,S)=
let
    fun check(x, a::bs)=
        if x=a then S
        else check(x, bs)
    |   check(x,nil) = x::S
in
    check(x, S)
end;

insert(3,[]);
insert(2,[1,5,9,0]);
insert(4,[1,2,3,4,5]);
```

出力

```
- use "kadai3311c"; 
[opening kadai3311c]
kadai3311c:4.13 Warning: calling polyEqual
val insert = fn : ''a * ''a list -> ''a list
val it = [3] : int list
val it = [2,1,5,9,0] : int list
val it = [1,2,3,4,5] : int list
val it = () : unit
```
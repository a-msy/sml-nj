# 非手続き型言語　１回目課題
## 演習3.1.1 e)
解答のソースコード

```
fun thirde(a::b::c::cs)=c;
fun st3(str)=thirde(explode str);
st3("abcde");
```

出力

```
- use "kadai311e.txt";
[opening kadai311e.txt]
kadai311e.txt:1.6-1.27 Warning: match nonexhaustive
          a :: b :: c :: cs => ...

val thirde = fn : 'a list -> 'a
val st3 = fn : string -> char
val it = #"c" : char
val it = () : unit
```
## 演習3.1.1 f)
解答のソースコード

```
fun cyclelist (L) =
if L = nil then nil
else tl(L)@[hd(L)];

cyclelist(explode "abced");
cyclelist([1,2,3,4,5]);
```

出力

```
- use "kadai311f.txt"; 
[opening kadai311f.txt]
kadai311f.txt:2.6 Warning: calling polyEqual
val cyclelist = fn : ''a list -> ''a list
val it = [#"b",#"c",#"e",#"d",#"a"] : char list
val it = [2,3,4,5,1] : int list
val it = () : unit
```

## 演習3.1.2 a)
解答のソースコード

```
fun maxmin(a,b,c)=
if a<b then
 if a<c then
  if b<c then (a,c)
  else (a,b)
 else (c,b)
else
 if a<c then
  (b,c)
 else
  if b<c then
   (b,a)
  else
   (c,a)
;
maxmin(1,2,3);
maxmin(1,3,2);
maxmin(2,1,3);
maxmin(2,3,1);
maxmin(3,1,2);
maxmin(3,2,1);
maxmin(33,12,99);
maxmin(0,100,999);
maxmin(5,2,5);
```

出力

```
- use "kadai312a.txt"; 
[opening kadai312a.txt]
val maxmin = fn : int * int * int -> int * int
val it = (1,3) : int * int
val it = (1,3) : int * int
val it = (1,3) : int * int
val it = (1,3) : int * int
val it = (1,3) : int * int
val it = (1,3) : int * int
val it = (12,99) : int * int
val it = (0,999) : int * int
val it = (2,5) : int * int
val it = () : unit
```

## 演習3.1.2 b)
解答のソースコード

```
fun sort(a,b,c)=
if a<b then
 if a<c then
  if b<c then [a,b,c]
  else [a,c,b]
 else [c,a,b]
else 
 if a<c then
  [b,a,c]
 else
  if b<c then 
   [b,c,a]
  else 
   [c,b,a]
;
sort(1,2,3);
sort(1,3,2);
sort(2,1,3);
sort(2,3,1);
sort(3,1,2);
sort(3,2,1);
sort(33,12,99);
sort(0,100,999);
sort(5,2,5);
```

出力

```
- use "kadai312b.txt"; 
[opening kadai312b.txt]
val sort = fn : int * int * int -> int list
val it = [1,2,3] : int list
val it = [1,2,3] : int list
val it = [1,2,3] : int list
val it = [1,2,3] : int list
val it = [1,2,3] : int list
val it = [1,2,3] : int list
val it = [12,33,99] : int list
val it = [0,100,999] : int list
val it = [2,5,5] : int list
val it = () : unit
```

## 演習3.1.2 c)
解答のソースコード

```
fun round(a:real,d)=
((trunc a) +5) div d * d
;
round(114.512, 10);
round(31.433, 10);
round(95.1, 10);
round(5.3222, 10);
```

出力

```
- use "kadai312c.txt"; 
[opening kadai312c.txt]
val round = fn : real * int -> int
val it = 110 : int
val it = 30 : int
val it = 100 : int
val it = 10 : int
val it = () : unit
```

## 演習3.1.2 d)
解答のソースコード

```
fun sdel(a::b::cs)=a::cs;
sdel([1,2,3,4,5,6]);
```

出力

```
- use "kadai312d.txt"; 
[opening kadai312d.txt]
kadai312d.txt:1.6-1.26 Warning: match nonexhaustive
          a :: b :: cs => ...

val sdel = fn : 'a list -> 'a list
val it = [1,3,4,5,6] : int list
val it = () : unit
```
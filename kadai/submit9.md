# 非手続き型言語　9回目課題

09430509
今田将也

## 資料演習問題5.4.7 c)で空の文字列があっても動くようにする．例えば[“abc”, “def”, “ba”, “aa”, ””]

```
fun filter(P, nil) = nil
|   filter(P, x::xs) =  if P(x) then x::filter(P,xs)
                        else filter(P,xs)
;

filter( fn s => if s = "" then false else hd(explode(s)) = #"a",["abc", "def", "ba", "aa",""]);
```

出力

```
- use "kadai547";
[opening kadai547]
val filter = fn : ('a -> bool) * 'a list -> 'a list
val it = ["abc","aa"] : string list
val it = () : unit
```

## 資料演習問題5.4.11


```
exception EmptyList;
fun reduceB (_,[],_) = raise EmptyList
|   reduceB (F,[a],g) = F(a,g)
|   reduceB (F,x::xs,g) = F(x,reduceB(F,xs,g))
;
reduceB(op -,[1,2,3,4,5],6);
reduceB(op +,[1,2,3,4,5],6);
```

出力

```
- use "kadai5411"; 
[opening kadai5411]
exception EmptyList
val reduceB = fn : ('a * 'b -> 'b) * 'a list * 'b -> 'b
val it = ~3 : int
val it = 21 : int
val it = () : unit
```

## 資料演習問題5.4.12

```
exception EmptyList;
fun reduceB (_,[],_) = raise EmptyList
|   reduceB (F,[a],g) = F(a,g)
|   reduceB (F,x::xs,g) = F(x,reduceB(F,xs,g))
;

reduceB(fn (_,g) => g+1,[1,2,3,4,5],0);(*a*)
reduceB(fn (a,g) => a::g ,[1,2,3],[]);(*bはわかりませんでした*)
```

出力

```
- use "kadai5412"; 
[opening kadai5412]
exception EmptyList
val reduceB = fn : ('a * 'b -> 'b) * 'a list * 'b -> 'b
val it = 5 : int
val it = [1,2,3] : int list
val it = () : unit
```
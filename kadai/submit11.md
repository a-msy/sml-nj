# 第11回

## 556

```
fun applyList [] _ = []
|   applyList (F::Fs) x = F x::applyList Fs x;

fun makeFnList _ [] = []
|   makeFnList F (x::xs) = F x::makeFnList F xs;

fun sq (nil,_) = true
| sq (_,nil) = false
| sq (x::xs, y::ys) = if x=y then sq (xs, ys) else sq (x::xs, ys);

fun subsequence x y = sq (explode x, explode y);

val g = makeFnList subsequence;
val text = g ["ear","part","trap","seat"];
applyList text "separate";
```

```
- use "kadai556";
[opening kadai556]
val applyList = fn : ('a -> 'b) list -> 'a -> 'b list
val makeFnList = fn : ('a -> 'b) -> 'a list -> 'b list
kadai556:9.27 Warning: calling polyEqual
val sq = fn : ''a list * ''a list -> bool
val subsequence = fn : string -> string -> bool
val g = fn : string list -> (string -> bool) list
val text = [fn,fn,fn,fn] : (string -> bool) list
val it = [true,true,false,true] : bool list
val it = () : unit
```
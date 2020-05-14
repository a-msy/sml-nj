# 第４回課題
09430509 今田将也

## 3.3.13
解答のソースコード

```
fun power_set(nil) = [nil]
|   power_set(x::xs) = power_set(xs) @ ( List.map (fn ys => x::ys) ( power_set(xs) ) )
;
power_set([1,2,3]);
power_set([1,2]);
```

出力

```
- use "kadai3313";
[opening kadai3313]
[autoloading]
[library $SMLNJ-BASIS/basis.cm is stable]
[library $SMLNJ-BASIS/(basis.cm):basis-common.cm is stable]
[autoloading done]
val power_set = fn : 'a list -> 'a list list
val it = [[],[3],[2],[2,3],[1],[1,3],[1,2],[1,2,3]] : int list list
val it = [[],[2],[1],[1,2]] : int list list
val it = () : unit
```

## 3.4.3
解答のソースコード

```
```

出力

```
```

## 3.4.4
解答のソースコード

```
exception Error;
fun listmax([]) = raise Error
|   listmax([n:real]) = n
|   listmax(L) =
        let
            fun max(x, y) = if x>y then x
                            else y
        in
            max(hd(L),listmax(tl(L)))
        end;
listmax([1.1, 2.2, 3.3, 6.6, 5.5, 4.4]);
listmax([]);
```

出力

```
- use "kadai344";
[opening kadai344]
exception Error
val listmax = fn : real list -> real
val it = 6.6 : real

uncaught exception Error
  raised at: kadai344:2.25-2.30
             ../compiler/TopLevel/interact/interact.sml:56.32-56.36
```

## 5.2.1
解答のソースコード

```
exception Tarinai;
fun dai3([]) = raise Tarinai
|   dai3(L) = if List.length(L) > 3 then hd(tl(tl(L))) else raise Tarinai;

dai3([1,2,3,4,5]);
dai3([1]);
dai3([]);
```

出力

```
- use "kadai521"; 
[opening kadai521]
exception Tarinai
val dai3 = fn : 'a list -> 'a
val it = 3 : int

uncaught exception Tarinai
  raised at: kadai521:3.67-3.74
             ../compiler/TopLevel/interact/interact.sml:56.32-56.36
```

## 5.2.2
解答のソースコード

```
exception ValueIsMinus;
fun kaijyo(0) = 1
|   kaijyo(x) = if x < 0 then raise ValueIsMinus else x*kaijyo(x-1); 

kaijyo(5);
kaijyo(0);
kaijyo(~5);
```

出力

```
- use "kadai522"; 
[opening kadai522]
exception ValueIsMinus
val kaijyo = fn : int -> int
val it = 120 : int
val it = 1 : int

uncaught exception ValueIsMinus
  raised at: kadai522:3.37-3.49
             ../compiler/TopLevel/interact/interact.sml:56.32-56.36
```
# 非手続き型言語　10回目課題

09430509
今田将也


## 資料演習問題5.4.5


```
(*c*)
map (fn c => if c >= #"a" andalso c <= #"z" then chr(ord(c)+ord(#"A")-ord(#"a")) else c) [#"I",#"m",#"A",#"d",#"a"];

(*d*)
map (fn s=> if size(s) > 5 then substring(s,0,5) else s) ["abcde", "Nonmonoton", "fa", "rest"];
```

出力

```
- use "kadai545";                                
[opening kadai545]
val it = [#"I",#"M",#"A",#"D",#"A"] : char list
val it = ["abcde","Nonmo","fa","rest"] : string list
val it = () : unit
```

## 資料演習問題5.6.1

```
(*d*)
foldl (fn(x,y)=>y^x) "" ["aaa","bbb","ccc"];

(*e*)
foldr op- 0 [1,2,3,4];

(*f*)
foldr ( fn(x,y)=> x andalso y ) true [true,false,true];

(*g*)
foldr (fn(x,y)=>x orelse y) false [true,false,true];

(*h*)
foldr (fn (x,y) => x <> y) false [true,false,true];
```

出力

```
- use "kadai561"; 
[opening kadai561]
val it = "aaabbbccc" : string
val it = ~2 : int
val it = false : bool
val it = true : bool
val it = false : bool
val it = () : unit
```
# 非手続き型言語　6回目課題

09430509
今田将也

## 演習3.6.3

解答のソースコード

```
fun eval (nil,_) = 0.0
|   eval (p::nil,_) = p:real
|   eval (p::ps,a:real) = p + a*eval(ps,a)
;
eval([~2.0,4.0,6.0],2.0); 
```

出力

```
- use "kadai363"; 
[opening kadai363]
val eval = fn : real list * real -> real
val it = 30.0 : real
val it = () : unit
```

## 演習3.6.4

解答のソースコード

```
fun padd([],Q)=Q
|   padd(P,[])=P
|   padd((p:real)::ps,q::qs)=(p+q)::padd(ps,qs)
;

fun smult([],_)=[]
|   smult(p::ps,(q:real))=(p*q)::smult(ps,q)
;

fun pmult(P,[])=[]
|   pmult(P,q::qs)=padd(smult(P,q),0.0::pmult(P,qs))
;

fun Poly(nil) = [1.0]
|   Poly(x::xs) = pmult([~x,1.0],Poly(xs))
;

mult([2.0,1.0]);

```

出力

```
```

## 演習3.6.5

解答のソースコード

```
わかりませんでした
```

出力

```
```
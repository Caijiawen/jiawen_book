## PL course note



Goal : Being able to learn new languages and recognize the similarities and differences across languages

#### syntax , type-checking and evaluation

• Addition:
– Syntax: e1+e2 where e1 and e2 are expressions
– Type-checking: type int but only if e1 and e2 have type int in the same static environment, else
does not type-check
– Evaluation: evaluate e1 to v1 and e2 to v2 in the same dynamic environment and then produce
the sum of v1 and v2

- Syntax: how you write something
- Semantics: what something means
  - Type-checking: In static environment
  - Evaluation:In dynamic environment



- Less than
  - Syntax: e1<e2 when e1 and e2 are expressions
  - Type-checking:type bool, only for e1 and e2 are int ,else not type-check
  - Evaluation: if value of e1 is less than value of e2 , produce True , else produce Fasle.

#### Function

```sml
fun pow (x:int, y:int) = (* correct only for y >= 0 *)
if y=0
then 1
else x * pow(x,y-1)
```

#### List

val x = [1,2,3];

5::x    ->   [5,1,2,3]

null x   -> false   null [] -> true

hd x   -> 1

tl x -> [2,3]



#### Let expression(create local environment)

This technique — define a local function that uses other variables in scope — is a hugely common and
convenient thing to do in functional programming.

```
fun countup_from1 (x:int) =
let fun count (from:int, to:int) =
if from=to
then to::[]
else from :: count(from+1,to)
in
count(1,x)
end
```

let 可以用来搞动态规划

```
fun good_max (xs : int list) =
if null xs
then 0 (* note: bad style; see below *)
else if null (tl xs)
then hd xs
else
(* for style, could also use a let-binding for hd xs *)
let val tl_ans = good_max(tl xs)
in
if hd xs > tl_ans
then hd xs
else tl_ans
end
```

### Creating Our Own Types

在第二节课，我们会使用复合类型（compound types）。在前面的课程中，我们已经接触了int , string , list , tuple等类型。

3 ways to build compound types

- Each of :  tuples , list (list has multiple values)
- One of :  options(none or data) , list (tail is null or a list)
- self reference:  list (recursion structure)

#### records

val my_niece =  {id=41111, name="Amelia"};

\#id my_niece  -> 41111

#### datatype binding

Datatype mytype = TwoInts of int*int | Str of string | Pizza

![image-20190726155428051](http://ww2.sinaimg.cn/large/006tNc79gy1g5dan2trx0j313c0m8wi0.jpg)



TwoInts  —   tag part

(1+2,3+4) —  data part



![image-20190726162341602](http://ww1.sinaimg.cn/large/006tNc79gy1g5dbh9ux3oj312g0egdhn.jpg)



#### expression tree

![image-20190726172128271](http://ww1.sinaimg.cn/large/006tNc79gy1g5dd5b374tj30zy0pwqfn.jpg)

![image-20190726172215289](http://ww2.sinaimg.cn/large/006tNc79gy1g5dd64pj92j310o0kgaj4.jpg)
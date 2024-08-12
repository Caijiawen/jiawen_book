### 过程抽象



过程抽象的精髓在于通过组合过程（函数）解决问题。

我们通过一个寻找单边量函数的根的问题来理解过程抽象的含义。

(增加牛顿法的数学证明)

主函数`findRoot` 由 `fixPoint` 和 `newtonFunction`  构成 。

`fixPoint`  函数的主要作用是寻找不动点 ， 给定函数 f 和 变量 x ， 它会不停地将 x 转化为 $f(x)$ , 直到 x 非常接近 $f(x)$

 而 `newtonFunction` 的作用是提供了牛顿函数nf , 当 x 接近 nf(x) 时 ， 可以保证 g(x) = 0   

```python
def findRoot(g , x):
    def newtonFunction(g , x):
        deriv = lambda g,x: (g(x+1e-4) - g(x))/1e-4
        return lambda x: x - g(x)/deriv(g,x)

    def fixPoint(f , x):
        isClose = lambda a,b: True if abs(a-b)<1e-3 else False
        while True:
            n = f(x)
            if isClose(x,n):
                return n
            else:
                x = n
    
    return fixPoint(newtonFunction(g,x) , x)


print(findRoot(lambda x:x**2-5 , 1))
# result: 2.236067977521573
```

上面的例子是过程抽象的绝佳例子，解决单变量函数求根的方法是一个由低阶过程组合而成的高阶过程。

运用这样的方法可以解决所有的简单算法型问题(输入和输出都是简单数据)。





### 数据抽象

在前面的例子中，输入输出都是简单的数据，例如整数，浮点数；这样的数据在python中被称为primitive data type，也就是说它们可以被看做是语言自带的积木。

当我们需要建造复杂的建筑，甚至是城市时，语言自带的积木就远远不能满足我们的需求了。我们需要更复杂的数据类型来表达复杂的需求。

**对象** 是进行数据抽象的基本工具 ， 举个例子 ， 我们实现一个分数的类：



```python
######## helper function
def gcd(a , b):
    if b==0: 
        return a 
    else: 
        return gcd(b , a%b)

class Fraction():
    ########## abstraction barrier: fraction definition(treat fraction as numer and denom)
    def __init__(self , n , d):
        # n stands for numerator , d stands for denominator
        assert type(n) == int
        assert type(d) == int
        self.n = n
        self.d = d
        # we can use multiple ways to represent fraction , e.g:list or tuple
        
    def getNumer(self):
        return self.n

    def getDenom(self):
        return self.d
    
    ########## abstraction barrier: fraction arithmetic and printing(treat fraction as fraction)
    def add(self , other):
        newDenom = other.getDenom() * self.getDenom()
        newNumer = self.getNumer() * other.getDenom() + other.getNumer() * self.getDenom()
        div = gcd(newDenom , newNumer)
        return Fraction(int(newNumer/div) , int(newDenom/div))
    
    def printFraction(self):
        print(str(self.getNumer()) + "/" + str(self.getDenom()))
    
a = Fraction(2,4)
b = Fraction(3,3)
c = a.add(b)
c.printFraction()
## result:3/2
```





### 解释器

写一个scheme解释器：

|      |                        | 例子          |
| ---- | ---------------------- | ------------- |
| 输入 | scheme语句             | (+ 2 (* 4 6)) |
| 输出 | 执行scheme语句得到的值 | 26            |

我们把写解释器的步骤分为三个部分：

- 分词：把`(+ 2 (* 4 6))` 转化为 ` ['(' , '+' , 2 , '(' , '*' , 4 , 6 , ')' , ')']`
- 表达式树：把` ['(' , '+' , 2 , '(' , '*' , 4 , 6 , ')' , ')']` 转化为 `Pair('+', Pair(2, Pair(Pair('*', Pair(4, Pair(6, nil))), nil)))`

- Eval-Apply:  执行表达式树，得到结果26


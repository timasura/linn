## λ


### 1.定义函数式接口，必要

```Java

@FunctionalInterface
public interface ITes {
    public int calculate(int x, int y);
}

```


### 2.获取ITes对象实例

#### 1.匿名内部类

```Java

ITes tes = new ITes(){
    @Override
    public int calculate(int x, int y) {
        return x + y;
    }
};

```

#### 2.Lambda表达式

```Java

ITes tes = (x, y) -> x + y;

```
* 1. "(x, y)" 表示 函数的__`参数列表`__
* 2. "x + y"  表示 函数的__`返回值`__，可以加上"{}", 如: ITes tes = (x, y) -> {return x + y;};
* 3. "(x, y) -> x + y" 表示实现接口的对象__`实例`__,tes 为 对象的引用
* 4. 这里只是获取了一个对象，使用时需要 tes.calculate(3,6) 。Lambda表达式的作用是简化了匿名函数的定义，把方法的具体实现传递给对象 tes



### 3.定义一个函数实现数据传递和行为传递，可选

```Java

static void option(int x ,int y , ITes it){
    // 定义功能代码
    System.out.println(it.calculate(x, y));
}

```


### 4.调用测试

```Java

option(1, 2, (x, y) -> x / y);
option(3, 1, (x, y) -> x - y);

```

### Lambda示例

```Java

IntFunction<IntUnaryOperator> curriedAdd = a -> b -> a + b;    <==>    IntFunction<IntUnaryOperator> curriedAdd = a -> (b -> a + b);

IntFunction<IntUnaryOperator> add = new IntFunction<IntUnaryOperator>(){
    @Override
    public IntUnaryOperator apply(int a) {
        return new IntUnaryOperator(){
            @Override
            public int applyAsInt(int b) {
                return a + b;
            }
                    
        };
    }
};

```

### Lambda Questions
* Lambda 和 匿名内部类的区别：语法、范围、[性能](https://code.i-harness.com/zh-CN/q/1596d4c)
* 反编译Lambda代码 与 原代码进行对比
* 普通类对象，匿名内部类对象，Lambda对象 在JVM里的区别

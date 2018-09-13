## Lambda


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


### 3.定义一个函数实现数据传递和行为传递，可选

```Java

static void option(int x ,int y , ITes it){
    System.out.println(it.calculate(x, y));
}

```


### 4.调用测试

```Java

option(1, 2, (x, y) -> x / y);
option(3, 1, (x, y) -> x - y);

```


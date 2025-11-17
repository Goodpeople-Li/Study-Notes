# MicroPython基础

1. ***运算符***
    |符号| 描述 |
    |:---:|:---:|
    | // | 整除|
    | ** | 指数 |

2. ***数据类型转换***

    | 函数  | 说明  |
    | :---: | :---: |
    |int(x)| 转化为整型|
    |float(x)| 转化为浮点型|
    |str(x) | 转化为字符串 |

3. ***字符串***
   - 采用双引号定义法
  
4. ***字符串拼接***
   ```
    name = 'LCKFB'
    print("hello " + name)
    #或者这样
    print("hello " + name,     end='')#这样可以末尾空格而不是默认换行           
    ```

5. ***字符串格式化***
   ```
   name = "张三"
    age = 18
    weight = 140.54
    message = "我叫%s，今年%d岁，体 重%f斤" % (name, age, weight)
    print(message)
    ```

6. ***判断语句***
   - if语句基本格式
    ```
    if age >= 18:
    print("你是一个成年人了")
    ```


    - if...else语句格式
    ```
    if age >= 18:
    print("你的年龄大于等于18岁")
    elif age > 10:
    print("你的年龄大于10岁并且小于18岁")
    else:
    print("你的年龄小于等于10岁")
    ```

7. ***循环语句***
   1. While循环
    ```
    i = 0
    while i < 10:
    print("i = %d" % i)
    i += 1
    ```

    2. For循环
    ```
     name = "LCKFB"
    for x in name:
    print(x)#range语句是用于获得一个数字序列。指的是从0开始，到num结束（不含num本身
    ```

     语法一：range(num)
    ```
     name = "LCKFB"
    for x in name:
    print(x)
    ```

    语法二：range(num1, num2)
    ```
    for x in range(5, 10):#指的是从num1开始，到num2结束（不含num2本身）
    print(x)
    ```
    
8. 使用 global关键字 可以在函数内部声明变量为全局变量，相当于C语言里的static。

9. ***类和继承***
     1. 定义类
    ```
    class MyClass:
    def __init__(self, param):
        self.param = param

    def method(self):
        # 方法实现
        pass
    ```

    2. 实例化对象
     ```
    my_object = MyClass("value")
     ```

    3. 访问属性和调用方法：
    ```
    value = my_object.param
    my_object.method()
    ```

    4. 继承
    在 microPython 中，您可以使用继承来创建一个类从另一个类继承属性和方法。通过继承，子类可以获得父类的特征并添加自己的特定功能。例如：

    ```
    class ChildClass(MyClass):
    def __init__(self, param, child_param):
        super().__init__(param)
        self.child_param = child_param

    def child_method(self):
        # 子类方法实现
        pass
    ```
    5. 多重继承： microPython 支持多重继承，即一个类可以从多于一个父类继承。多重继承可通过在类定义中列出多个父类来实现。
    ```
    class ChildClass(ParentClass1, ParentClass2): # 类定义
    pass
    ```
    


  

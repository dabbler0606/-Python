# Python 的世界

## 入门第一课

```python
print('Hello Fun Python!')
```

```text
>>>
Hello Fun Python!
```

Python 是一门优雅的语言。有着自己的独特的设计理念。了解并理解这些理念，能够让我们更好的学习 Python，掌握 Python。

## 面向对象的设计

Python 是一门 “纯“ 面向对象的编程语言。为何说 “纯“ 呢？因为在 Python 中，**万物皆为对象。**

```python
price = 100
print(type(price))
print(dir(price))
```

```text
>>>
<class 'int'>
['__abs__', '__add__', '__and__', '__bool__', '__ceil__', '__class__', '__delattr__', '__dir__', '__divmod__', '__doc__', '__eq__', '__float__', '__floor__', '__floordiv__', '__format__', '__ge__', '__getattribute__', '__getnewargs__', '__gt__', '__hash__', '__index__', '__init__', '__init_subclass__', '__int__', '__invert__', '__le__', '__lshift__', '__lt__', '__mod__', '__mul__', '__ne__', '__neg__', '__new__', '__or__', '__pos__', '__pow__', '__radd__', '__rand__', '__rdivmod__', '__reduce__', '__reduce_ex__', '__repr__', '__rfloordiv__', '__rlshift__', '__rmod__', '__rmul__', '__ror__', '__round__', '__rpow__', '__rrshift__', '__rshift__', '__rsub__', '__rtruediv__', '__rxor__', '__setattr__', '__sizeof__', '__str__', '__sub__', '__subclasshook__', '__truediv__', '__trunc__', '__xor__', 'as_integer_ratio', 'bit_length', 'conjugate', 'denominator', 'from_bytes', 'imag', 'numerator', 'real', 'to_bytes']
```

> **type** 和 **dir** 是 Python 的内建方法。type 输出对象类型，如输出中 price 为整数。dir 输出对象属性。

从输出来看，即使最简单的整数，在 Python 中也是一个 int 类型对象。有着自己的属性和方法。

那么为何这样设计，答案 一致性。

生活中我们都希望事事有标准，杂乱的事物可以表现的整齐、一致。Python 中，所有的对象都是由 object 对象派生而来。object 类中定义了基础属性和方法。这些属性和方法所有类共有。

```python
class object:
    def __dir__(self, *args, **kwargs): # real signature unknown
        """ Default dir() implementation. """
        pass
    
    def __eq__(self, *args, **kwargs): # real signature unknown
        """ Return self==value. """
        pass
```

那么我们可以不用关心对象类型，来调用它们的共同方法。

```python
i = 100  # 整数
s = 'hello'  # 字符串
print(i.__dir__())
print(s.__dir__())
```

所有的对象都有 \_\_dir\_\_ 方法来获取属性。但要调用长长的 \_\_dir\_\_\(\) 函数，能否更简单些。可以，使用上文我们提到的 dir 内建函数。

```python
print(dir(i))
print(dir(s))
```

dir 函数仅仅调用了类的内置 \_\_dir\_\_\(\) 函数。这就是一致性带来的好处。我们可以在所有对象上调用 dir 函数不用顾虑它的类型。


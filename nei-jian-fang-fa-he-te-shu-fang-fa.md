# 内建方法和特殊方法

## property

property 是 Python 提供的装饰器。用来代替通过 get 获取属性。可以进行一些简单的计算。

```python
class Counter(object):
    _count = 0
    
    @property
    def count(self):
        if self._count > 1000:
            self._count = 0
        return self._count
```

一些较为复杂的运算，可以通过库提供的带缓存的 property 进行装饰。

Python ≥ 3.8

```python
import functools
class MyClass:
    @functools.cached_property
    def foo(self):
        print("long calculation here")
        return 21 * 2
```

Python ≥ 3.2 

```python
import functools
class MyClass:
    @property
    @functools.lru_cache()
    def foo(self):
        print("long calculation here")
        return 21 * 2
```

> [`functools`](https://docs.python.org/zh-cn/3/library/functools.html#module-functools) 模块应用于高阶函数，即参数或（和）返回值为其他函数的函数。 通常来说，此模块的功能适用于所有可调用对象。 👉 [这里](https://docs.python.org/zh-cn/3/library/functools.html)


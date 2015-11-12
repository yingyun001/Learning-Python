# 关于 @property

---

~~~ python
# 先来看我写的错误的代码：
class Stu(object):
   # setter
   @score.setter
   def score(self, score):
      self._score = score
   @property
   def score(self):
      return self._score

s = Stu()
s._score = 100
print s._score
~~~
~~~ bash
# 执行结果
Traceback (most recent call last):
  File "property.py", line 1, in <module>
    class Stu(object):
  File "property.py", line 3, in Stu
    @score.setter
NameError: name 'score' is not defined
~~~

现在知道了:**@property** 要放到前面啊！

---

* 说实话，现在处于 Python 小白阶段的我还没有真切的感受到 **`@property`** 带来的好处，目前的理解就是从网站上学到的而已：

  这里用 **`@property`** 装饰器满足了两点好处：
  * 可以在类的外部对属性进行简单操作，例如：
    ~~~ python
    [object].[property] = ***
    print [object].[property]
    ~~~
    
    不用写成下面这种复杂的样子了：
    ~~~ python
    [object].set_[property](***)
    print [object].get_[property]()
    ~~~
  
  * 操作属性时，可以对赋给属性的参数值进行**检查**，例如：
    ~~~ python
    def [property](self, value):
        if not isinstance(value, int):
            raise ValueError('[property] must be an integer!')
        if value < 0 or value > 100:
            raise ValueError('[property] must between 0 ~ 100!')
        self._[property] = value
    ~~~

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

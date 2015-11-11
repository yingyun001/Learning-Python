# 关于 @property

---

# 先来看我写的错误的代码：
~~~ python
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


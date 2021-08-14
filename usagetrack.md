```python
import diagnostics
session = diagnostics.session(auto_sync=False, server="orz.cx")
diag.send("Started")

@session.event(args=False)
def util(a, b):
  return a+b

class my_class:
  a: int
  
  @session.event()
  def __init__(self, a):
    self.a = a
  
  @session.event()
  def do_something(self):
    print(self.a)
   
  @session.event(result=False)
  def one_plus(self):
    return self.a + 1

def main():
  my_obj = my_class(3)
  session.sync()
  my_obj.one_plus()
  util(3, 1)



session.close()

```

Struct/parser/builder but better
### Model
![image](https://user-images.githubusercontent.com/61394004/128643329-f7c98345-6be0-42ca-9eb7-044540a33abe.png)
### Example
```python
class head(channel):
  consume(build):
    return build, SimpleNameSpace()
  
  build(blu_print, build):
    return build
  
class tail(channel):
  consume(build, blu_print):
    return blu_print
  
  build(blue_print):
    return blue_print, str()
 
class get_str(channel):
  consume(build, blu_print):
    parts = build.split(" ")
    blu_print.str = parts[0]
    return " ".join(parts[1:]), blu_print
    
  build(blu_print, build):
    parts += " " + blu_print.str
    
    
# parser = SymetricParser(head, get_str, tail)
parser = Parser(head, get_str, tail)
my_data = parser.consume("owo 3") # namespace(str="owo")
my_str = parser.build(my_data)  # "owo"
```

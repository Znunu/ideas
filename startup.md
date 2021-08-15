@main.py
```python
import startup
startup.scan()

print("You'll see me every time you boot")
```

@terminal
```bat
python main register

python main unregister
```

@startup/__init__.py
```python
with(get_startup_folder) as file:
  file.write("{python_exe} {script}")

```

@startup/__init__.py
```python
import parselib
import apscheduler
import startup.win

def scan(venv: bool = None, script = None, callback = None, id = None)
```

@startup/win.py
```python
import winpath

def set_startup(command)
```


@startup/__main__.py
```python
import startup.win
import apscheduler
```


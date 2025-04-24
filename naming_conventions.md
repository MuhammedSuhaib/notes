## 3. Naming Conventions

- Camel Case: `myVariableName` (JS/TS)
- Snake Case: `my_variable_name` (Python)
- Pascal Case: `MyVariableName` (Both)
- Lower Case: `myvariablename` (Both, but uncommon)
- Double Underscore: `__private_variable` (Python only, used for name mangling)
---
### names to avoid as variables

```python
import builtins, keyword

# 1 ) Hard keywords  – absolutely forbidden
hard = set(keyword.kwlist)

# 2 ) Soft keywords – legal but confusing
soft = set(keyword.softkwlist)

# 3 ) Built‑ins (functions, types, exceptions) – legal but risky
built_in = set(dir(builtins))

discouraged = soft | built_in            # plus all hard keywords, of course

items=len(discouraged)
for i in discouraged:
    print(i)
```
```
next
ConnectionRefusedError
__name__
zip
case
copyright
id
FileExistsError       
anext
aiter
UnicodeEncodeError    
AssertionError        
sorted
sum
len
frozenset
BufferError
ResourceWarning
repr
complex
format
DeprecationWarning
input
set
None
bin
bool
int
exit
UnicodeWarning
compile
help
PermissionError
filter
RecursionError
ascii
ConnectionResetError
KeyboardInterrupt
FutureWarning
True
RuntimeWarning
__import__
ConnectionAbortedError
WindowsError
ZeroDivisionError
StopAsyncIteration
bytearray
UnboundLocalError
bytes
SystemExit
credits
False
quit
callable
__spec__
oct
type
AttributeError
_
memoryview
EnvironmentError
ImportWarning
IOError
EncodingWarning
delattr
dict
issubclass
list
Ellipsis
ExceptionGroup
object
SyntaxError
ArithmeticError
locals
FloatingPointError
tuple
classmethod
BaseExceptionGroup
all
setattr
hex
chr
EOFError
slice
__loader__
LookupError
IsADirectoryError
Exception
UnicodeError
property
UnicodeDecodeError
match
FileNotFoundError
enumerate
float
divmod
TimeoutError
TabError
KeyError
globals
license
BlockingIOError
UserWarning
GeneratorExit
min
SystemError
PendingDeprecationWarning
abs
SyntaxWarning
NameError
MemoryError
NotImplementedError
BytesWarning
map
pow
round
breakpoint
PythonFinalizationError
ValueError
ModuleNotFoundError
IndentationError
BrokenPipeError
max
ReferenceError
iter
OverflowError
getattr
TypeError
__package__
reversed
staticmethod
vars
print
NotADirectoryError
__doc__
hasattr
RuntimeError
str
ConnectionError
any
ProcessLookupError
super
range
exec
BaseException
ImportError
UnicodeTranslateError
ord
dir
StopIteration
InterruptedError
_IncompleteInputError
__debug__
IndexError
isinstance
hash
OSError
ChildProcessError
open
Warning
__build_class__
eval
NotImplemented
```


- **Use none of `hard`.**
- **Avoid `soft`** (e.g. `"match"`, `"case"`).
- **Avoid `built_in`** (`"list"`, `"dict"`, `"print"`, `"Exception"`, …) or you’ll shadow Python’s standard objects.
---


#### printing all keywords at once using "kwlist"
```py
import keyword
print(keyword.kwlist)

# The list of keywords is : 
# False
# None
# True
# and
# as
# assert
# async
# await
# break
# class
# continue
# def
# del
# elif
# else
# except
# finally
# for
# from
# global
# if
# import
# in
# is
# lambda
# nonlocal
# not
# or
# pass
# raise
# return
# try
# while
# with
# yield
```

```py
import builtins
print(dir(builtins) )
temp_var = len(dir(builtins))
for i in range(temp_var):
    print(dir(builtins)[i])
```

```
['ArithmeticError', 'AssertionError', 'AttributeError', 'BaseException', 'BaseExceptionGroup', 'BlockingIOError', 'BrokenPipeError', 'BufferError', 'BytesWarning', 'ChildProcessError', 'ConnectionAbortedError', 'ConnectionError', 'ConnectionRefusedError', 'ConnectionResetError', 'DeprecationWarning', 'EOFError', 'Ellipsis', 'EncodingWarning', 'EnvironmentError', 'Exception', 'ExceptionGroup', 'False', 'FileExistsError', 'FileNotFoundError', 'FloatingPointError', 'FutureWarning', 'GeneratorExit', 'IOError', 'ImportError', 'ImportWarning', 'IndentationError', 'IndexError', 'InterruptedError', 'IsADirectoryError', 'KeyError', 'KeyboardInterrupt', 'LookupError', 'MemoryError', 'ModuleNotFoundError', 'NameError', 'None', 'NotADirectoryError', 'NotImplemented', 'NotImplementedError', 'OSError', 'OverflowError', 'PendingDeprecationWarning', 'PermissionError', 'ProcessLookupError', 'PythonFinalizationError', 'RecursionError', 'ReferenceError', 'ResourceWarning', 'RuntimeError', 'RuntimeWarning', 'StopAsyncIteration', 'StopIteration', 'SyntaxError', 'SyntaxWarning', 'SystemError', 'SystemExit', 'TabError', 'TimeoutError', 'True', 'TypeError', 'UnboundLocalError', 'UnicodeDecodeError', 'UnicodeEncodeError', 'UnicodeError', 'UnicodeTranslateError', 'UnicodeWarning', 'UserWarning', 'ValueError', 'Warning', 'WindowsError', 'ZeroDivisionError', '_IncompleteInputError', '__build_class__', '__debug__', '__doc__', '__import__', '__loader__', '__name__', '__package__', '__spec__', 'abs', 'aiter', 'all', 'anext', 'any', 'ascii', 'bin', 'bool', 'breakpoint', 'bytearray', 'bytes', 'callable', 'chr', 'classmethod', 'compile', 'complex', 'copyright', 'credits', 'delattr', 'dict', 'dir', 'divmod', 'enumerate', 'eval', 'exec', 'exit', 'filter', 'float', 'format', 'frozenset', 'getattr', 'globals', 'hasattr', 'hash', 'help', 'hex', 'id', 'input', 'int', 'isinstance', 'issubclass', 'iter', 'len', 'license', 'list', 'locals', 'map', 'max', 'memoryview', 'min', 'next', 'object', 'oct', 'open', 'ord', 'pow', 'print', 'property', 'quit', 'range', 'repr', 'reversed', 'round', 'set', 'setattr', 'slice', 'sorted', 'staticmethod', 'str', 'sum', 'super', 'tuple', 'type', 'vars', 'zip']        
ArithmeticError
AssertionError
AttributeError
BaseException
BaseExceptionGroup
BlockingIOError
BrokenPipeError
BufferError
BytesWarning
ChildProcessError
ConnectionAbortedError
ConnectionError
ConnectionRefusedError
ConnectionResetError
DeprecationWarning
EOFError
Ellipsis
EncodingWarning
EnvironmentError
Exception
ExceptionGroup
False
FileExistsError
FileNotFoundError
FloatingPointError
FutureWarning
GeneratorExit
IOError
ImportError
ImportWarning
IndentationError
IndexError
InterruptedError
IsADirectoryError
KeyError
KeyboardInterrupt
LookupError
MemoryError
ModuleNotFoundError
NameError
None
NotADirectoryError
NotImplemented
NotImplementedError
OSError
OverflowError
PendingDeprecationWarning
PermissionError
ProcessLookupError
PythonFinalizationError
RecursionError
ReferenceError
ResourceWarning
RuntimeError
RuntimeWarning
StopAsyncIteration
StopIteration
SyntaxError
SyntaxWarning
SystemError
SystemExit
TabError
TimeoutError
True
TypeError
UnboundLocalError
UnicodeDecodeError
UnicodeEncodeError
UnicodeError
UnicodeTranslateError
UnicodeWarning
UserWarning
ValueError
Warning
WindowsError
ZeroDivisionError
_IncompleteInputError
__build_class__
__debug__
__doc__
__import__
__loader__
__name__
__package__
__spec__
abs
aiter
all
anext
any
ascii
bin
bool
breakpoint
bytearray
bytes
callable
chr
classmethod
compile
complex
copyright
credits
delattr
dict
dir
divmod
enumerate
eval
exec
exit
filter
float
format
frozenset
getattr
globals
hasattr
hash
help
hex
id
input
int
isinstance
issubclass
iter
len
license
list
locals
map
max
memoryview
min
next
object
oct
open
ord
pow
print
property
quit
range
repr
reversed
round
set
setattr
slice
sorted
staticmethod
str
sum
super
tuple
type
vars
zip
```
---

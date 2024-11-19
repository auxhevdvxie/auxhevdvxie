

### Python 学习笔记 
1. **Python 基础语法**  
- **变量与数据类型**  
  - 动态类型语言，无需声明变量类型。

```python
x = 10        # 整型
y = 3.14      # 浮点型
name = "Alice"  # 字符串
flag = True    # 布尔类型
```
 
  - 常用数据类型：`int`、`float`、`str`、`bool`、`list`、`tuple`、`dict`、`set`。
 
- **控制结构**  
  - 条件语句：

```python
if x > 10:
    print("Greater than 10")
elif x == 10:
    print("Equal to 10")
else:
    print("Less than 10")
```
 
  - 循环：

```python
for i in range(5):  # 输出 0 到 4
    print(i)

n = 0
while n < 5:
    print(n)
    n += 1
```
 
- **函数定义与调用**  
  - 使用 `def` 关键字定义函数：

```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))
```
 
  - 可变参数：

```python
def sum_all(*args):
    return sum(args)

print(sum_all(1, 2, 3, 4))
```
2. **Python 数据结构**  
- **列表（List）**  
  - 可变数据类型，支持索引和切片。

```python
my_list = [1, 2, 3, 4]
my_list.append(5)      # 添加元素
print(my_list[1:3])    # 切片
```
 
- **元组（Tuple）**  
  - 不可变数据类型。

```python
my_tuple = (1, 2, 3)
print(my_tuple[1])
```
 
- **字典（Dictionary）**  
  - 键值对集合。

```python
my_dict = {"name": "Alice", "age": 25}
my_dict["age"] = 26  # 修改
print(my_dict["name"])
```
 
- **集合（Set）**  
  - 无序、不重复元素集合。

```python
my_set = {1, 2, 3}
my_set.add(4)
print(my_set)
```
3. **面向对象编程**  
- **类与对象**  
  - 使用 `class` 定义类。

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def greet(self):
        return f"Hi, I am {self.name}."

alice = Person("Alice", 25)
print(alice.greet())
```
 
- **继承**  
  - 支持单继承和多继承。

```python
class Student(Person):
    def __init__(self, name, age, student_id):
        super().__init__(name, age)
        self.student_id = student_id
    
    def greet(self):
        return f"Hi, I am {self.name}, ID: {self.student_id}."

bob = Student("Bob", 20, "S12345")
print(bob.greet())
```
4. **文件操作**  
- **读取文件** 

```python
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
```
 
- **写入文件** 

```python
with open("example.txt", "w") as file:
    file.write("Hello, world!")
```
 
- **逐行读取** 

```python
with open("example.txt", "r") as file:
    for line in file:
        print(line.strip())
```
5. **异常处理**  
- 使用 `try-except` 捕获异常：

```python
try:
    x = 1 / 0
except ZeroDivisionError as e:
    print(f"Error: {e}")
finally:
    print("Finished!")
```
6. **常用库**  
- **数学与科学计算**  
  - `math`：提供数学函数。

```python
import math
print(math.sqrt(16))
```
 
  - `numpy`：高效的数组操作。

```python
import numpy as np
arr = np.array([1, 2, 3])
print(arr * 2)
```
 
- **数据处理**  
  - `pandas`：数据分析与处理。

```python
import pandas as pd
df = pd.DataFrame({"A": [1, 2], "B": [3, 4]})
print(df)
```
 
- **绘图**  
  - `matplotlib` 和 `seaborn`：可视化数据。

```python
import matplotlib.pyplot as plt
plt.plot([1, 2, 3], [4, 5, 6])
plt.show()
```
 
- **网络请求**  
  - `requests`：发送 HTTP 请求。

```python
import requests
response = requests.get("https://api.example.com")
print(response.json())
```
7. **进阶知识**  
- **装饰器**  
  - 在函数执行前后添加额外功能。

```python
def decorator(func):
    def wrapper(*args, **kwargs):
        print("Before function call")
        result = func(*args, **kwargs)
        print("After function call")
        return result
    return wrapper

@decorator
def say_hello():
    print("Hello!")

say_hello()
```
 
- **生成器**  
  - 使用 `yield` 返回值。

```python
def count_up_to(max):
    count = 1
    while count <= max:
        yield count
        count += 1

for num in count_up_to(5):
    print(num)
```
 
- **多线程与多进程**  
  - 多线程：


```python
import threading

def print_numbers():
    for i in range(5):
        print(i)

thread = threading.Thread(target=print_numbers)
thread.start()
thread.join()
```
 
  - 多进程：


```python
from multiprocessing import Process

def print_numbers():
    for i in range(5):
        print(i)

process = Process(target=print_numbers)
process.start()
process.join()
```


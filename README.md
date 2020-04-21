# PythonFuncs
常用的matlab函数对应到python函数

MATLAB中 0:4
```python
range(5)
```
	
MATLAB中 1:5
```python
xrange(1,6,1) 或 xrange(1,6)
```

MATLAB中 1:2:5
```python
xrange(1,6,2)
```
	
MATLAB中开平方根的运算：`sqrt(x)`
```python
import math
math.sqrt(x)
x ** 0.5
```

MATLAB中的幂运算：`^`
```python
**
```

判断是否为整数`integer`: 
*Matlab:*
```matlab
mod(x,1); ~isinf(x) & floor(x) == x
```
*Python:*
```python
x.is_integer()
```

**python3里面没有`long`这个长整型，统一由`int`代替**

数组下标
```python
fifth_letter = "MONTY"[4] # 可以直接在声明的时候就直接取某一个值
```
	
**取某一既带大写又带小写字母的全部大或小写的字符串**
```python
x.upper()
x.lower()
```

打印字符串
```python
# Python 2
print "Ah, so your name is ___, your quest is ___, and your favorite color is ___." ___ (name, quest, color)
print "Ah, so your name is %s, your quest is %s, and your favorite color is %s." %s (name, quest, color)

# 最新的format用去
# Python 3
print("Ah, so your name is {}, your quest is {}, and your favorite color is {}.".format(name, quest, color))
```

与或符判断顺序：

	1 -- `not` is evaluated first;
	2 -- `and` is evaluated next;
	3 -- `or` is evaluated last.

`def`, `if`, `else`, `elif`都要在最后加上冒号

检测字符串是否只由字母组成
```python
x.isalpha()
```

MATLAB中string的连结：`str4 = [str1, str2, str3]`
```python
str4 = str1 + str2 + str3
```

检查库中函数的办法
```python
import module # Imports some module
everything = dir(module) # Sets everything to a list of things from the module
print everything # Prints 'em all!
```

检查变量类型

	`type(x) == int` or `type(x) == float` # 而int和float都不用加引号

MATLAB中连结矩阵元素：`x = []; x = [x; [a b]]; x = [x c d];`
```python
x = []
x.append([a b])
x.remove([a b])

x = []
x.exxpend([c d])
x.remove([d])

n.pop(index) # will remove the item at index from the list and return it to you
n.remove(item) # will remove the actual item if it finds it
```

MATLAB向量取部分值：`a(1:end); a(2:end); a(2:end-1); a(1:3)`
```python
a[0:]
a[1:]
a[1:-1]
a[0:3]
```

反查元素在向量中的位置，还可以在某一位置插入值
```python
animals = ["aardvark", "badger", "duck", "emu", "fennec fox"]
duck_index = animals.index("duck")
animals.insert(duck_index, "cobra")

a = [1,3,4,5]
three_index = a.index(3)
a.insert(three_index, 7)
```

向量可以直接连续用加号
```python
a = [1, 2, 3]
b = [4, 5, 6]
print a + b
```

字典可以直接赋值，不需要提前开辟内存空间
```python
dict_name = {}
dict_name[new_key] = new_value

del dict_name[key_name] # 删除
```

字典可以多维的
```python
my_dict = {
	"fish": ["c", "a", "r", "p"],
	"cash": -4483,
	"luck": "good"
}
print my_dict["fish"][0] # 不能打印某一个key，想打印key只能遍历的方式去打印
my_dict["fish"].sort()
my_dict[0].remove("a")
```

字典打印key名称和key值的方法
```python
d = {'a': 'apple', 'b': 'berry', 'c': 'cherry'}
for key in d:
	print key + " " + d[key]
```

MATLAB中访问二维数组：a(1,2) = 1
```python
a[1][2] = 1
```
	
判断一个值是否在一个向量里面
```python
if x not in A
if guess_row not in range(5)
```

字符串二维数组初始化成单一字符的使用方法
```python
for x in range(5):
	board.append(["O"] * 5)
```
	
打印在同一行
```python
print(char), # 逗号是说明打印要在同一行
print(char) # 正常打印
```

字符串数组还有一种遍历的方式
```python
choices = ['pizza', 'pasta', 'salad', 'nachos']
print 'Your choices are:'
for index, item in enumerate(choices):
	print index, item # 把序号和字符串的值都打出来了
```

有一个循环遍历多个数组
```python
list_a = [3, 9, 17, 15, 19]
list_b = [2, 4, 8, 10, 30, 40, 50, 60, 70, 80, 90]
for a, b in zip(list_a, list_b):
```

字符串替换或批量替换用replace
```python	
def censor(text,word):
	if word in text:
		text = text.replace(word, "*" * len(word))
	return text

censor("this hack is wack hack", "hack") # 结果为 "this **** is wack ****"
```

数组统计出现的次数
```python
x.count(item)
```

MATLAB中unique函数，用来返回数据中的唯一值
```python
import numpy as np
np.unique()
```

**python里面的`find`只能找到第一个，`rfind`只能找到最后一个，而不像MATLAB里面的`find`可以找到所有的**

MATLAB里面的floor和ceil函数
```python
np.floor()
np.ceil()
```
MATLAB定义一个数组后，a = 1:5，可以直接打印出来
```python
a = range(5)
print a # 打印不出来
a = list(range(5))
print a
```

字符串复制
```python
b = a.reverse() # b并没有被赋值
b = a[::-1] # b被赋值，深拷贝
```

MATLAB里面step为小数时候的等差数列：a = -4:0.1:4
```python
import numpy as np
a = np.arange(-4,4,0.1)
```

MATLAB里面自然对数：a = ln(x)
```python
import numpy as np
a = np.log(x)
```
Python文件IO的时候，尽量使用with as的语句，这样不用担心f.close()的问题
```python
with open("text.txt", "w") as textfile:
	textfile.write("Success!")

textfile = open("text.txt", "w")
textfile.write("Success!")
textfile.close()
```

读取txt文件每一行，生成list
```python	
with open("text.txt", "r") as textfile:
	textfile.read().splitlines()
# 而不是下面的命令，否则list每一个元素里面结尾会有一个'\n'
with open("text.txt", "r") as textfile:
	textfile.readlines()
```
	
Python中`os.path.join()`产生的斜杠在Windows和Linux下的不同表现和解决方法:
通过`pathlib.PurePath.as_posix()`。从Python 3.4开始可以通过`pathlib.PurePath.as_posix()`来生成斜杠（`/`）格式的路径，其实其实现原理和`str.replace()`并没有太大区别。例如：

```python
import os.path
from pathlib import Path

result = os.path.join('a', 'b', 'c')
result = Path(result).as_posix()

# 或者
import os.path

result = os.path.join('a', 'b', 'c')
result = result.replace('\\', '/')
```

Python将输出记录到txt里面
```python
import sys
class Logger(object):
    def __init__(self, filename='default.log', stream=sys.stdout):
	    self.terminal = stream
	    self.log = open(filename, 'a')

    def write(self, message):
	    self.terminal.write(message)
	    self.log.write(message)

    def flush(self):
	    pass

sys.stdout = Logger('logname.log', sys.stdout)
sys.stderr = Logger('logname_error_msg.log', sys.stderr)		# redirect std err, if necessary

# now it works
print(print something)
```

Python的['str1'] + ['str2']会是['str1', 'str2']。['str1'] + 'str2'会是['str1', 's', 't', 'r', '2']

Python的字典的value如果是一个列表，比如['str1', 'str2]，那么想取['str1']就是dict[key][0:1]，想取'str1'就是dict[key][0]

Python中PIL的Image读入的图片转换成cv2读入的图片
```python
from PIL import Image
import cv2
import numpy as np

img_PIL = Image.open(image_path)

# PIL格式中的width和height
width = img_PIL.size[0]
height = img_PIL.size[1]

# 转换成RGB模式
pil_image = img_PIL.convert('RGB')

# 转换成cv2的BGR模式
img_cv2_channel3 = np.array(pil_image)[:, :, [2, 1, 0]]

# 从[h, w, 3]转换成[h, w]
img_cv2 = cv2.cvtColor(img_cv2_channel3, cv2.COLOR_BGR2GRAY)

# 此时 img_cv2_channel3 等价于 img = cv2.imread(imgPath)
# 此时 img_cv2 等价于 img = cv2.imread(imgPath, 0)
```

Python中cv2读入的图片转换成PIL的Image读入的图片
```python

# cv2读入3通道
img = cv2.imread(image_path)
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
im_pil = Image.fromarray(img)
```

Python中PIL的Image读入图片从mode I (16 bit灰度图像) 转换成model L （8 bit灰度图像）
```python

# 假设img_PIL是mode I
img_PIL = Image.open(image_path)

im = np.array(img_PIL)
im2 = (im // 2 ** 8).astype(np.uint8)
im3 = Image.fromarray(im2)
im3.save(image_save_path)

# img_PIL_2会显示为mode L
img_PIL_2 = Image.open(image_save_path)

```

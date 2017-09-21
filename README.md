# PythonFuncs
常用的matlab函数对应到python函数

MATLAB中开平方根的运算：sqrt(x)

	import math
	math.sqrt(x)
	x ** 0.5

MATLAB中的幂运算：^

	**

check if integer: mod(x,1); ~isinf(x) & floor(x) == x

	x.is_integer()
	
python3里面没有long这个长整型，统一由int代替

数组下标
	
	fifth_letter = "MONTY"[4] # 可以直接在声明的时候就直接取某一个值
	
取某一既带大写又带小写字母的全部大或小写的字符串

	x.upper()
	x.lower()

打印字符串

	print "Ah, so your name is ___, your quest is ___, and your favorite color is ___." ___ (name, quest, color)
	print "Ah, so your name is %s, your quest is %s, and your favorite color is %s." %s (name, quest, color)
	
与或符判断顺序：

	1 -- not is evaluated first;
	2 -- and is evaluated next;
	3 -- or is evaluated last.

def, if, else, elif都要在最后加上冒号

检测字符串是否只由字母组成

	x.isalpha()
	
MATLAB中string的连结：str4 = [str1, str2, str3]

	str4 = str1 + str2 + str3
	
检查库中函数的办法

	import module # Imports some module
	everything = dir(module) # Sets everything to a list of things from the module
	print everything # Prints 'em all!

检查变量类型

	type(x) == int or type(x) == float # 而int和float都不用加引号

MATLAB中连结矩阵元素：x = []; x = [x y];

	x = []
	x.append(y)
	x.remove(y)
	
	n.pop(index) # will remove the item at index from the list and return it to you
	n.remove(item) # will remove the actual item if it finds it
	
MATLAB向量取部分值：a(1:end); a(2:end); a(2:end-1); a(1:3)

	a[0:]
	a[1:]
	a[1:-1]
	a[0:3]

反查元素在向量中的位置，还可以在某一位置插入值

	animals = ["aardvark", "badger", "duck", "emu", "fennec fox"]
	duck_index = animals.index("duck")
	animals.insert(duck_index,"cobra")
	
	a = [1,3,4,5]
	three_index = a.index(3)
	a.insert(three_index,7)
	
向量可以直接连续用加号

	a = [1, 2, 3]
	b = [4, 5, 6]
	print a + b

字典可以直接赋值，不需要提前开辟内存空间

	dict_name = {}
	dict_name[new_key] = new_value
	
	del dict_name[key_name] # 删除
	
字典可以多维的
	
	my_dict = {
	  "fish": ["c", "a", "r", "p"],
	  "cash": -4483,
	  "luck": "good"
	}
	print my_dict["fish"][0] # 不能打印某一个key，想打印key只能遍历的方式去打印
	my_dict["fish"].sort()
	my_dict[0].remove("a")
	
字典打印key名称和key值的方法

	d = {'a': 'apple', 'b': 'berry', 'c': 'cherry'}
	for key in d:
  		print key + " " + d[key]
	
MATLAB中访问二维数组：a(1,2) = 1

	a[1][2] = 1
	
判断一个值是否在一个向量里面

	if x not in A
	if guess_row not in range(5)

字符串二维数组初始化成单一字符的使用方法

	for x in range(5):
		board.append(["O"] * 5)
	
打印在同一行

	print char, # 逗号是说明打印要在同一行
	print char # 正常打印

字符串数组还有一种遍历的方式

	choices = ['pizza', 'pasta', 'salad', 'nachos']
	print 'Your choices are:'
	for index, item in enumerate(choices):
		print index, item # 把序号和字符串的值都打出来了

有一个循环遍历多个数组

	list_a = [3, 9, 17, 15, 19]
	list_b = [2, 4, 8, 10, 30, 40, 50, 60, 70, 80, 90]
	for a, b in zip(list_a, list_b):
	
字符串替换或批量替换用replace
	
	def censor(text,word):
		if word in text:
			text = text.replace(word, "*" * len(word))
		return text
	
	censor("this hack is wack hack", "hack") # 结果为 "this **** is wack ****"
	
数组统计出现的次数

	x.count(item)
	

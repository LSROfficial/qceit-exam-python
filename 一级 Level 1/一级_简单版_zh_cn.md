# 起步阶段

1.	## 起步

Hello! 这里是你考试之路的起点。
因为目前中国电子协会 (接下来简称电协) 要求每位考生必须从一级起步, 所以这里会写的较为详细。
如果你不知道 Python 是什么, 那么我不推荐你进行考试。 你应该从了解 Python 开始。 在 Bilibili 中有较为详细的网课。
在确保自己有一定 Python 基础后, 我们开始针对考点学习。

2.	## 先知道什么是 Python

Python, 非常强大的语言。
你需要通过自我实践以了解更多。
在这里先讲述一个考点, Python 分为 `2.x` 和 `3.x` 两个版本, 现在广泛使用 `3.x` 版本, `2.x` 版本被基本弃用。

3.  ## 知道IDE

IDE 是一级考试的一个考点。 所谓 IDE 也就是你写代码的工具, 你可以理解为高级记事本。 在正式的开发中, 一般使用 `Jetbrains PyCharm` 或 `Microsoft Visual Studio Code` 进行开发, 
在考试标准中还有较为古老的 `JupyterNotebook` 等。 由于不做考试要求, 在这里不做详细介绍。
我们来了解 IDLE 的相关考点。


- ### 什么是IDLE?
	
	IDLE 是 Python 自带的 IDE。 功能简单, 轻量, 但也比较一般。
	
- ### 找到 IDLE, 打开

	在你的 Windows 开始菜单中能够找到 **`IDLE (Python 3.x 64-bit)`**。
	点开，你就进入了 IDLE 的界面。
	
- ### 一个IDE, 两种模式

	你打开 IDLE, 可以输入一些命令，但是没法换行。
	这是因为你进入的默认模式为 **`交互模式`**, 也叫 `Shell 模式` 或 `命令行模式`。
	在左上角的 `File` 中, 点开 `New File` 或 `Open`, 你就进入了 **`脚本模式`**, 也叫 `Script 模式` 或 `文件模式`。
	*ps:要考的!*

- ### IDLE 基本功能

	- 交互模式

		一般来说, 你打开交互模式后, 会显示
		
		```bash
		Python 3.12.1 (tags/v3.12.1:2305ca5, Dec  13 2099, 25:61:61) [MSC v.1937 64 bit (AMD64)] on win32
		Type "help", "copyright", "credits" or "license()" for more information.
		>>>
		```
		
		你可以尝试输入
		```Python
		print("Hello, World!")
		```
		在这之后, 终端将会输出 `Hello, World!`。
	
	- 脚本模式
		
		`File` -> `New File` 或 `Open` 以打开脚本模式。
		所谓脚本模式, 就是正常的敲代码。
		在你写完东西后, 在上面选择 `Run` -> `Run Module` -> 命名, 保存 -> 得到结果。
	
	
4.	## 知道怎么写最基本的代码

如果你有最简单的思维, 那么你走大运了。 Python 的最基本内容简单到人类都会。
毕竟:
> 人生苦短, 我用 Python。 

那么现在就看看最基本的东西。

- ### 知道基本编程的思路
	基本思路很简单。
	你喂给它一堆东西, 它想一想, 给你吐出来一堆东西。
	这就是**输入, 处理, 输出**的思想。 也叫面向过程编程。
	在实际编写的时候, 我们更喜欢使用面向对象编程。 这方面内容将在六级讲到。
	
- ### 知道怎么跟机器说话
	跟机器说话更简单。
	和语文标自然段类似。
	当你写了一段话:
	```Python
		a = 1
		if a == 1:
		print("I'm here.")
	```
	会报错。 为什么? 因为你没告诉它**这段话是属于这个if的**。 怎么告诉? 很简单, 加四个空格或一个制表符(Tab)。 考试时推荐使用四个空格。
	
	例如:
	```Python
		a = 1
		if a == 1:
			print("I'm here.")
	```
	但是这时候, 我发现话一多, 我看不懂了啊! 例如下边这段代码:
	
	```Python
	import socket
	import datetime

	HOST = "127.0.0.1"
	PORT = 3721

	try:
		server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
		server.bind((HOST, PORT))
		server.listen(5)
	except Exception as e:
		raise ConnectionError(f"Error connecting to {HOST}:{PORT},\nHere is an error message: \n{e}")

	while True:
		_connect, addr = server.accept()
		print(f"[{datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")}] 客户端 {addr} 已连接.")
		with _connect:
			while True:
				data = _connect.recv(1024)
				if not data:
					break
				print(f"收到: {data.decode()}")
				with open("message.txt", "a") as f:
					txt = (f"[{datetime.datetime.now().strftime('%Y-%m-%d %H:%M:%S')}] [Sender: {addr[0]}: {addr[1]}]\n"
						   f"\tReceived: {data.decode()}\n\n")
					f.write(txt)
				_connect.sendall(data)
		print(f"客户端 {addr} 断开连接.")
	```
	
	当你费劲啃完这段话了, 转头又忘了... 这时候你就想: 我得把这段代码什么意思记下来。
	
	但是直接写是绝对不行的, 直接报了错。
	
	我们需要告诉 Python 这段话不是代码, 是我自己给自己说的。
	
	那么我们就需要使用井号`#`。
	
	比如:
	```Python
		a = 1	# 这个 a 指的是 xxxxx
		if a == 1:
			print("I'm here.")
	```
	等到你 2000 年后再次看这段代码, 仍然能知道这个 a 指的是 xxxxx, 你就会感谢 2000 年前的自己。
	
- 知道具体怎么写
	如果前边是知道怎么以人类的方式说话, 这一段就代表着一门具体的语言。
	
	让我们先讲一级的内容。
	
	- 变量
	
		变量, 就是会变的量。
	
		听上去很简单, 实际上也确实很简单。
	
		比如我们取个变量名, 叫 a, 或者叫 b, c, d, sushi, fxxk_nvidia ......
	
		这里的变量名可以包括**大小写字母**, **数字**, **下划线(_)**, *甚至是汉字*!
		但是汉字并不推荐使用。 这里仅作为考点讲到。
		因为有一道题会考:
		> 变量名只能是字母, 数字, 下划线, 不能是其他内容。
		
		> 错误。
		
		但这个变量名不能是**关键字**。 
		
		什么是关键字?
		
		关键字就是 Python 给功能留的单词。
		
		很容易理解。 你不会让自己的孩子叫**打印**或者**同步**吧?
		
		下面是 Python 的39个关键字。
		```
		False await else import pass None async class for try break continue def finally return
		True del except global while and elif is nonlocal raise or if in with as assert lambda yield
		```
		
	- 字符串, 数值
		
		这个变量得有个初始值。
		
		你可以简单地写:
		
		```Python
		a = 1
		```
		
		这个`1`可以是任何东西。 包括数字, 文字, 甚至是一个对象, 文件。
		在一级, 我们只学习三类, 一类是**整数**(`integer`), 在 Python 中简写为 `int`,
		另一种是**浮点数**(`float`),
		还有一种是文字, 叫做**字符串**(`string`), 在 Python 中简写为 `str`。
		
		`int` 即为整数, 名如其是, 1, 2, 3, 10000, 都是整数型, 但 1.2, 8.66, 或者是 8.0, 都属于浮点型。
		`str` 是字符串, 需要使用`"`或`'`括起来。
		
		尽管 Python 对于类型限制较为宽松, 了解类型仍然是十分必要的。
		并且在实际中大大小小的方式都需要不同类型的数据。
		
		假设有一个方法叫做 `speak(some_text)` , 它的功能就是输出你给他的文本(其实就是`print()`), 需要一个字符串类型的变量, 那么我们就可以这么使用它:
		```Python
		speak("This is a message!")
		```
			
		将会输出: `This is a message!`
		
		很简单, 对吧?
		
		那么我需要塞进去一个数字, 怎么办?
		
		我可以:
		
		```Python
		speak("1231231232778")
		```
		
		输出: `1231231232778`
		
		但是我也可以这样:
		
		```Python
		speak(1231231232778)
		```
		
		明明它需要字符串型, 我却输入了整数型, 怎么可以这样?
		
		原来, Python 是拥有*隐式转换*的, 当你输入 `int` 或 `float` 时, 若需要 `str`, 便会将数值转化为字符串。
		
		你肯定会说: 老师, 我懂了!
		看我举一反三, 假设有一个方法叫 `get_digit_1(number)` , 需要一个`int`, 可以用来获取一个数字的个位数, 返回 `int` 形式, 那就可以这样:
		
		```Python
		print(get_digit_1("1231231232778"))
		```
	
		然而并非如此。
		`str` 并不能隐式转化为 `int` 或 `float`。
		但是我没法确保输入进去的是 `int`, 有可能是 `str` 怎么办?
		那么你就可以使用**显式转化**!
		这里有一个例子:
		
		```Python
		a = "1"		
		# 很明显, 这是一个字符串, 里面有一个数字1
		# 当我想要将 a 转化为 int 时, 我就:
		b = int(a)	
		# 这样我就把转为 int 后的 a 给了 b
		```
		
		注意, 当你使用 `int()` 后, 并不会返回到这个变量里, 你需要再找一个变量装它。
		与此相同的, 你可以使用 `str()` 或 `float()`。
		
		是不是很简单?
		
		到此, 你就学会了这三种类型的定义与转化了。
		
	- 表达式, 运算符, 逻辑运算
		
		我们现在来学习**表达式**, **运算符** 和 **逻辑运算**。
		
		表达式, 就是你小学学习的 1+1。
		比如我之前的变量,
		```Python
		a = 2
		```
		
		可以写为
		```Python
		a = 1 + 1
		```
		
		这里的`+`就是运算符, `1+1`就是表达式。
		
		让我们稍微复杂一点:
		```Python
		a = 1
		b = 2
		c = a + b
		```
		
		这时候, `a+b` 就是表达式。
		
		很好理解, 对吧?
		
		我们先来知道有什么运算符:
		算术运算符有这些:
			`+`, 意味着加;
			`-`, 意味着减;
			`*`, 意味着乘;
			`/`, 意味着除;
			`^`, 意味着乘方;
			
			在这之外的, 还有`%`, 意味着取模, 就是取余数。
			比如, `3%2=1` 。
			
		比较运算符有这些:
			`<`, 意味着小于;
			`>`, 意味着大于;
			`<=`, 意味着小于或等于;
			`>=`, 意味着大于或等于;
			`==`, 意味着等于.
			
		除了小学运算符, 还有一个编程语言独有的赋值运算符。 也就是之前给变量赋值的那个`=`。
		除了 `=` 外, 还有下列几种算数运算符和赋值杂交的赋值运算符:
			`+=`, 意味着让自己加上后面东西后赋值;
			`-=`, 意味着自己减去后面东西后赋值;
			`*=`, 意味着自己乘上后面东西后赋值;
			`/=`, 意味着自己除去后面东西后赋值;
			`%=`, 意味着自己取余后面东西后赋值;
		
		这里有一个赋值运算符的例子:
		```Python
		a = 10
		a += 2	# 这段代码相当于 a = a + 2, 其他运算符同理。
		print(a)
		```
		
		将会输出`12`。
		
		之后我们来了解逻辑运算。
		
		在了解逻辑运算之前, 我们要了解什么是**布尔值**(`boolean`, 在 Python 中简称为 `bool`)。
		布尔值, 说简单就是对(`True`)和不对(`False`), 还有一个空(`None`)。
		在前边的比较运算符中, `(1 < 2)` 这个表达式会返回一个 `True`, 因为 1 确实小于 2。
		
		并且 `int`, `str` 和 `float` 是可以隐式转化为 `bool` 的,
		
		所有不为 `0` 的 `int`, `0.0` 的 `float` 和 所有的 `str` 都是 **`True`**。
		0, 0.0 是 `False`。
		
		逻辑运算, 在各个语言, 甚至是机械电路中都是常客,
		他们是 **与(和)**, **或**, **非(否)**,
		也就是 `and`, `or`, `not`。
		
		`and`, 就是 **两边是否同时正确**, 他会检测它前边的东西是否为 `True`, 
		
		如果是, **直接返回后边的内容**, 否则返回 `False`。
		
		没错, 他事实上并不是检测两边是否相同, 而是检测前边的东西。
		
		类似的, `or` 也是惰性检测, 当前边的东西是 `False` 时, **返回后边的内容**, 否则返回 `True`。
		
		而 `not` 更加简单, 如果是 `True`, 变成 `False`; 如果是 `False`, 变为 `True`。
		
		这里有一个例子:
		
		```Python
		a = True
		b = 0
		c = 1
		d = 'im back 我是后背'
		print(a and b)	# False
		print(a and c)	# 1
		print(b and c)	# False
		print(b or c)	# 1
		print(not a)	# False
		print(a and d)	# im back 我是后背
		```
		
5.	## 内置库海龟

- ### 什么是库?
	
	你在学习中, 会学习许多的定理, 例如勾股定理, 牛顿第二定律等。
	如果在考试中你需要从头到尾写一遍这些定理的证明方法, 简直不要太崩溃。
	
	换到 Python 里也是一样, 你一个功能不能每次都写一遍。
	
	Python 官方和社区为你构建了许多*定理*, 叫做**库**。
	Python 官方的叫做**内置库**, 社区的叫做**第三方库**。
	你可以把它理解为一个仓库, 里面有你需要的方法。
	
- ### 怎么用?
	
	我们现在只需要学习怎么在程序里用, 关于怎么下载之类的复杂用法, 我们会在四级中讲到。
	你只需要知道内置库不用下载, 第三方库需要下载。
	
	在 Python 中, 我们使用 `import <库名>` 或 `from <库名> import <方法>`的语句导入库。
	
	```Python
	import turtle
	```
	
	这两种方法有什么区别呢?
	
	`import <库名>` 相当于把这个仓库的地址给你, 你拿这里面的东西时, 告诉系统去这个仓库里用一下这个。
	`from <库名> import <方法>` 相当于直接把这个东西拿自己的仓库里来了, 用的时候直接用就可以了。
	
	特别的, 有一种方法叫做 `from <库名> import *`, 它相当于把整个仓库搬过来了, 想用什么用什么。
	但注意, 如果你的仓库里有一个东西和搬过来的东西重名了, 那就完蛋了, 系统会不知道用哪个。
	
	在这之后, 这个库有许多的方法可供使用。
	假设有一个库叫做 `pkg_one`, 它提供一个叫做 `get_time` 的方法, 可以返回现在的时间, 那我们就可以这么导入并调用:
	
	```Python
	import pkg_one
	time = pkg_one.get_time()
	print(time)
	```
	
	我们也可以这么调用:
	
	```Python
	from pkg_one import get_time
	time = get_time()
	print(time)
	```
	
	或是:
	
	```Python
	from pkg_one import *
	time = get_time()
	print(time)
	```
	
- ### 海龟

	在一级, 我们需要重点掌握一个内置库, 叫做**海龟**(`Turtle`)。
	
	海龟, 是一个 Python 自带的绘画工具库, 可以给你个画板, 让你用代码画图。
	
	我们了解一些 `turtle` 的基本用法。
	
	- 基本
		
		海龟库使用一根画笔, 在开头导入库之后, 我们使用
		
		```Python
		pen = turtle.pen()	# 你也可以搞一个海龟, 那样就是 turtle.turtle()
		```
		
		来生成一根画笔。
		这根画笔是一切。
		
		之后, 我们在画完画后, 要写一行 `turtle.done()`, 代表我画完了。
		
		**重要** 海龟的坐标系和数学坐标系一样, 以中心点作为原点。
		
	- 设置画笔属性
	
		`turtle.color(color)`		设置画笔颜色，支持字符串, 如 `"red"`; 或 RGB, 如`(255, 255, 255)`

		`turtle.fillcolor(color)`	设置填充颜色, 同上

		`turtle.begin_fill()`		开始填充区域

		`turtle.end_fill()`			结束填充区域

		`turtle.pensize(width)`		设置画笔宽度, `width` 为宽度
	
	- 控制画笔移动
	
		`turtle.forward(x)`			(重要) 向前移动 `x` 像素

		`turtle.backward(x)`		(重要) 向后移动 `x` 像素

		`turtle.left(angle)`		(重要) 向左旋转指定角度（角度制）

		`turtle.right(angle)`		(重要) 向右旋转指定角度（角度制）

		`turtle.penup()`			(重要) 提起画笔（移动时不绘制轨迹）

		`turtle.pendown()`			(重要) 放下画笔（移动时绘制轨迹）

		`turtle.goto(x, y)`			移动到坐标 `(x, y)`

		`turtle.speed(speed)`		设置绘图速度, 范围从 0（最快）到 10
		
	- 画圆
		
		`t.circle(r)`				画圆, `r` 为半径
		
		注意, 它并不是以当前坐标作为圆心, 而是**以当前坐标绕一圈回到原点**!
		
	以下是画一个正方形的演示:
	 
	```Python
	import turtle

	pen = turtle.Pen()
	pen.speed(0)

	pen.hideturtle()
	pen.penup()
	pen.goto(-300,300) 
	pen.pendown() 
	pen.speed(1) 
	
	pen.forward(100)
	pen.right(90)
	pen.forward(100)
	pen.right(90)
	pen.forward(100)
	pen.right(90)
	pen.forward(100)
	pen.right(90)
	
	turtle.done()
	```
	
至此, 我们就学习完了一级的基本内容, 是不是很简单?

你可以[点击这里|./二级%20Level%202/二级_简单版.md]进入下一章。
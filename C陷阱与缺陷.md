C陷阱与缺陷
[TOC]
#第一章 词法陷阱
##1.5字符与字符串
	单引号包含的字符代表整数，双引号包含的字符串代表数组指针(绝大部分)
#第二章 语法陷阱
##2.1 理解函数声明
	pt() 是 *pt()
##2.2 运算符优先级
	不确定的差表，加括号
##2.3 句尾分号
	1.return后加分号
	2.声明后加分号，否则可能作为函数返回值类型。
##2.5 函数调用
	f() 括号为函数参数，C语言要求即使函数不带参数也应该包括参数列表。因此 f 只计算函数地址，不调用函数
#第三章 语义陷阱
##3.1 指针与数组
	1.C语言只有一维数组，但数组元素可以任意，但需要长度相同。数组大小需要固定(ASIC)/不固定(C99)
	2.对数组只能sizeof 和 取首元素的指针
	3.当数组指针不用于sizeof 其总会被转换为指向首元素的指针
##3.6 边界计算与不对称边界
	1.用第一个入界点与第一个出界点表示数组范围  x = 0 || x < 16
##3.7 求值顺序
	1.对于 && 或 || 只有需要时才对右侧操作数求值
##3.9 整数溢出
	未预见，但需要考虑
#第六章 预处理器
##6.1 宏定义不能多空格
	#define f (x)  ((x) - 1) 错误
	#define f(x)  ((x) - 1) 
##6.2 宏不是函数
    在一个表达式内出现两次宏参数的不能使用++ / --

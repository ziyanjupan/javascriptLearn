##js定位
+ 核心js
+ 客户端js


<script type='text/javascript'> 的type要写（浏览器兼容性）
type还可以 为vbscript（仅ie）、 acomscript（兼容性不好）


###命名规范：
小写下划线：print_log 
骆驼命名法:printLog

###控制台：
console.log('Hello World');
会打印两行：
1.代码执行的结果 Hello World
2.值（函数的返回值、表达式的值） undefined

IE的两行 先2，后1

火狐 firebug

##基础语法
###基本变量与数据类型
var声明变量，用分号结尾
`var num;`
js是弱类型语言（没有类型之分）





###js的弱类型,可以随意改变数据的类型
var num=1;//number
num="123";//string
num=console.log;//function
（会自动加;前提是换行）
###运算符
####typeof运算符
语法： string typeof 变量或数据   
返回数据的类型对应的字符串
数学运算符 + - * / %
赋值运算符 = += ...
位运算符（WebGL等用到【three.js】）
new运算 创建对象
is运算 判断属性是否属于某个对象
delete 删除一个成员
instanceof 判断对象的构造方法
条件运算符 true ?表达式1:表达式2
逻辑运算符 || && ！
相等运算符 ==(判断值相等)  ===（判断值和类型都相等）
var n1=null;
var n2=undefined;
n1==n2;//true  有一个自动转换成同一个数据类型 ('true'==true;//false )引用类型比较地址
n1===n2;//false
 
###流程控制
选择结构
if(不一定是boolean类型【数据类型转换】)
switch case
循环结构
while(){}
for(item in arr)//遍历的是索引 item
要输出 arr[item]
代码分析
数组的元素类型可以是各种数据类型
###函数
###对象
###常用对象
###高级





###自调用函数(沙箱模式)

	(function () {
		// 方法体
	})();
	在定义自己的同时，调用自己
	-> 在沙箱中运行
	-> js有什么关系呢？
		js常常是多个库混合在一起使用
		<script src="..."></script>
	-> 在js中函数可以限定一个变量的作用域

###作用域链
	-> 作用域链就是一个变量的数组
	-> 要求：学会绘制作用域链图
	-> 步骤：
		1、从script标签开始是第0链
			依次记录script标签中声明的变量(包括函数等)
			顺序是从上到下，从左到右
		2、凡是看到了函数，那么从函数定义开始，启用一个新链
			那么这个就是第1链，再在函数内重新统计里面的变量绘制第1链
			在变量的统计中，只考虑使用var声明的变量
		3、如此可能会有多条第1链，其关系为兄弟
		4、如此往复，得到一个树状图谱，即为作用域链
			由于一节一节的链接起来，称其为链
	-> 凡是代码访问变量的时候，讲究一个规则
		从代码访问开始往上找变量的数据，首先在当前链中找，如果找到就使用这个数据
		如果没有找到，就往上一级链中找(第2链往第1链中找)，如果还没找到，就在网上
		直到到达0级作用于链，还没有就跑出一个错误

	-> 函数中访问某个成员，首先看当前函数中是否使用var声明了这个成员
		如果声明了，就使用这个，否则往上一级找，直到出现异常

###闭包
	-> 在函数中声明的变量，无法在函数外访问，那么这个时候就构成了闭包
		var f = function() {
			var num = 123;
		};
	-> 可以得到一个能够存储数据的函数
		var func = (function() {
			return function() {
			
			};
		})();


###arguments

###变量名提升，函数名提升

声明式 (函数名提升【变量名提升，作用域】)


定义式


###函数的4种调用模式

函数 方法 构造器 上下文 （this的不同：window，当前对象，刚创建的对象（改写return功能））


模拟重载

###函数与构造函数的区别

模拟next

对象和数组相似（区别在于length属性）

关联数组


Function是所有函数的基本类型

###正则替换


prototype（函数属性），__proto__（对象属性）,constractor


###上下文调用模式
func.apply(obj,array);
func.call(obj,arg1,arg2);
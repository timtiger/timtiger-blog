# 《代码整洁之道》

## 代码保持整洁，如何说服产品和Leader争取时间去保持整洁？

  混乱的代码只会拖累自己，耽误更多的时间。要想做得快，代码就得写的好。

## 有意义的命名

### 名副其实

例如，一个消息数组命名
bad: list
better: messages

### 避免误导

例如：一个国家名称与简称的Map对象。
bad: countries
good: countryByCodeMap

### 做有意义的区分

如爸爸妈妈女儿三个变量命名
bad: p1, p2, p3
good: father, mother, daughter

### 使用读得出来的名称

就别自己创造一些无法读出来的单词

### 使用可搜索的名称

假设你命名为e, 搜索这个变量的时候会搜索到太多无关的地方

### 类名

类名应该是名词或者名词短语。例如Customer,WikiPage等。应该避免使用Manager,Processor, Data 或Info这样的类名。类名不应当是动词

### 方法名

方法名应当是动词或者动词短语，如deletePage,update或save。

## 函数

### 短小

作者推荐120行以内最佳。

### 只做一件事

你懂的

### 每个函数一个抽象层级

大概意思就是一个函数里面做的事情是一个层面的事。比如修改UI就只做修改UI，你别把字符串拼接的代码写在一起。修改UI和拼接字符串是两个不同层级的事。

然后代码最好是自订向下按调用顺序排列

### Switch语句

一但用到Switch语句实际上就表明了这个函数做了不止一件事。不过要确保每个case分支都是干的抽象层级相同的事情。比如三个case跳转到三个不同的界面，执行的都是跳转界面操作。

### 使用具有描述性的名称

比如删除账号的响应函数。delete就不够好，而deleteAccount就描述得很清楚了。

### 函数参数

没有参数最佳，1个参数次之，2个参数可以接受，最多不要超过三个参数。参数传一个布尔值是愚蠢的，明摆着就是在说此函数至少干了两件事。

### 无副作用

做的事基本和函数名吻合，不要多做事也不要少做事。比如你在deleteAccount的函数里刷新了界面就是事情做多了，有副作用。

### 分隔指令与询问

大致意思就是一个函数要么就是纯回答问题，要么就是纯执行指令。不要两件事都干

### 使用异常代替返回错误码

当函数执行错误的时候尽量抛出异常，而不是return一个错误码。

### 别重复自己

就是一样的代码别拷贝来拷贝去的搞的到处都是。

## 注释

好的代码一眼就能看懂，不需要注释。但也不能盲目不写注释。总之要把自己放到读者的角度，一眼能看懂代码。

## 格式

使用大家常用的格式化工具即可，团队可以指定自己的格式和规则

## 对象

参数过多的时候，使用对象作为参数。

## 错误处理

定义错误基类，让各种错误在基类上去定义子类

## 边界

使用第三方代码时应该做好包装，不要让第三方代码在项目里到处都是。

## 单元测试

TDD测试驱动开发，先把测试用例都枚举了，再开发代码

## 类

尽量短小精悍，高内聚低耦合，不可盲目在项目里使用太多的类和方法。

## 系统

将系统的构造和使用分开

## 迭代

不停的迭代自己的程序

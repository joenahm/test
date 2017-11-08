# JavaScript知识点

<a id="1" name="1"></a>

### 1. 基础

<a id="1.1" name="1.1"></a>

#### 1.1 基本语句

<a id="1.1.1" name="1.1.1"></a>

- **1.1.1 script标签和外部js文件 : 如何给网页添加js代码**

**JavaScript一般放在网页的`<script></script>`标签中间，也可以放在外部文件里（如script.js,1.1.1.js）。**

后半句话说明了放在外部js文件中的语句和`<script></script>`标签中的语句是同等级的，所以在外部js文件中的语句不应该加`<script></script>`标签。

**外部文件的引用方式是`<script src="文件地址"></script>`。**

比如当前目录中有一个"1.1.1.js",我可以通过`<script src="1.1.1.js"></script>`来引用它。这样它的内容就和写在当前网页中一样了。

**`<script></script>`标签可以放在`<head></head>`或`<body></body>`标签中，但是通常把它放在`<body></body>`标签的后边。**

比如：
```
<body>
	假装这里有很多HTML标签。。。
</body>
<script>
	alert("我叫李秀丽，我喜欢森健太郎！可是小野也喜欢他，我该怎么办呢？把森调职到中国来！(详见新标日初级上下册)");
</script>
```

这就是一个正常的`<script></script>`标签。对了，`alert()`是js的一个方法（就是函数），他能弹出一个小窗口，告诉你一点事情（也许有时你并不想知道）。

#### [点击去练一手！~](http://sjydzq.top/web/rensyuu.php?id=1509801967&type=js)

<a id="1.1.2" name="1.1.2"></a>

- **1.1.2 js的基本语法**

```
输出语句 : alert(xx)
学习一门语言怎么能不先学输出语句呢，我们需要用它来查看我们代码的效果啊
这个输出语句我们在上小节中已经接触过了，他就是一个能展示信息的小弹窗，使用起来十分方便。
我们可以把示例中的xx换成你想输出的任何东西！（请记住这句话）
另外，我们以后还会详细的介绍alert()方法的，这里只是图方便直接拿来用用（笑）
```
**变量声明与定义**

很高兴的告诉你，js是一门弱类型的语言。

什么叫弱类型？就是你定义一个变量的时候不用再操心它是int还是float了，直接一个var上去就好了（甚至连var都不需要！）。

比如：
```
var a = 1;	//定义了一个变量
b = 2;		//同样定义了另一个变量
c = "我是一个字符串";	//定义了一个字符串
d = [1,2,3];	//定义了一个数组，注意这里是方括号，不是花括号！
e = ["aaa","bbb","ccc"];	//定义了一个字符串数组
...
```
如果你明白了我在说什么，并且你c语言具有一定基础，你可能会哇的一下哭出来。

妈的，有这么方便好用的东西，我还学他喵喵喵的c语言啊！它有它方便的地方自然就有它不好的地方咯，至于哪里不好有兴趣的同学请自行百度。而且想知道用var定义的变量和不用var定义的变量有什么区别的同学也请自行百度。（**今后我统一使用用var定义的变量**）

好，继续，我们已经知道了输出语句，然后知道变量的定义了。我们就可以输出自己定义的变量了!~好吧，虽然有点傻，不过确实可以了。
```
/*(基于上面语句块的定义)*/
alert(a) 	//会输出1
alert(d) 	//会输出整个数组，即，1,2,3
...
/*其他以此类推*/
```
哦对了，你不会不知道`//`和`/**/`是注释吧，好了现在你知道了...啥？啥叫注释？注释就是给人看到的字儿，电脑不执行，对电脑来说，注释了的东西就相当于不存在。

**条件分支与循环**

说实话，c语言基础好的同学可以跳过这一段，因为和c语言的完全一样！**哎，别别，还真有不一样的！**

和c语言一样的部分：

条件分支
```
if(条件1){
	语句1;
}else if(条件2){
	语句2;
}else{
	语句3;
}//这个就不用我再说什么了吧，我再说那是侮辱你...
```
```
switch(待判断变量){
	case 条件1:
		语句1;
		break;
	case 条件2:
		语句2;
		break;
	default :
		语句3;
}//这个也和c的几乎一样，只不过待判断变量可以是任何类型
```

循环
```
while(条件){
	语句;
}
```
```
do{
	语句;
}while(条件);
```
```
for( 变量初始化 ; 结束条件 ; 变量更改){
	语句;
}
```

和c语言不一样的部分：

**for...in循环**
```
for(变量 in 集合){
	语句;
}
```
说实话，这个循环方式好用的一匹！因为你啥都不用管，啥都不用问，直接数组啥的往里丢，就可以用了

比如：
```
var arr = [1,2,3];
for( i in arr ){
	alert(arr[i]);
}
```
这样你就能遍历输出一个数组了，怎么样，是不是很简单？

**函数定义与调用**

js的函数定义也和以上特征一样，具有不跟你多BB的特点

比如：
```
function 函数名(参数表){
	函数体
}
```
怎么样，是不是很简单？啥，没看出来？那与c对比一下

```
/*c语言的max()函数定义*/
int max(int a, int b){
	if( a > b ){
		return a;
	}else{
		return b;
	}
}

/*js的max()函数定义*/
function max(a, b){
	if( a > b ){
		return a;
	}else{
		return b;
	}
}
```

现在细心的同学可能已经发现了，在js里用`function`关键字来定义函数，并且`返回值类型`和`参数类型`也都不需要我们来关心。这点看似并不怎么大的变化，将在实际使用中带来数不尽的好处（当然，也许会产生同样多甚至更多的麻烦，取决于使用者，哈哈）。

好了，到这里js的基本语法已经学完了，恭喜！
#### [点击去练一手！~](http://sjydzq.top/web/rensyuu.php?id=1510110156&type=js)
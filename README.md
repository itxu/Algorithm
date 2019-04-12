README
===========================

I have managed all the `markdown` grammar, please let me know or issue me if I left something behind or used some inappropriate words . Thanks.

****
## Table of Contents
* [Seperator](#Seperator)
* [Title](#Title)
* [Text](#Text)
    * General
    * Single Line
    * Multiple Line
    * Highlighting
    * Wrapping
    * Italic
    * Bold
    * Delete Line
* [Image](#Image)
    * Source From Internet
    * Source From GitHub Repository
* [Link](#Link) 
    * Super-link
        *  Outter URL
        *   Repository URL
    *  Anchor
    * [Image Link](#Image Link)
* [Table](#Table)
    * Disorder
    * Order
    * Check box
* [Block Reference](#BlockReference)
* [Code Highlighting](#CodeHighlighting)
* [Table](#Table) 
* [Emoji](#Emoji)
* [diff use](#diffUse)

<pre>
## Table of Contents
* [Seperator](#Seperator)
* [Title](#Title)
* [Text](#Text)
    * General
    * Single Line
    * Multiple Line
    * Highlighting
    * Wrapping
    * Italic
    * Bold
    * Delete Line
* [Image](#Image)
    * Source From Internet
    * Source From GitHub Repository
* [Link](#Link) 
    * Super-link
        *  Outter URL
        *  Repository URL
    *  Anchor
    * [Image Link](#Image Link)
* [Table](#Table)
    * Disorder
    * Order
    * Check box
* [Block Reference](#BlockReference)
* [Code Highlighting](#CodeHighlighting)
* [Table](#Table) 
* [Emoji](#Emoji)
* [diff use](#diffUse)
</pre>


### Seperator
-----------

***
<pre>***</pre>
or
<pre>---</pre>
or
<pre>___</pre>

---

Title
------

# h1 size 
<pre># h1 size </pre>
## h2 size 
<pre>## h2 size </pre>
### h3 size 
<pre>### h3 size </pre>
#### h4 size
<pre>#### h4 size</pre>
##### h5 size
<pre>##### h5 size</pre>
###### h6 size   
<pre>###### h6 size </pre>

Text
------
### General
This is a general text
<pre>This is a general text</pre>
### Single Line
   Place 1 tab or 4 space in the head.
<pre>    This is a general text</pre>
### Block
#### method 1
Place 1 tab or 4 space in a row in the head

    Example
    Example
    Example

<pre>
    Example
    Example
    Example
</pre>

#### method 2

```
Example
Example
Exampe
```
<pre>
```
Example
Example
Exampe
```
</pre>


### Hightlight
`This` is the word i want to hightlight  

<pre>
`This` is the word i want to hightlight
</pre>


#### Wrapping
Return or Enter button can't turn to next line    
Type two space at the end can turn to next line  
Or Live a emply line between two sentence

#### Italic Bold DeleteLine

|Code|Result|
|----|-----|
|`*Italic1*`|*Italic1*|
|`_Italic2_`| _Italic2_|
|`**Bold1**`|**Bold1**|
|`__Bold2__`|__Bold2__|
|`~~DelectLine~~`|~~DelectLine~~|
|`***Italic&Bold1***`|***Italic&Bold1***|
|`___Italic&Bold2___`|___Italic&Bold___|
|`***~~Italic&Bold&DelectLine~~***`|***~~Italic&Bold&DelectLine1~~***|
|`~~***Italic&Bold&DelectLine2***~~`|~~***Italic&Bold&DelectLine2***~~|

<pre>
|Code|Result|
|----|-----|
|`*Italic1*`|*Italic1*|
|`_Italic2_`| _Italic2_|
|`**Bold1**`|**Bold1**|
|`__Bold2__`|__Bold2__|
|`~~DelectLine~~`|~~DelectLine~~|
|`***Italic&Bold1***`|***Italic&Bold1***|
|`___Italic&Bold2___`|___Italic&Bold___|
|`***~~Italic&Bold&DelectLine~~***`|***~~Italic&Bold&DelectLine1~~***|
|`~~***Italic&Bold&DelectLine2***~~`|~~***Italic&Bold&DelectLine2***~~|
</pre>


Image
------
Use：
```
![alt](URL title)
```
alt and tilte is keyword in html (omitable):  
-alt means the words displayed when faill to load image  
-title means the words displayed when hover your mouse on it (quote required)  

The URL is the url address of the image. If you refer to the image in the same repository you can use the **relative path** directly. If you refer to the images in other github repositories, you should use full path like:

```
https://github.com/520/../img.png
```

|#|Code|Result|
|---|---|----
|1|`![baidu](http://www.baidu.com/img/bdlogo.gif "百度logo")`|![baidu](http://www.baidu.com/img/bdlogo.gif "Baidu logo")
|2|`![][foryou]`|![][foryou]

注意例2的写法使用了**URL标识符**的形式，在[链接](#链接)一节有介绍。
>在文末有foryou的定义：
```
[foryou]:https://github.com/guodongxiaren/ImageCache/raw/master/Logo/foryou.gif
```

Link
------
### Outter URL

|#|Code|Result|
|---|----|-----|
|1|`[My Github Page](https://github.com/520 "I love github")`|[My Github Page](https://github.com/520 "i love github")|

<pre>
|#|Code|Result|
|---|----|-----|
|1|`[My Github Page](https://github.com/520 "I love github")`|[My Github Page](https://github.com/520 "i love github")|
</pre>

语法2由两部分组成：
- 第一部分使用两个中括号，[ ]里的标识符（本例中zhihu），可以是数字，字母等的组合，标识符上下对应就行了（**姑且称之为URL标识符**）
- 第二部分标记实际URL。

>使用URL标识符能达到复用的目的，一般把全文所有的URL标识符统一放在文章末尾，这样看起来比较干净。
>>URL标识符是我起的名字，不知道是否准确。囧。。

### Inner URL
|Code|Result|
|----|-----|
|`[我的简介](/example/profile.md)`|[我的简介](/example/profile.md)|
|`[example](./example)`|[example](./example)|


### Anchor
(#title) like anchor in HTML. It can be used with any title.


|Code|Result|
|---|---|
|`[To The Top](#readme)`|[To The Top](#readme)|

<pre>
|Code|Result|
|---|---|
|`[To The Top](#readme)`|[To The Top](#readme)|
</pre>

不过要注意，标题中的英文字母都被转化为**小写字母**了。
> 以前GitHub对中文支持的不好，所以中文标题不能正确识别为锚点，但是现在已经没问题啦！

## Table
### Disorder

* I
- Love
* Github

<pre>
* I
- Love
* Github
</pre>


### Multiple Layer Disorder

* I
    * Love
        * Github
        
<pre>
* I
    * Love
        * Github
</pre>
            

### Order

1. I
2. Love
3. Github

<pre>
1. I
2. Love
3. Github
</pre>


### Multiple Layer Order
和无序列表一样，有序列表也有多级结构。
#### 语法
```
1. 这是一级的有序列表，数字1还是1
   1. 这是二级的有序列表，阿拉伯数字在显示的时候变成了罗马数字
      1. 这是三级的有序列表，数字在显示的时候变成了英文字母
```

#### 效果

1. 这是一级的有序列表，数字1还是1
   1. 这是二级的有序列表，阿拉伯数字在显示的时候变成了罗马数字
      1. 这是三级的有序列表，数字在显示的时候变成了英文字母
	 

### Check Box
- [x] check
- [ ] uncheck

<pre>
- [x] check
- [ ] uncheck
</pre>

您可以使用这个功能来标注某个项目各项任务的完成情况。
> Tip:
>> 在GitHub的**issue**中使用该语法是可以实时点击复选框来勾选或解除勾选的，而无需修改issue原文。

## Block Reference

### 常用于引用文本
#### 文本摘自《深入理解计算机系统》P27
　令人吃惊的是，在哪种字节顺序是合适的这个问题上，人们表现得非常情绪化。实际上术语“little endian”（小端）和“big endian”（大端）出自Jonathan Swift的《格利佛游记》一书，其中交战的两个派别无法就应该从哪一端打开一个半熟的鸡蛋达成一致。因此，争论沦为关于社会政治的争论。只要选择了一种规则并且始终如一的坚持，其实对于哪种字节排序的选择都是任意的。
> **“端”（endian）的起源**  
以下是Jonathan Swift在1726年关于大小端之争历史的描述：  
“……下面我要告诉你的是，Lilliput和Blefuscu这两大强国在过去36个月里一直在苦战。战争开始是由于以下的原因：我们大家都认为，吃鸡蛋前，原始的方法是打破鸡蛋较大的一端，可是当今的皇帝的祖父小时候吃鸡蛋，一次按古法打鸡蛋时碰巧将一个手指弄破了，因此他的父亲，当时的皇帝，就下了一道敕令，命令全体臣民吃鸡蛋时打破较小的一端，违令者重罚。”

### 块引用有多级结构
#### 语法
```
> 数据结构
>> 树
>>> 二叉树
>>>> 平衡二叉树
>>>>> 满二叉树
```
#### 效果
> 数据结构
>> 树
>>> 二叉树
>>>> 平衡二叉树
>>>>> 满二叉树

Code Hightlight
----------

```Java
public static void main(String[]args){} //Java
```
```c
int main(int argc, char *argv[]) //C
```
```Bash
echo "hello GitHub" #Bash
```
```javascript
document.getElementById("myH1").innerHTML="Welcome to my Homepage"; //javascipt
```
```cpp
string &operator+(const string& A,const string& B) //cpp
```

<pre>
```Java
public static void main(String[]args){} //Java
```
```c
int main(int argc, char *argv[]) //C
```
```Bash
echo "hello GitHub" #Bash
```
```javascript
document.getElementById("myH1").innerHTML="Welcome to my Homepage"; //javascipt
```
```cpp
string &operator+(const string& A,const string& B) //cpp
```
</pre>


Table
--------

Colume1  | Colume2|
--------- | --------|
Unit1  | Unit2 |
Unit3  | Unit4 |

<pre>
Colume1  | Colume2|
--------- | --------|
Unit1  | Unit2 |
Unit3  | Unit4 |
</pre>

### Alignment

| Left | Center  | Right |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |

<pre>
| Left | Center  | Right |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |
</pre>



Emoji
----------
Github的Markdown语法支持添加emoji表情，输入不同的符号码（两个冒号包围的字符）可以显示出不同的表情。

比如`:blush:`，可以显示:blush:。

具体每一个表情的符号码，可以查询GitHub的官方网页[http://www.emoji-cheat-sheet.com](http://www.emoji-cheat-sheet.com)。

但是这个网页每次都打开**奇慢**。。所以我整理到了本repo中，大家可以直接在此查看[emoji](./emoji.md)。

diff Use
---------
版本控制的系统中都少不了diff的功能，即展示一个文件内容的增加与删除。
GFM中可以显示的展示diff效果。使用绿色表示新增，红色表示删除。
#### 语法
其语法与代码高亮类似，只是在三个反引号后面写diff，
并且其内容中，以 `+ `开头表示新增，`- `开头表示删除。

#### 效果

```diff
+ 鸟宿池边树，僧敲月下门
- 鸟宿池边树，僧推月下门
```



--------------------------------

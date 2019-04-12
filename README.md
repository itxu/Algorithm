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
<pre>
1. No change in first layer
   1. Changed to roman number in second layer
      1. Changed to alphabet in third layer
</pre>


1. No change in first layer
   1. Changed to roman number in second layer
      1. Changed to alphabet in third layer
	 

### Check Box
- [x] check
- [ ] uncheck

<pre>
- [x] check
- [ ] uncheck
</pre>


## Block Reference


> **All alphabets in keyborad**  
qwertyuiop  
asdfghjkl  
zxcvbnm  

<pre>
> **All alphabets in keyborad**  
qwertyuiop  
asdfghjkl  
zxcvbnm  
</pre>

### Multiple Construction in Block Reference

> Data Structure
>> Tree
>>> Binary tree
>>>> Balanced binary tree
>>>>> Fully balanced binary tree

<pre>
> Data Structure
>> Tree
>>> Binary tree
>>>> Balanced binary tree
>>>>> Fully balanced binary tree
</pre>

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
Github's Markdown support emoji  
:blush:。
`:blush:`

Check emoji signal below
[https://www.emoji-cheat-sheet.com](http://www.emoji-cheat-sheet.com)。

or check it in my place[emoji](./emoji.md)。

diff Use
---------
add diff keyword behind three back quote and + means add, - means remove



```diff
+ plus means to add
- minues means  to remove
```

<pre>
```diff
+ plus means to add
- minues means to remove
```
</pre>

--------------------------------

## vim的按键功能

>经常使用vim，但是只会简单的几个命令，对vim的高级操作基本一窍不通，所以抽时间整理了常用的按键功能可以当做一个vim的查询手册。

#### 一般模式
>三种模式中只有一般模式可以与编辑模式和命令行模式相互切换，编辑模式和命令行模式不能切换。一般模式可以进行光标的移动、复制、粘贴、查找和替换等。

**按键操作** | **作用** | **类别** |
---- | --- | ---- |
h或者左箭头 | 光标向左移动一个字符  | 移动
j或者下箭头[^1] | 光标向下移动一个字符  | 移动 
k或者上箭头 | 光标向上移动一个字符  | 移动
l或者右箭头 | 光标向右移动一个字符  | 移动
Ctrl+f    | page down， 向下移动一页 | 移动
Ctrl+b    | page up，向上移动一页    |移动
Ctrl+d    | 向下移动半页    | 移动
Ctrl+u    | 向上移动半页    | 移动
num+space[^2] | 向右移动num个字符 | 移动
0    | 移动到本行的最前面 | 移动
$    | 移动到本行的最后面 | 移动
G    | 移动到本文件的最后一行 | 移动
nG   | 移动到本文件的第n行 |移动
gg   | 移动到本文件的第一行 |移动
N+Enter | 光标向下移动N行 | 移动
/word   | 向下查找名为word的字符串 | 查找
?word   | 向上查找名为word的字符串 | 查找
n[^3]    | 重复前一个查找操作，向下查找字符 | 查找
N    | 重复前一个查找操作，向上查找字符 | 查找
:n1,n2s/word1/word2/g | 在第n1行到n2行查找为word1的字符，并替换为word2 | 替换
:n1,n2s/word2/word2/gc | 与上个类似，但是每次替换需要用户confirm | 替换
:1,$s/word1/word2/g | 全文查找word替换为Word2 | 替换
:1,$s/word1/word2/gc | 全文查找word1，用户confirm替换为word2 | 替换
x,X    | x向后删除一个字符（Del），X向前删除一个字符（backspace） | 删除
nx    | 向后删除n个字符 | 删除
dd    | 删除光标所在行 | 删除
ndd    | 删除光标所在的向下n行 | 删除
d1G    | 删除光标所在向上到第一行    | 删除
dG    | 删除光标所在到最后一行 | 删除
d$    | 删除光标所在到该行的最后一个字符 | 删除
d0 | 删除光标所在到改行的第一个字符 | 删除
yy | 复制光标所在行 | 复制
nyy | 复制光标所在向下n行 | 复制
y1G | 复制光标所在行到第一行的所有数据 | 复制
yG | 复制光标所在行到最后一行的书友数据 | 复制
y$ | 复制光标所在位置到该行的最后一个字符 | 复制
y0 | 复制光标所在位置到该行的第一个字符 | 复制
p,P | p为将复制的内容在光标下一行粘贴， P为粘贴在光标上一行 | 粘贴
J | 将光标所在行与下一行的数据结合为同一行 | 连接
u | undo，复原前一个操作 | 恢复
Ctrl+r[^4] | redo，重复上一个操作 | 

---

#### 一般模式切换到编辑模式可用的按键

**按键操作** | **作用** | **类别** |
--- | --- | ---- |
i,I | 进入插入模式，i为从当前光标出插入，I为当前所在行的第一个非空空格符出插入 | insert mode
a,A | 进入插入模式，a为当前光标的下一个字符出插入，A为从光标所在行的最后一个字符出开始插入| insert mode
o,O | 进入插入模式，o为当前光标所在的下一行处插入新的一行，O为在当前光标所在处的上一行插入新的一行 | insert mode
r,R | 进入插入替换模式，r只会替换光标所在的那一个字符一次，R会一直替换光标所在的文字，知道按下ESC为止 | replace mode
ESC | 退出编辑模式，回到一般模式 | 

---

#### 一般模式切换到命令行模式的可用按键

**按键操作** | **作用** | **类别** |
---- | --- | ---- |
:w | 将编辑的文件写入到硬盘文件中 | 保存
:w! | 当文件属性为“只读”时，强制写入该文件，权限相关 | 保存
:q | 离开 | 退出
:q! | 强制退出，不保存 | 退出
:wq | 保存后离开，wq!为强制保存退出 | 保存退出
:ZZ | 如果文件没有改动，离开，如果发生了改动则保存后离开 | 保存退出
:w filename | 另存为 | 保存
:r filename | 在编辑的数据中读入另一个文件，将filename的内容加到光标后面 | 
:n1,n2 w filename | 将n1到n2行的内容保存到filename | 保存
:! command | 暂时离开vim 到命令行模式下查看command的显示结果 | 
:set nu | 显示行号 |
:set nonu | 不显示行号 | 

---

[^1]:如果想进行多次移动的话，可以使用数字加上相关按键，比如我们需要向下移动10行，可以使用```10j```或者```10下箭头```。
[^2]:数字➕空格。
[^3]:通常n或者N配合/word可以重复的查找字符。
[^4]:u和Ctrl+r是非常重用的操作。

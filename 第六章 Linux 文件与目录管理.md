### 目录与路径

#### 相对路径与绝对路径
绝对路径：路径的写法“一定由根目录/写起” 例如：/usr/share/doc 目录
相对路径：路径的写法“不是由/写起”  相对于目前工作目录的路径


相对路径：简单而言就是方便
绝对路径：正确度要比较好

#### 目录的相关操作
![6.1.2.1](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6-1-2-1.png)

常见的处理目录的指令：
- cd:变换目录
- pwd：显示目前的目录
- mkdir:创建新的目录
- rmdir：删除一个空的目录
##### cd
主文件夹时  提示符中会包含“~”

##### mkdir
![6.1.2.2](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6-1-2-2.png)

##### rmdir
![6.1.2.3](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6-1-2-3.png)


#### 关于可执行文件路径的变量：$PATH
当我们在执行一个指令的时候，举例来说“ls”好了，系统会依照PATH的设置去每个PATH定义的目录下搜寻文件名为ls的可执行文件， 如果在PATH定义的目录中含有多个文件名为ls的可执行文件，那么先搜寻到的同名指令先被执行！

##### 谨记几点
- 不同身份使用者默认的PATH不同，默认能够随意执行的指令也不同（如root与dmtsai）； 
- PATH是可以修改的； 
- 使用绝对路径或相对路径直接指定某个指令的文件名来执行，会比搜寻PATH来的正确； 
- 指令应该要放置到正确的目录下，执行才会比较方便； 
- 本目录（.）最好不要放到PATH当中。
***
### 文件与目录管理
#### 文件与目录的检视：ls
![6.2.1.1](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6-2-1-1.png)

#### 复制、删除和移动：cp，rm，mv

##### cp（复制文件或目录）
![6.2.2.1](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6-2-2-1.png)

范例：
![6.2.2.2](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6-2-2-2.png)
![6.2.2.3](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6-2-2-3.png)
![6.2.2.4](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6-2-2-4.png)

谨记：
- 是否需要完整的保留来源文件的信息？ 
- 来源文件是否为链接文件 （symbolic link file）？ 
- 来源文件是否为特殊的文件，例如 FIFO, socket 等？ 
- 来源文件是否为目录？


##### rm（移除文件或目录）
![6.2.2.5](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6-2-2-5.png)


##### mv（移动文件和目录）
![6.2.2.6](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6-2-2-6.png)


#### 取得路径的文件名称和目录名称

basename 与 dirname
![6.2.3.1](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6.2.3.1.png)


### 文件内容查阅

- cat 由第一行开始显示文件内容 
- tac 从最后一行开始显示，可以看出 tac 是 cat 的倒着写！  
- nl 显示的时候，顺道输出行号！ 
- more 一页一页的显示文件内容 
- less 与 more 类似，但是比 more 更好的是，他可以往前翻页！ 
- head 只看头几行 
- tail 只看尾巴几行 
- od 以二进制的方式读取文件内容！

#### 直接检视文件内容
cat/tac/nl
##### cat
![6.3.1.1](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6.3.1.1.png)

##### tac
反向 cat
##### nl（添加行号打印）
！[6.3.1.2](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6.3.1.2.png)

#### 可翻页检视
##### more（一页一页翻动）
！[6.3.2.1](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6.3.2.1.png)
- 空白键 （space）：代表向下翻一页； 
- Enter ：代表向下翻“一行”； 
- /字串 ：代表在这个显示的内容当中，向下搜寻“字串 这个关键字； 
- :f ：立刻显示出文件名以及目前显示的行数； 
- q ：代表立刻离开 more ，不再显示该文件内容。 
- b 或 [ctrl]-b ：代表往回翻页，不过这动作只对文件有用，对管线无用。

##### less（一页一页翻动）
！[6.3.2.2](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6.3.2.2.png)

- 空白键：向下翻动一页； 
- [pagedown]：向下翻动一页； 
- [pageup] ：向上翻动一页；
- /字串 :向下搜寻“字串”的功能；
- ?字串 :向上搜寻“字串”的功能；
- n :重复前一个搜寻 （与 / 或 ? 有关！）；
- N :反向的重复前一个搜寻 （与 / 或 ? 有关！）；
- g :前进到这个数据的第一行去；
- G :前进到这个数据的最后一行去 （注意大小写）；
- q :离开 less 这个程序；


#### 数据撷取
head/tail

##### head（取出前面几行）
！[6.3.3.1](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6.3.3.1.png)
##### tail（取出后面几行）
！[6.3.3.2](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6.3.3.2.png)

##### 例题
！[6.3.3.3](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6.3.3.3.png)

#### 非纯文本文件：od
！[6.3.4.1](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6.3.4.1.png)

#### 修改文件时间或创建新文件（touch）
- modification time （ mtime） ： 当该文件的“内容数据”变更时，就会更新这个时间！内容数据指的是文件的内容，而不是文件的属性或权限喔！

- status time （ ctime） ： 当该文件的“状态 （status）”改变时，就会更新这个时间，举例来说，像是权限与属性被更改了，都会更新这个时间啊。

- access time （ atime） ： 当“该文件的内容被取用”时，就会更新这个读取时间 （access）。举例来说，我们使用 cat 去读取 /etc/man_db.conf ， 就会更新该文件的 atime 了。

！[6.3.5.1](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6.3.5.1.png)

touch:
![6.3.5.2](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6.3.5.2.png)
![6.3.5.3](https://github.com/liuhongkang/Linux-Learning/blob/master/images/6.3.5.3.png)
即使我们复制一 个文件时，复制所有的属性，但也没有办法复制 ctime 这个属性的。 ctime 可以记录这个文件最近的状态 （status） 被改变的时间。

使用情况：
- 创建一个空的文件； 
- 将某个文件日期修订为目前 （mtime 与 atime）



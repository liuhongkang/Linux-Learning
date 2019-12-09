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

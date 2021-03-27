# 第二章实验
## **一、实验环境**
- windows10专业版
- Virtualbox
- Ubuntu 20.04 Server 64bit
## **二、实验目的**
- 利用asciinema进行录屏操作并上传
- 利用vimtutor掌握vim的基本操作
## **三、实验要求**
- 确保本地已经完成asciinema auth，并在asciinema成功关联了本地账号和在线账号
- 上传本人亲自动手完成的vimtutor操作全程录像
- 在自己的github仓库上新建markdown格式纯文本文件附上asciinema的分享URL
- **提醒**避免在终端操作录像过程中暴漏密码、个人隐私等任何机密数据
## **四、实验步骤**
**1. 在官网找到ubuntu系统的asciinema下载命令行，在cmd利用ssh连接虚拟机后，输入如下代码进行asciinema安装**
```
sudo apt-add-repository ppa:zanchey/asciinema
sudo apt-get update
sudo apt-get install asciinema
```
**2. 关联asciinema账号**
```
asciinema auth
```
**3. 进行录制**
```
asciinema rec
```
**4. 使用asciinema录制vimtutor操作全程**
- **lesson 1**
[![asciicast](https://asciinema.org/a/sb9tHxLvvJVmUFJBWp7ekJkPM.svg)](https://asciinema.org/a/sb9tHxLvvJVmUFJBWp7ekJkPM)
- **lesson 2**
[![asciicast](https://asciinema.org/a/LqWVu6in5PWKrBukKFDizyePG.svg)](https://asciinema.org/a/LqWVu6in5PWKrBukKFDizyePG)
- **lesson 3**
[![asciicast](https://asciinema.org/a/5CU4rDJI05OA2GUoq0nqq8UdQ.svg)](https://asciinema.org/a/5CU4rDJI05OA2GUoq0nqq8UdQ)
- **lesson 4**
[![asciicast](https://asciinema.org/a/zECGgNB6eGxdauwdPTHvIYAC4.svg)](https://asciinema.org/a/zECGgNB6eGxdauwdPTHvIYAC4)
- **lesson 5**
[![asciicast](https://asciinema.org/a/pY7zXagCslShW2mifPoDj1DZe.svg)](https://asciinema.org/a/pY7zXagCslShW2mifPoDj1DZe)
- **lesson 6**
[![asciicast](https://asciinema.org/a/KlXVbLL8y2R4e22D2mwPAtg6B.svg)](https://asciinema.org/a/KlXVbLL8y2R4e22D2mwPAtg6B)
- **lesson 7**
[![asciicast](https://asciinema.org/a/jZdFXTuDIsBBDZcgVRBu2zVPF.svg)](https://asciinema.org/a/jZdFXTuDIsBBDZcgVRBu2zVPF)
## **五、vimtutor完成后的自查清单**
- 你了解vim有哪几种工作模式？
    - Normal mode：浏览，修改文本
    - Insert mode：可以编辑输入
    - Select mode：用鼠标拖选区域的时候，进入了选择模式。在这个模式下，选择完了高亮区域后，敲任何按键就直接输入并替换选择的文本了
    - Visual mode：可选定一些字符、行、多列
    - Command-line mode：可以输入各种命令
    - Ex mode：多行的command-line模式
- Normal模式下，从当前行开始，一次向下移动光标10行的操作方法？如何快速移动到文件开始行和结束行？如何快速跳转到文件中的第N行？
    - 向下移动光标10行：``10j``
    - 移动到文件开始行：``gg``
    - 移动到文件结束行：``G``
    - 跳转到文件第N行：``N G``
- Normal模式下，如何删除单个字符、单个单词、从当前光标位置一直删除到行尾、单行、当前行开始向下数N行？
    - 删除单个字符：``x``
    - 删除单个单词：
        - ``dw``:光标定位单词首字母，删除当前单词
        - ``de``:光标定位单词首字母之前，删除后一个单词
        - ``db``:光i包定位单词尾之后，删除前一个单词
    - 从当前光标位置一直删除到行尾：``d$``
    - 删除单行：``dd``
    - 删除当前行开始向下数N行：``Ndd``
- 如何在vim中快速插入N个空行？如何在vim中快速输入80个-？
    - 在vim中快速插入N个空行：
        - 向下插入：``N o Esc``
        - 向上插入：``N O Esc``
    - 在vim中快速输入80个-：``80i- Esc`` 或者 ``80a- Esc``
- 如何撤销最近一次编辑操作？如何重做最近一次被撤销的操作？
    - 撤销最近一次编辑操作：``u``
    - 重做最近一次被撤销操作：``Ctrl+R``
- vim中如何实现剪切粘贴单个字符？单个单词？单行？如何实现相似的复制粘贴操作呢？
    - 剪切粘贴单个字符：``x p``
    - 剪切粘贴单个单词：``dw p``
    - 剪切粘贴单行：``d$ p``
    - 实现相似的复制粘贴操作：``v``进入可视模式，移动对文本进行选中，``y``复制，``p``粘贴
- 为了编辑一段文本你能想到哪几种操作方式（按键序列）？
    - ``a``在光标后插入内容，``A``在行尾插入内容
    - ``ce、cw、c$``删除单词/行之后进入insert模式修改内容
    - ``dd、dw、d$``删除单行/单词/从光标位置删除到行尾
    - ``i``进入插入模式
    - ``o``在光标上方新建一行并进入插入模式，``O``在光标下方新建一行并进入插入模式
    - ``p``粘贴内容
    - ``:q!/:wq!``退出但不保存所作更改/退出且保存所做更改
    - ``r``替换单个字母，``R``进入replace模式替换文字
    - ``u``撤销最近一次编辑操作，``U``恢复某行原始状态，``Ctrl+R``重做最近一次被撤销操作
    - ``v``进入可视模式，在此模式下可以移动光标选中文本内容
    - ``:w``保存更改
    - ``x``删除字母
    - ``y``复制内容
- 查看当前正在编辑的文件名的方法？查看当前光标所在行的行号的方法？
    - ``Ctrl+G``
- 在文件中进行关键词搜索你会哪些方法？如何设置忽略大小写的情况下进行匹配搜索？如何将匹配的搜索结果进行高亮显示？如何对匹配到的关键词进行批量替换？
    - 关键词搜索：
        - ``/word`` 用``n``向后搜索，``N``向前搜索
        - ``?word`` 用``n``向前搜索，``N``向后搜索
    - 设置忽略大小写情况下进行匹配搜索：``:set ic``
    - 将匹配的搜索结果进行高亮显示：``:set hls``
    - 对匹配到的关键词进行批量替换：
        - ``:s/old/new``在一行中以new替换头一个old
        - ``:s/old/new/g``在一行中以new替换所有的old
        - ``#,#s/old/new/g``在#到#两行间，以new替换所有的old
        - ``%s/old/new/g``替换文件中的所有事件
        - ``%s/old/new/gc``在进行全文替换时，确认是否需要进行全文替换
- 在文件中最近编辑过的位置来回快速跳转的方法？
    - ``Ctrl+O``向前跳转
    - ``Ctrl+I``向后跳转
- 如何把光标定位到各种括号的匹配项？例如：找到(, [, or {对应匹配的),], or }
    - 光标位于(,[,{时键入``%``，再按``%``可以返回
- 在不退出vim的情况下执行一个外部程序的方法？
    - ``:!<command>``
- 如何使用vim的内置帮助系统来查询一个内置默认快捷键的使用方法？如何在两个不同的分屏窗口中移动光标？
    - 查询一个内置默认快捷键的使用方法：``:help[快捷键名]``
    - 在两个不同的分屏窗口中移动光标的方法：``Ctrl+W``
## **六、参考资料**
- [vimtutor双语教程](https://blog.csdn.net/zhaoyu106/article/details/72896216)
- [vim六种工作模式](https://tieba.baidu.com/p/6071569672?red_tag=3175470467)
- [markdown教程](https://www.markdownguide.org/extended-syntax/#syntax-highlighting)
# 第四章实验:shell脚本编程基础
## **一、实验环境**
- windows10专业版
- Virtualbox
- Ubuntu 20.04 Server 64bit
## **二、实验目的**
- 掌握shell脚本编程语言
## **三、实验报告要求**
- 所有源代码文件必须单独提交并提供详细的```-help```脚本内置帮助信息
- 任务三的所有统计数据结果要求写入独立实验报告
## **四、实验任务**
### **任务一：用bash编写一个图片批处理脚本，实现以下功能：**
- [x] 支持命令行参数方式使用不同功能
- [x] 支持对指定目录下所有支持格式的图片文件进行批处理
- [x] 支持以下常见图片批处理功能的单独使用或组合使用
  - [x] 支持对jpeg格式图片进行图片质量压缩
  - [x] 支持对jpeg/png/svg格式图片在保持原始宽高比的前提下压缩分辨率
  - [x] 支持对图片批量添加自定义文本水印
  - [x] 支持批量重命名（统一添加文件名前缀或后缀，不影响原始文件扩展名）
  - [x] 支持将png/svg图片统一转换为jpg格式图片
### **任务二：用bash编写一个文本批处理脚本，对以下附件分别进行批量处理完成相应的数据统计任务：**
- [x] 统计不同年龄区间范围（20岁以下、[20-30]、30岁以上）的球员数量、百分比
- [x] 统计不同场上位置的球员数量、百分比
- [x] 名字最长的球员是谁？名字最短的球员是谁？
- [x] 年龄最大的球员是谁？年龄最小的球员是谁？
### **任务三：用bash编写一个文本批处理脚本，对以下附件分别进行批量处理完成相应的数据统计任务：**
- [x] 统计访问来源主机TOP 100和分别对应出现的总次数
- [x] 统计访问来源主机TOP 100 IP和分别对应出现的总次数
- [x] 统计最频繁被访问的URL TOP 100
- [x] 统计不同响应状态码的出现次数和对应百分比
- [x] 分别统计不同4XX状态码对应的TOP 10 URL和对应出现的总次数
- [x] 给定URL输出TOP 100访问来源主机
## **五、实验步骤**
### **任务一**
- 安装```imagemagick```
```bash
sudo apt-get update 
sudo apt-get install -y imagemagick
```
- 编写脚本并附上脚本帮助信息
```bash
    -c Q               对jpeg格式图片进行图片质量因子为Q的压缩
    -r R               对jpeg/png/svg格式图片在保持原始宽高比的前提下压缩分辨率为R
    -w content size position   对图片批量添加自定义文本水印,content写入水印内容，size写入水印大小，position写入水印位置，如North,West..
    -p text            统一添加文件名前缀，不影响原始文件扩展名
    -s text            统一添加文件名后缀，不影响原始文件扩展名
    -t                 将png/svg图片统一转换为jpg格式图片
    -h                 帮助文档
```
- 测试脚本
### **任务二**
- 将文件下载到虚拟机中
```bash
wget "https://c4pr1c3.gitee.io/linuxsysadmin/exp/chap0x04/worldcupplayerinfo.tsv"
```
- 编写脚本并附上脚本帮助信息
```bash
    -a                 统计不同年龄区间范围（20岁以下、[20-30]、30岁以上）的球员数量、百分比
    -p                 统计不同场上位置的球员数量、百分比
    -mn                 名字最长的球员是谁？名字最短的球员是谁？
    -ma                 年龄最大的球员是谁？年龄最小的球员是谁？
    -h                 帮助文档
```
- 测试脚本
### **任务三**
- 下载p7zip-full到虚拟机中用于解压软件
```bash
sudo apt-get install p7zip-full
```
- 将文件下载到虚拟机中并解压
```bash
wget "https://c4pr1c3.gitee.io/linuxsysadmin/exp/chap0x04/web_log.tsv.7z"
7z x web_log.tsv.7z
```
- 编写脚本并附上脚本帮助信息
```bash
    -a      统计访问来源主机TOP 100和分别对应出现的总次数
    -b      统计访问来源主机TOP 100 IP和分别对应出现的总次数
    -u      统计最频繁被访问的URL TOP 100
    -p      统计不同响应状态码的出现次数和对应百分比
    -f      分别统计不同4XX状态码对应的TOP 10 URL和对应出现的总次数
    -s URL  给定URL输出TOP 100访问来源主机
    -h      帮助文档
```
- 测试脚本
## **六、参考资料**
- [awk命令详解](https://blog.csdn.net/weixin_41477980/article/details/89511954)
- [sort-k命令详解](https://www.cnblogs.com/yangyongzhi/archive/2012/11/05/2755421.html)
- [match正则表达式匹配方法](https://www.cnblogs.com/ldq678/p/9375305.html)
- [awk入门教程](http://www.ruanyifeng.com/blog/2018/11/awk.html)
- [shell遍历目录及其子目录](http://blog.sina.com.cn/s/blog_45722cc00100ysoq.html)
- [convert命令](https://blog.csdn.net/newborn2012/article/details/24964577)
- [ImageMagick](http://www.imagemagick.com.cn/)
- [2021-linux-public-EddieXu1125](https://github.com/CUCCS/2021-linux-public-EddieXu1125/tree/chap0x04/chap0x04)
- [linux-2020-LyuLumos](https://github.com/CUCCS/linux-2020-LyuLumos/tree/ch0x04)
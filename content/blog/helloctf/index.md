---
title: "NSS CTF 招新标准"
slug: "/helloctf"
---

亲爱的小柚子们，祝贺你们圆满的完成了军训~
那么在接下来的时间里，想要加入实验室的就可以开始准备了哦。
我们会把每个方向涉及到的题型以及所需学习的内容都大致介绍一遍，划划重点，请务必查看你想学习的反向
不过在此之前，需要强调：
**以下内容是考核要点，但招新赛可能会略微超出以下范围，并且也不一定全部涉及，只是让你们有一个大致的了解**
点击蓝色的链接可以转调到我们寻找的参考资料，为了深入学习可以自行百度搜索更有价值的知识哦~
首先是 Web 方向

## Web招新标准

* **了解http协议**  
  常用知识点：http协议中的[请求方式](https://blog.csdn.net/qq_45086218/article/details/114113971)(post,get重点看，其他方式了解以下就行)，常用[http请求头](https://zhuanlan.zhihu.com/p/45173862)的意义，通过burp或者其他工具进行[http请求头伪造](https://blog.csdn.net/weixin_44953600/article/details/107515973)

* **了解php的基本语法**      
  常用知识点：php代码审计，php一些函数绕过，md5碰撞，以上知识点[这篇博客](https://blog.csdn.net/qq_45086218/article/details/114113971)都有讲到

* **常用工具的使用**    
  常用的工具这边直接贴个[下载链接](https://www.sqlsec.com/tools.html)了，至少把菜刀(或者蚁剑)和御剑后台扫描的使用给熟悉一下

* **基本[sql语法](https://www.liaoxuefeng.com/wiki/1177760294764384/1179610846971200)(至少把查询语法给看完哈，球球了这对sql注入非常重要)**  
  常用知识点：了解sql注入的[一般步骤](https://blog.csdn.net/ewyherayh/article/details/106524972#t14)和sql注入的几种[基本注入方式](https://blog.csdn.net/qq_43635212/article/details/108289524)，入门至少掌握联合注入

* **文件上传**  
  常用知识点：文件上传大多数都是绕过过滤上传一个马到服务器，并通过这个马拿到服务器的命令执行权，考点主要包括绕过前端的过滤和后端过滤，前端过滤就是burp抓包改包，后端的过滤主要是绕过白名单和黑名单，老样子贴个[链接](https://blog.csdn.net/qq_43390703/article/details/104858705): D，这篇博客大部分文件上传的考点都涉及到了，入门只需掌握前端js的绕过和后端的后缀名绕过，burp抓包修改content-type和伪造文件头就ok了

* **反序列化**  
  常用知识点：反序列化招新应该主要就是考察[php反序列化](https://blog.csdn.net/solitudi/article/details/113588692)，入门应该知道php反序列化的原理和反序列化pop链的构造

* **文件包含**  
  常用知识点：[php文件包含](https://www.jianshu.com/p/41807d87da9b)，php的一些[伪协议](https://segmentfault.com/a/1190000018991087)，入门至少掌握php伪协议中的php://filter和php://input

如有问题可以联系 QQ：1343944630 的师傅哦~

再来是 Crypto 方向

# Crypto招新标准

## 编码

熟悉ASCII码、十六进制、base64/32/16编码、unicode编码、url编码的格式，了解每一种编码的基本原理以及能够运用在线或离线工具进行编/解码。

ASCII码：一套计算机最通用的信息交换标准，将128个字符以阿拉伯数字编码。e.g. A=65 a=97

自己百度。

十六进制转字符：将十六进制转换为十进制后，通过十进制对应的ASCII码转换成字符。e.g. 0x61=97=a

https://blog.csdn.net/qq_33242956/article/details/93199564

base64编码：顾名思义，64就是64个可打印字符，A~Z、a~z、0~9、+、/，这64个可打印字符。2^6=64
**原则：**3*8 转换成4*6 这里的8是指电脑的二进制位8bit 即一个字符在电脑里存储情况，3指的是三个字符（任意），4指的是64个中4个可打印字符，6只得是6个二进制位。要想得到可打印字符，必须将6位补位00，形成8个二进制位，再换算十进制数，再用这个十进制数找到相应的可打印字符。 e.g. base64("hello world")="aGVsbG8gd29ybGQ="

https://blog.csdn.net/xuebing1995/article/details/78795577

unicode编码：自己百度。

url编码:对http中请求参数进行编码。

https://www.cnblogs.com/jerrysion/p/5522673.html

## 密码

古典密码：

- **凯撒密码**

  凯撒密码（Caesar）加密时会将明文中的每个字母都按照其在字母表中的顺序向后（或向前）移动固定数目（循环移动）作为密文。

- **仿射密码**

  仿射密码的加密函数是 E(x)=(ax+b)(modm)，其中

  - x表示明文按照某种编码得到的数字
  - a和 m互质
  - m是编码系统中字母的数目。

  解密函数是 D(x)=a−1(x−b)(modm)，其中 a−1 是 a 在 Zm 群的乘法逆元。

- **playfair**

  Playfair 密码（Playfair cipher or Playfair square）是一种替换密码，基本原理是找一个密钥排列成5*5的矩阵，类似：

  ![image-20210924130115442](C:\Users\bestkasscn\AppData\Roaming\Typora\typora-user-images\image-20210924130115442.png)

  剩下的空间由未加入的英文字母依 a-z 的顺序加入。注意，将 q 去除，或将 i 和 j 视作同一字。将要加密的明文分成两个一组。若组内的字母相同，将 X（或 Q）加到该组的第一个字母后，重新分组。若剩下一个字，也加入 X 。在每组中，找出两个字母在矩阵中的地方。若两个字母不同行也不同列，在矩阵中找出另外两个字母（第一个字母对应行优先），使这四个字母成为一个长方形的四个角。若两个字母同行，取这两个字母右方的字母（若字母在最右方则取最左方的字母）。若两个字母同列，取这两个字母下方的字母（若字母在最下方则取最上方的字母）。新找到的两个字母就是原本的两个字母加密的结果。

- **维吉尼亚密码**

  维吉尼亚密码（Vigenere）是使用一系列凯撒密码组成密码字母表的加密算法，属于多表密码的一种简单形式。

- **词频分析**

  在线解密：http://quipqiup.com/

- **摩斯电码**

  e.g. Morsecode：-- --- ·-· ··· · / -·-· --- -·· ·

  在线解密：https://tool.lu/morse/

现代密码：

- **RSA**

  RSA 加密算法是一种非对称加密算法，算法的可靠性由极大整数因数分解的难度决定。

  ![image-20210924130716765](C:\Users\bestkasscn\AppData\Roaming\Typora\typora-user-images\image-20210924130716765.png)

  https://ctf-wiki.org/crypto/asymmetric/rsa/rsa_theory/

- **MD5**

  MD5 的输入输出如下

  - 输入：任意长的消息，512 比特长的分组。
  - 输出：128 比特(32位)的消息摘要。

  不要求掌握原理，只要能看懂格式并运用工具解密即可。

  e.g. md5("NSS")="248cdc66c441a6612309f6e2ce80a63c"

以上要求熟悉并能独立进行编/解码，其中凯撒密码要求重点掌握。

参考：https://blog.csdn.net/qq_40837276/article/details/83080460?utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.no_search_link&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.no_search_link

有问题可以考虑联系 QQ：576732161 以及 QQ：1123603165 的师傅哦~

再来是略微困难的 Pwn 方向

# Pwn 招新标准 

* **要求可以掌握基本的linux文件操作命令**   
  你不会linux下的一些命令你学个球   
  参考：https://blog.csdn.net/qq_29837161/article/details/85473423

* **ret2libc**  
  即控制程序执行流，去调用libc动态链接库中的函数来getshell,难点在于泄露libc基地址和偏移计算     
  参考：https://blog.csdn.net/m0_46363249/article/details/115264179

* **ret2text**  
  即控制程序执行流，去执行程序中给出的后门代码    
  参考：https://blog.csdn.net/m0_46363249/article/details/115066971

* **格式化字符串任意地址读写**
  https://blog.csdn.net/qq_43394612/article/details/84900668

* **uaf**   
  堆题，有能力可以了解，新生若无一定基础不建议去看
  参考：https://blog.csdn.net/qq_31481187/article/details/73612451    


新生赛做出任何 1-3 道 Pwn,有意向者可以联系 QQ：2955063401 入队。

倒数第二个方向 Reverse

# Reverse 招新标准

## 编程能力

能编写最基础的C程序

pta上的作业能轻松完成

学习基础的python脚本

## 计算机体系

能理解硬件，操作系统是如何运行程序的 

能从底层理解程序的运行

## 逆向理解

 能理解基础的算法及其逆向思维

- [异或](如何理解「异或（XOR）」运算在计算机科学中的重要性？ - 阿里聚安全的回答 - 知乎 https://www.zhihu.com/question/20484426/answer/180582779)
- [base64](https://blog.csdn.net/qq_20545367/article/details/79538530)

## 逆向程序

能使用逆向相关工具

- IDA
- OD

能理解程序是如何运行在系统上的

如果你不知道如何学习这些 请直接联系 QQ：3063825079

最后是 Misc 方向
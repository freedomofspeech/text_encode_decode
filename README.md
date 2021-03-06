# text_encode_decode

**如需使用，不需要编程知识，但需要一台安装了python3和jupyter notebook的电脑**
* python3安装方法见 https://www.python.org/about/gettingstarted/ 以及 https://www.python.org/downloads/
* jupyter notebook安装方法见(不是第一项JupyterLab!!是第二项classic Jupyter Notebook!!) https://jupyter.org/install

## Encoder1 - Decoder1

Encoder1：

   字符串 --> Unicode  --> 进制转换 --> 数字字母字符串  
   
   目标进制必须在[2,36]范围内，推荐16以上进制，34进制输出长度最短且重复最少   

Decoder1:

   数字字母字符串 -->  字符串
   
   进制数必须和编码时相同

## Encoder2 - Decoder2

Encoder2：

   数字字母字符串 --> 摩斯码

Decoder2:

   摩斯码 --> 数字字母字符串

## 中文-摩斯码转换

   传统方式是参考《标准电码本》，先将每个中文字符转换成4位数字，再转换成数字的摩斯码。  
   
   本代码与传统方式不同，直接使用Unicode，再在此基础上进行进制转换等操作，因此转换结果与传统方式不同，需要配合本代码中的解码器使用。  

   编码方法
   
   ```python
   test_text = '自由使用internet'
   base = 34

   encode1 = encoder1(test_text,base)
   #print(encode1)
   encode2 = encoder2(encode1)
   print(encode2)
   ```
   
   解码方法
   
   ```python
   morse = '----- ... --.- -.... ----- .--. .-- -.. ----- .... -.- .--- ----- .--. .-- ....- ----- ----- ...-- ...-- ----- ----- ...-- ---.. ----- ----- ...-- . ----- ----- ..--- -..- ----- ----- ...-- -.-. ----- ----- ...-- ---.. ----- ----- ..--- -..- ----- ----- ...-- .'
   base = 34
   decoder1(decoder2(morse),base)
   ```
   
   注意：编码和解码的进制(base)必须相同。

## Future Work
* 丰富编码器种类
* 发布app

**本是上班摸鱼的成果，水平有限，希望能抛砖引玉，有需要的尽管拿去用**


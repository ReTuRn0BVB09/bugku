# RE_Crino

这是一道逆向题，题目给的东西却是一个图片，拖进binwalk一波分析  

![](https://github.com/ReTuRn0BVB09/bugku/blob/master/RE_Crino/images/1.png)

发现除了原本的jpg以外还有一个zip文件，于是用010editor将后面的zip文件单独提取出来  

![](https://github.com/ReTuRn0BVB09/bugku/blob/master/RE_Crino/images/2.png)

解压之后得到一个exe文件，直接运行是这样的界面  

![](https://github.com/ReTuRn0BVB09/bugku/blob/master/RE_Crino/images/3.png)  

用ida打开该文件，进行静态分析  

![](https://github.com/ReTuRn0BVB09/bugku/blob/master/RE_Crino/images/7.png)

看到这里有一个进行加密操作的for循环，于是设置断点进行动态调试  

![](https://github.com/ReTuRn0BVB09/bugku/blob/master/RE_Crino/images/6.png)

找到ebp所指向的0x0019FED4，进行单步进入，并将每次所存储的字符记录下来得到uncry1}rC03{wvg0sae1ltof  

对字符串逆向之后得到fotl1eas0gvw{30Cr}1yrcnu  

![](https://github.com/ReTuRn0BVB09/bugku/blob/master/RE_Crino/images/4.png)

这时根据之前exe文件运行的界面提示：9层反向栅栏，进行解密  

fot  
l1e  
as0  
gvw  
{30  
Cr}  
1y  
rc  
nu  

![](https://github.com/ReTuRn0BVB09/bugku/blob/master/RE_Crino/images/5.png)

得到flag:flag{C1rno1sv3rycute0w0}

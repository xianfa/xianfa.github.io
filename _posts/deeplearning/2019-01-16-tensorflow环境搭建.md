﻿---
categories: [深度学习]
tags: [virtual box, ubuntu, python3, pip3, virtualenv, tensorflow]
---
环境是前几天整的，还是需要记录下，方便查阅翻看，以前虚拟机都是用的vmware，这次使用使用virtualbox作为虚拟机,操作系统使用ubuntu，如无特别说明，以后使用软件均以开源优先，万一需要研究源码，还可以直接获取。
# 总体过程
先下载了ubuntu18.10版本的server和desktop，然后创建了两个4Gmem,50GHD的虚拟机，安装后server可以运行，desktop不行，直接删除了desktop，只使用server。开始装两个想的是可以学习使用机群。还是先学习单机，然后查资料，找到了tensorflow中文社区，里面写的需要用python2，然后就查python2的安装，里面提到需要删除python3，果断卸载python3，结果发现无法上网，郁闷。
既然这样了，想着反正要用python2，不如装个低版本的ubuntu，在163镜像网站，下载了16.04.5的server，直接在原来的虚拟机上安装，结果发现无法启动，干脆又重新建了个虚拟机安装。启动后发现，里面自带的居然还是python3，怨自己没有好好找找带python2的版本，没法子。
再继续查找资料，无意中看到了tensorflow的官网，先前没有用官网是因为google的网不好访问，另外不太喜欢e文，主要还是懒。这次看到后就进去看了看，居然发现里面的安装是基于python3的，前面查python2的算是白忙活了。
继续创建虚拟机，重新安装18.10的server，按照里面的安装指导安装pip3和virtualenv，然后source进入虚拟环境安装tensorflow，执行过安装验证后就OK了。
# 经验教训
来来回回安装好几次系统，浪费了不少时间，不能偷懒，学什么东西，一定要从知识的源头获取，一定要学最新的。python3出来了，tensorflow的开发者不可能一直用python2，这是基本常识。
另外在处理的过程中有两点需要注意  
1.有些命令需要加sudo，不加的话执行不成功，一旦没注意到，后面又得花时间排查。  
2.apt-get不能正常运行，需要加nameserver，8.8.8.8和8.8.4.4，现在是直接su 到root，然后vi /etc/resolv.conf修改保存。  
2019.1.21日追加，由于后面要使用绘图方面的功能，最好装desktop的环境，我猜想用图形界面绘图方面交互可能会更好，现在都是保存为图片查看.
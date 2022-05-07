# 2022-03-28-github pages+sphinx搭建线上博客
---
## 1.需求分析
---
搭建一个线上网页，分享非涉密内容，输出个人价值，帮助同路人。
- 线上网站面向中英文读者
- 线上网页应该包含至少四到五个栏目，包含中英文界面
- 具有搜索功能
- 高度自定义

## 2.最终效果
---
https://novakhogithubio.rtfd.io

## 3.思路及我踩过的坑
---
- 尝试过jekyll + github pages方案，但是模板不满足四五个栏目，自行修改难度大
- 尝试过直接clone别人的项目，然后修改，报错多，作者本人给不出具体的原因
- 于是，就有了这个sphinx + github pages + Read the docs方案，优点是高度自定义，本地可预览


## 4.配置过程
---
### 4.1 换源 装python
---
- Linux/Unix系统
需要换源，对此不清楚的小伙伴参考*2020-03-02-yum源介绍与配置* 
再使用wget下载并编译，安装gcc
```bash
wget https://www.python.org/ftp/python/3.8.2/Python-3.8.2.tar.xz
yum install tar -y
xz -d Python-3.8.2.tar.xz
tar xf Python-3.8.2.tar 
./configure --prefix=/usr/local/python3.8.2
yum install gcc -y
make && make install
```

- Windows系统
则直接到python官网下载安装(检查环境变量是否生效)即可
备注：本人由于做过很多小软件，需要不同的虚拟环境，则使用了anaconda创建虚拟环境，再进行安装相关组件。



### 4.2 配置github仓库
---


### 4.3 配置Read the docs
---




## 5.注意事项
---
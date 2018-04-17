---
layout: post
title:  在Jekyll网页中使用MathJax插入数学公式
subtitle: mathjax配置教程
date:   2018-04-17 20:00:00 +8
tags:
    - jekyll 
    - github
    - math
---

- 本文参考了[利用MathJax在Jekyll网页中插入数学公式](https://luocongsky.github.io/2017/05/20/利用MathJax在Jekyll网页中插入数学公式/) 这篇文章

# 配置并链接MathJax库
新建一个`head_mathjaxsupport.html`文件,并在`<head>`标签中添加如下代码:  

```
<!-- MathJax Support -->
   <script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_HTMLorMML"></script>
   <script type="text/x-mathjax-config">
     MathJax.Hub.Config({
       Tex: {
         equationNumbers: {
           autoNumber: "AMS"
         }
       },
       tex2jax: {
         inlineMath: [ ['$','$'], ['\\(','\\)'] ],
         displayMath: [ ['$$','$$'], ['\[','\]'] ],
         processEscapes: true,
       },
       "HTML-CSS": {
         preferredFont: "STIX",
         scale: 100,
         styles: {
           ".MathJax_Display": { "text-align": "center", margin: "0em 0em" },
           ".mi": { "color": "#4d4d4d" },
           ".mo": { "color": "#4d4d4d" }
         }
       }
     });
   </script>
<!-- End MathJax Support -->

```

接下来需要查看`_layouts`文件夹下的基本布局文件(通常是`default.html`),决定是否引入mathjax支持,修改后的`head.html`文件如下:  
[head.html](https://github.com/bitowang/bitowang.github.io/blob/master/_includes/head.html)

# 行内 行间插入数学公式

- 在行内插入数学公式这些 $x$, $y$, $x_1$, $y_1$ 公式了

- 带有特殊符号的行内公式:
    1. $$\\|\psi  \rangle$$, 
    2. $x'$, 
    3. $$ x^* $$

- 段间公式:  
$$
    \begin{aligned}
    \dot{x} & = \sigma(y-x) \\
    \dot{y} & = \rho x - y - xz \\
    \dot{z} & = -\beta z + xy
    \end{aligned}
    \label{aabb}
$$

# 参考链接
* [MathJax官网](https://www.mathjax.org/)
* [利用MathJax在Jekyll网页中插入Tex/LaTex数学公式](http://baige5117.github.io/blog/mathjax_in_jekyll.html)  
* [How to use MathJax in Jekyll generated Github pages](http://haixing-hu.github.io/programming/2013/09/20/how-to-use-mathjax-in-jekyll-generated-github-pages/)



---
title: '[vim] 笔记整理'
date: 2020-03-22 03:50:28
tags: vim
---

部分vim杂七杂八的笔记

```vim
# 匹配长度大于70的行
/\%>70v.\+

# 查找origin_xxx等, 但忽略origin_aaa和origin_bbb
/\vorigin_(((aaa|bbb)@!).*)

# 关闭当前buffer以外的buffer
:bufdo bd
```

部分正则和perl风格不同: https://www.jianshu.com/p/3abd6fbc3322
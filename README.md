# input-type类型：
* button(单机按钮)
* checkbox(复选框)
* file(文件上传)
* hidden(隐藏的输入字段)
* image(图像形式的提交按钮)
* password(密码字段)
* radio(单选按钮)
* reset(重置按钮)
* submit(提交按钮)
* text(文本)
## html5中type类型：
### email
(email 类型用于应该包含 e-mail 地址的输入域。在提交表单时，会自动验证 email 域的值。) 

### url
(url 类型用于应该包含 URL 地址的输入域。在提交表单时，会自动验证 url 域的值。)

### number
(number 类型用于应该包含数值的输入域。您还能够设定对所接受的数字的限定：```Points: <input type="number" name="points" min="1" max="10" step="2" value="6"/> (value为默认值 step为步长)```)

### range
(range 类型用于应该包含一定范围内数字值的输入域。range 类型显示为滑动条。您还能够设定对所接受的数字的限定：```<input type="range" name="points" min="1" max="10" />```)

### date pickers:

* date 选取日、月、年
* month 选取月、年
* week 选取周和年
* time 选取时间（小时和分钟）
* datetime 选取时间、日、月、年（UTC 时间）
* datetime-local 选取时间、日、月、年（本地时间）

### search
(search 类型用于搜索域，比如站点搜索或 Google 搜索。search 域显示为常规的文本域。)

***
#.dataset[] 获取自定义数据集
event.prenventDefault(); 取消事件的默认动作
***


# SVG
## Scalable Vector Graphics 可缩放矢量图形
### 优势：体积小，质量高，效果好，可控程度高
1. 以文件方式载入方式：
	1. ```**<iframe src="demo.svg" frameborder="0"></iframe>```
	2. ```<object data="demo.svg" type=""></object>```
	3. ```<embed src="demo.svg" type=""></embed>```
2. 直接把svg代码复制进html中


# html5 新选择器
1. 返回第一个满足选择器条件的元素，一个dom对象
```document.querySelector(selector);```
2. 返回所有满足该条件的元素，一个元素类型是dom类型的数组
```document.querySelectorAll(selector);```

**类比jQuery的```$('.item')```**是返回一个jQuary对象(dom元素的数组)
本质上jQuery方式和querySelector方式都是获取DOM数组，只不过jQuery会多一些其他成员
**dom数组的每一个成员注册事件不能像jQuery一样直接注册，需要遍历每个子元素分别注册**
###h5就是将我们经常需要的操作又包装了一层

# Element.classList
## 输出Element拥有的class的数组
1. ```Element.classList.add('classAttr');//添加类```
2. ```Element.classList.remove('classAttr');//移除类```
3. ```Element.classList.toggle('classAttr');//切换事件```
4. ```ELement.classList.contains('classAttr')//判断当前classlist中有没有classAttr这个属性;```





















<h1 align="center">css3--笔记</h1>

## 目录
1. [属性选择器](#user-content-属性选择器)
2. [伪类选择器](#user-content-伪类选择器)
3. [颜色](#user-content-颜色)

***

# 属性选择器
1. **E[attr=val]**  eg. inoput[type="text"]
2. **E[attr~=val]** 表示一个单独的属性值，这个属性值是以空格分隔的
3. **E[attr|=val]** 要么表示一个单独的属性值，要么这个属性值是以'-'隔的
4. **E[attr\*=val]** 表示的属性值里包含val字符并且在任意位置
5. **E[attr^=val]** 表示的属性值里包含val字符并且在开始位置
6. **E[attr$=val]** 表示的属性值里包含val字符并且在结束位置

<h3 align="right"><a href="#user-content-css3--笔记">返回目录</a></h3>

***

# 伪类选择器
+ **E:first-child** //相对于E元素的父级作参考，“所有”子元素的最后一个子元素,并且位置要对应
+ **E:last-child** //相对于E元素的父级作参考，“所有”子元素的第一个子元素,并且位置要对应
+ **E:first-of-type** //相对于E元素父级作参考，“特定类型元素E”的第一个子元素
+ **E:last-of-type** //相对于E元素父级作参考，“特定类型元素E”的最后一个子元素
+ **E:nth-of-type(n)** //选中第n个(n>=1,当n作为系数时n的取值可以为0)
+ **E:nth-last-child(n)** //以最后一个元素为起点
+ **E:only-child** //选择的是父元素中只有一个子元素，而且只有唯一的一个子元素。也就是说，匹配的元素的父元素中仅有一个子元素，而且是一个**唯一的子元素**
+ **E:only-of-type** //是表示一个元素他有很多个子元素，而其中只有一种类型的子元素是唯一的，使用“:only-of-type”选择器就可以选中这个元素中的唯一一个类型子元素
+ **E:empty** //匹配没有任何子元素（包括text节点）的元素E
+ **E:target** //URL后面跟锚点#，指向文档内某个具体的元素。这个被链接的元素就是目标元素(target element)，:target选择器用于选取当前活动的目标元素
+ **E:before/E:after** //在每个 <p> 元素的内容之前/之后插入新内容(content:""; //必须要加！！)
+ **E:selection** //能定义被选择时的background-color，color及text-shadow样式
+ **E:placeholder** //用于控制表单输入框占位符的外观，它允许开发者/设计师改变文字占位符的样式，默认的文字占位符为浅灰色

<h3 align="right"><a href="#user-content-css3--笔记">返回目录</a></h3>

***

# 颜色
+ **opacity:1** //透明度（子元素会继承父元素的透明度）
+ **background:transparent** //完全透明
+ rgba(0,0,0,0.3) //rgb加透明度
+ hsla(0~360,0~100%,0~100%,0~1);

<h3 align="right"><a href="#user-content-css3--笔记">返回目录</a></h3>

***

# 文字
+ **text-shadow:h-shadow v-shadow blur color** //基础的文本阴影效果
```
h-shadow	必需。水平阴影的位置。允许负值
v-shadow	必需。垂直阴影的位置。允许负值
blur	可选。模糊的距离
color	可选。阴影的颜色。参阅 CSS 颜色值
```
+ **text-overflow: ellipsis** //单行文本溢出,需要配合**overflow: hidden**;**white-space: nowrap**


<h3 align="right"><a href="#user-content-css3--笔记">返回目录</a></h3>

***

# 边框圆角
+ **border-radius** 可分别设置长、短半径，以“/”进行分隔，遵循“1，2，3，4”规则
+ **border-color** 4个值也可以分别设置
+ 表格运用圆角需要**border-collapse:separate**
+ 当圆角半径小于或等于边框宽度时，元素內解是直角


<h3 align="right"><a href="#user-content-css3--笔记">返回目录</a></h3>

***







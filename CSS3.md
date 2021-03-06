<h1 align="center">css3--笔记</h1>

## 目录
1. [属性选择器](#user-content-属性选择器)
2. [伪类选择器](#user-content-伪类选择器)
3. [颜色](#user-content-颜色)
4. [文字](#user-content-文字)
5. [边框圆角](#user-content-边框圆角)
6. [边框阴影](#user-content-边框阴影)
7. [背景](#user-content-背景)
8. [Flex布局](#user-content-flex布局)
9. [过度](#user-content-过度)
10. [动画](#user-content-动画)
11. [判断鼠标进入容器方向](#user-content-判断鼠标进入容器方向)

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
+ **E:nth-last-child(n)** //以最后一个元素为起点,规定属于其父元素的第二个子元素的每个 p 元素
```
关于n的取值范围：
1. 当n作为一个独立的值时，n取值为>=1,例如nth-child(n)
2. 当n做一个系数时，n取值为n>=0或者n<0，例如nth-child(2n+1)、nth-child(-n+5)此处需要理解2n+1或者-n+5作为一个整体不嫩小于1;
```
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
### 做重合圆环时，第二个圆环的位置需绝对定位，left top值需设置成圆环border-width的值的负数，以便完美重合
+ **border-radius** 可分别设置长（纵轴）、短（横轴1）半径，以“/”进行分隔，遵循“1，2，3，4”规则
+ **border-color** 4个值也可以分别设置
+ 表格运用圆角需要**border-collapse:separate**
+ 当圆角半径小于或等于边框宽度时，元素內解是直角


<h3 align="right"><a href="#user-content-css3--笔记">返回目录</a></h3>

***

# 边框阴影
+ **box-shadow:h-shadow v-shadow blur (扩展量) color**
```
//水平偏移量：正值向右，负值向左，垂直：正值向下，负值向上
//偏移量和扩展是可以数学运算的（扩展量是扩展4个方向上的）
h-shadow	必需。水平阴影的位置。允许负值
v-shadow	必需。垂直阴影的位置。允许负值
blur	可选。模糊的距离//从一个颜色值在一定距离内进行一个渐变至透明的过程
color	可选。阴影的颜色。参阅 CSS 颜色值
```
+ **box-shadow:inset h-shadow v-shadow blur (扩展量) color**
//内阴影

<h3 align="right"><a href="#user-content-css3--笔记">返回目录</a></h3>

***

# 背景
+ background-clip: content-box;//默认的背景填充区域，只填充内容
+ background-clip: padding-box;//从padding处开始填充背景
+ background-clip: border-box;//从border处开始填充背景
+ background-origin: content-box;//背景填充定位原点
+ background-size: 100% auto;//背景图片大小
+ background-repeat: no-repeat;//不平铺

<h3 align="right"><a href="#user-content-css3--笔记">返回目录</a></h3>

***

# Flex布局
1. ### Flex是Flexible Box的缩写，意为“弹性布局”，用来为盒装模型提供最大的灵活性
+ 任何一个容器都可以指定为Flex布局
```
.box{
  display: flex;
}
```
+ 行内元素也可以使用Flex布局
```
.box{
  display: inline-flex;
}
```
**注意：设为Flex布局以后，子元素的float、clear和vertical-align属性将失效**

2. 采用Flex布局的元素，称为Flex容器（flex container），简称“容器”。它的所有子元素自动成为容器成员，成为Flex项目（Flex item），简称“项目。<br>
<img src="/flex/1.png"><br>
+ 容器默认存在两根轴：**水平的主轴（main axis）**和**垂直的交叉轴（cross axis）**。主轴的开始位置（与边框的交叉点）叫做**main start**，结束位置叫做**main end**；交叉轴的开始位置叫做**cross start**，结束位置叫做**cross end**。
+ 项目默认沿主轴排列。单个项目占据的主轴空间叫做**main size**，占据的交叉轴空间叫做**cross size**

3. 容器属性
    + flex-direction
    + flex-wrap
    + flex-flow
    + justify-content
    + align-items
    + align-content

    1. ### flex-direction属性
    > flex-direction属性决定主轴的方向（即项目的排列方向）
    ```
    .box-direction{
      flex-direction: row | row-reverse | column | column-reverse
    }
    ```
    <img src="/flex/2.png"><br>

    其属性值为：

    + row（默认值）：主轴为水平方向，起点在左端。
    + row-reverse：主轴为水平方向，起点在右端。
    + column：主轴为垂直方向，起点在上沿。
    + column-reverse：主轴为垂直方向，起点在下沿。

    2. flex-wrap属性
    > 默认情况下，项目都排在一条线（又称“轴线”）上。flex-wrap属性定义，如果一条轴线排不下，如何换行。
    <img src="/flex/3.png"><br>
    ```
    .box{
      flex-wrap: nowrap: nowrap | wrap | wrap-reverse;
    }
    ```

        1. nowrap(默认):不换行
        <img src="/flex/4.png"><br>
        2. wrap: 换行，第一行在上方
        <img src="/flex/5.jpg"><br>
        3. wrap:-reverse:换行，第一行在下方
        <img src="/flex/6.jpg"><br>

    3. flex-flow
    > flex-flow属性是flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap。
    ```
    .box {
      flex-flow: <flex-direction> || <flex-wrap>;
    }
    ```

    4. justify-content属性
    > justify-content属性定义了项目在主轴上的对齐方式。
    ```
    .box {
      justify-content: flex-start | flex-end | center | space-between | space-around;
    }
    ```
    <img src="flex/7.png"><br>

    它可能取5个值，具体对齐方式与轴的方向有关。下面假设主轴为从左到右:

    + flex-start（默认值）：左对齐
    + flex-end：右对齐
    + center： 居中
    + space-between：两端对齐，项目之间的间隔都相等。
    + space-around：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。

    5. align-items属性
    > align-items属性定义项目在交叉轴上如何对齐。
    ```
    .box {
      align-items: flex-start | flex-end | center | baseline | stretch;
    }
    ```
    <img src="flex/8.png"><br>

    它可能取5个值。具体的对齐方式与交叉轴的方向有关，下面假设交叉轴从上到下:

    + flex-start：交叉轴的起点对齐。
    + flex-end：交叉轴的终点对齐。
    + center：交叉轴的中点对齐。
    + baseline: 项目的第一行文字的基线对齐。
    + stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度。

    6. align-content属性
    > align-content属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。
    ```
    .box {
      align-content: flex-start | flex-end | center | space-between | space-around | stretch;
    }
    ```
    <img src="flex/9.png"><br>

    该属性可能取6个值:

    + flex-start：与交叉轴的起点对齐。
    + flex-end：与交叉轴的终点对齐。
    + center：与交叉轴的中点对齐。
    + space-between：与交叉轴两端对齐，轴线之间的间隔平均分布。
    + space-around：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。
    + stretch（默认值）：轴线占满整个交叉轴。

4. 项目的属性
> 以下6个属性设置在项目上。

+ order
+ flex-grow
+ flex-shrink
+ flex-basis
+ flex
+ align-self

    1. order属性
    > order属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。
    ```
    .item{
      order: <integer>;
    }
    ```
    <img src="flex/10.png"><br>

    2. flex-grow属性
    > flex-grow属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。
    ```
    .item{
      flex-grow: <number>; /* default 0 */
    }
    ```
    <img src="flex/11.png"><br>
    如果所有项目的flex-grow属性都为1，则它们将等分剩余空间（如果有的话）。如果一个项目的flex-grow属性为2，其他项目都为1，则前者占据的剩余空间将比其     他项多一倍。

    3. flex-shrink属性
    > flex-shrink属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。
    ```
    .item{
      flex-shrink: <number>;/* default 1 */
    }
    ```
    <img src="flex/12.jpg"><br>
    如果所有项目的flex-shrink属性都为1，当空间不足时，都将等比例缩小。如果一个项目的flex-shrink属性为0，其他项目都为1，则空间不足时，前者不缩小。
    负值对该属性无效。

    4. flex-basis属性
    > flex-basis属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目       的本来大小。
    ```
    .item {
      flex-basis: <length> | auto; /* default auto */
    }
    ```
    它可以设为跟width或height属性一样的值（比如350px），则项目将占据固定空间。

    5. flex属性
    > flex属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选。
    ```
    .item {
      flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
    }
    ```
    + 该属性有两个快捷值：auto (1 1 auto) 和 none (0 0 auto)。
    + 建议优先使用这个属性，而不是单独写三个分离的属性，因为浏览器会推算相关值。

    6. align-self属性
    > align-self属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元       素，则等同于stretch。
    ```
    .item {
      align-self: auto | flex-start | flex-end | center | baseline | stretch;
    }
    ```
    <img src="flex/13.png"><br>
    该属性可能取6个值，除了auto，其他都与align-items属性完全一致。


<h3 align="right"><a href="#user-content-css3--笔记">返回目录</a></h3>

***

# 过渡
### transition: property duration timing-function delay
+ transition-property //规定设置过度效果的CSS属性的名称
+ transition-duration //规定完成过度效果需要多少秒或毫秒
+ transition-timing-function //规定速度效果的速度曲线
    1. linear 规定以相同速度开始至结束的过渡效果（等于 cubic-bezier(0,0,1,1)）
    2. ease 规定慢速开始，然后变快，然后慢速结束的过渡效果（cubic-bezier(0.25,0.1,0.25,1)）
    3. ease-in	规定以慢速开始的过渡效果（等于 cubic-bezier(0.42,0,1,1))
    4. ease-out 规定以慢速结束的过渡效果（等于 cubic-bezier(0,0,0.58,1)）
    5. ease-in-out 规定以慢速开始和结束的过渡效果（等于 cubic-bezier(0.42,0,0.58,1)）
    6. cubic-bezier(n,n,n,n) 在 cubic-bezier 函数中定义自己的值。可能的值是 0 至 1 之间的数值
+ transition-delay //定义过度效果何时开始

<h3 align="right"><a href="#user-content-css3--笔记">返回目录</a></h3>

***

# 旋转
+ transform: rotate; // 2D旋转
+ transform: rotateX/rotatrY/rotateZ; // 3D旋转
+ **可以配合 perspective: 100px; 使用**
    1. perspective-origin: 50% 50%; //默认
    2. 当为元素定义perspective属性时，**其子元素会获得透视效果**，而不是元素本身。
    3. 属性只影响3D转换元素
    4. 取值为none或不设置，就没有真3D空间
    5. 取值越小，3D效果就越明显
    6. 值无穷大，或值为0时与取值为none效果一样
+ **transform-style:** flat(平面的)/preserve-3d(表示所有子元素在3D空间中呈现)/preserve(保持原状)
+ transform: scale(1,1); // 括号里填倍数 2D缩放
+ transform: scaleX/Y/Z(1) //3D缩放

<h3 align="right"><a href="#user-content-css3--笔记">返回目录</a></h3>

***

# 动画
+ animation-name: // 动画名称
+ animation-duration: // 动画持续时间
+ animation-play-state: // 动画状态
+ animation-iteration-count: // 动画播放次数
+ animation-fill-mode: // 动画终止时的状态
+ animation-direction: //动画执行的顺序
+ animation-timing-function: // 动画过度曲线
+ animation-delay: // 动画延时

```
/*动画序列*/
@keyframes change//名字{
  0%{

  }
  50%{

  }
  100%{

  }
}
```

<h3 align="right"><a href="#user-content-css3--笔记">返回目录</a></h3>

***

# 判断鼠标进入容器方向

```
$("div").on("mouseenter mouseleave",function(e) {
     var w = $(this).width(); // 得到盒子宽度
     var h = $(this).height();// 得到盒子高度
     var x = (e.pageX - this.offsetLeft - (w / 2)) * (w > h ? (h / w) : 1);
     // 获取x值
     var y = (e.pageY - this.offsetTop - (h / 2)) * (h > w ? (w / h) : 1);
     // 获取y值
     var direction = Math.round((((Math.atan2(y, x) * (180 / Math.PI)) + 180) / 90) + 3) % 4; //direction的值为“0,1,2,3”分别对应着“上，右，下，左”
     // 将点的坐标对应的弧度值换算成角度度数值
     var dirName = new Array('上方','右侧','下方','左侧');
     if(e.type == 'mouseenter'){
         $(this).html(dirName[direction]+'进入');
     }else{
         $(this).html(dirName[direction]+'离开');
     }
});

```

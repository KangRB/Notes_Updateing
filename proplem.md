# 整理的一些遇到的琐碎问题

1. ### 在做只有1/8的边框有颜色的圆环时，想到先做一个1/4边框有颜色的圆环，然后再用::before伪元素添加一个对应大小的有1/4边框透明的圆环覆盖并旋转。
      + 问题：添加覆盖的圆环时，出现位置不对应问题
      + 解决：需设置覆盖圆环的**position：absolute;** 并把 **top** 和 **left** 值设置成圆边 **border-width** 对应大小的 **负值**
      + eg:  
      ```
            .item:nth-of-type(1) .redius:nth-of-type(3)::before{
              content: '';
              position: absolute;
              top:-20px;
              left:-20px;
              width: 60px;
              height: 60px;
              border-radius: 50%;
              border:20px solid #ccc;
              /*transform: rotate(-45deg);*/
              border-color: #ccc #ccc transparent;
            }
      ```

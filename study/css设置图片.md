## div中图片高度自适应并与父元素等宽
### 需求：1、父元素不设置高度 2、图片高度自适应并且显示为正方形

img的父元素css：
.imgbox{
    position: relative;
    overflow: hidden;
    padding-bottom: 100%;/*重要属性*/
    outline: 1px solid green;
}
.imgbox img{
    width: 100%;
    position: absolute;
}
说明：装图片的盒子imgbox，设置的padding-bottom，当该值为百分比属性时，是基于父元素宽度的百分比，所以这里设置100%的时候，就相当于形成了一个正方形。当然，也可以设置padding-top。这时img就需要设置top:0;了。记得img要设置100%宽度。
亦可以根据通过调整padding-bottom的值来实现宽高按一定比例来显示

### 附：关于element-ui的Image组件
fit属性可以设置图片图和适应到容器框，同原生 object-fit
fill: 中文释义“填充”。默认值。替换内容拉伸填满整个content box, 不保证保持原有的比例。
contain: 中文释义“包含”。保持原有尺寸比例。保证替换内容尺寸一定可以在容器里面放得下。因此，此参数可能会在容器内留下空白。
cover: 中文释义“覆盖”。保持原有尺寸比例。保证替换内容尺寸一定大于容器尺寸，宽度和高度至少有一个和容器一致。因此，此参数可能会让替换内容（如图片）部分区域不可见。
none: 中文释义“无”。保持原有尺寸比例。同时保持替换内容原始尺寸大小。
scale-down: 中文释义“降低”。就好像依次设置了none或contain, 最终呈现的是尺寸比较小的那个。

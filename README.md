# iMOOC_H5_Reader
慕课网练习-移动Web App阅读器的实现  
## 实现功能：

 - 移动端兼容  
 - 使用`zepto`来实现交互动作 
 - 使用`iscrool`来优化滑动效果  
 - 使用`ajax`来请求数据 
 - 使用`json`文件模拟数据交互,实现了上下章节的切换  
 - 使用`localStrong`来保存用户操作记录


### 1. 如何将`jquery`的插件挂载到`zepto`中？   

```
//先引入zepto，然后将window下的jquery对象指向zepto中的$
<script>
window.jQuery = $;
</script>   
```

### 2.click事件  
在android4.0之前，click事件有300ms的延迟，在android4.0以后就没有了这个延迟  

### 3.移动端rem适配  
首先设置`viewport`的`meta`标签，然后根据浏览器的像素比`window.devicePixelRatio`来判断缩放，最后去动态计算rem  
````
var i = 0;
i = window.devicePixelRatio > 1 ? 1 / window.devicePixelRatio : 1;
document.write('<meta name="viewport" content="width=device-width,initial-scale=' + i + ',minimum-scale=' + i + ',maximum-scale=' + i + ',user-scalable=no" />');

var oHtml = document.getElementsByTagName("html")[0];
var iWidth = oHtml.getBoundingClientRect().width;
oHtml.style.fontSize = iWidth / 28.8 + "px";
````

这里设置html的`fontsize`是使用设计图的尺寸来除以一个数值的出的就是rem的基准值。尽量使所得数值为整数。  

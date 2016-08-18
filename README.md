# iMOOC_H5_Reader
慕课网练习-移动Web App阅读器的实现  
## 实现功能：

 - 移动端兼容  
 - 使用原生js来实现交互动作 
 - 使用`iscrool`来优化滑动效果  
 - 使用`ajax`来请求数据 
 - 使用`json`文件模拟数据交互,实现了上下章节的切换  
 - 使用`airTemplate`来渲染数据  
 - 使用`localStrong`来保存用户操作记录


### 1. 如何将`jquery`的插件挂载到`zepto`中？   

```
//先引入zepto，然后将window下的jquery对象指向zepto中的$
<script>
window.jQuery = $;
</script>   
```

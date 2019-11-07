# 前端学习

### 1、margin:0 auto介绍  
    margin:0 auto 设置对象上下间距为0，左右自动  
    可拆分： margin:0 auto 0 auto（上下）  
    还可拆分为：margin-left:auto;margin-right:auto;margin-top:0;margin-bottom:0;

### 2、作用
    对DIV设置margin:0 auto样式，是为了让DIV在浏览器中水平居中。布局居中、水平居中，均加入margin:0 auto即可。

### 3、float:left float 
    浮动到左边，浮动到右边，即设置布局在左侧或者右侧

### 4、设置css，让元素脱离文档流
    浮动（float）和绝对定位（position：absolute）  
    注：相对定位（position：relative）,不可以脱离文本流

### 5、绝对定位和相对定位
    绝对定位（position：absolute）；left:0；top:0 相当于在左侧  
    相对定位（position：relative）；right:0；top:0 相当于在右侧  
### 6、初始化属性状态
    ul{list-decoration:none;} 清除列表状态  
    a{text-decoration:none;} 清除文字初始化状态，如清除下划线  
    text-indent:10px内部向左10px  
    text-align:center 居中
    display:block; 设置标签为块元素  
### 7、鼠标指向位置
    未被访问的链接
    a:link {color: #000;}   
    鼠标指针移动到链接上  
    a:hover {color:white; height:30px; background: #f00;}
    正在被点击的链接
    a:active {color:#000;}  
    已被访问的链接  
    a:visited {color:#a369af;}
### 8、通常用 html 中的什么标签来构建导航条菜单
    li{float:left}  添加水平浮动，会变成水平的导航栏
    ul-li无序列表 ( 网页中显示的默认样式一般为：每项 li 前都自带一个圆点 )语法:
    <ul>
        <li>文本</li>
        <li>文本</li>
    </ul>     
    ol-li有序列表(在网页中显示的默认样式一般为：每项 li 前都自带一个序号，序号默认从1开始)
    <ol>
        <li>文本1</li>
        <li>文本2</li>
    </ol>    
    ul{border-bottom:5px solid #f60;} 添加一个高度为5px的水平的横线
    background-position:0 -30;    0----水平方向位置，-30----垂直方向位置
    注意： 菜单<li>浮动后，<li>脱离文档流，导致<ul>将失去高度和宽度；如果需要对<ul>进行整体背景设置，首先要给<ul>定义宽、高。
### 9、给选中的导航条设置高度
    设置当前选中的标签设置高出其他的10px 
    a.on, a:hover{ color:#fff;background-color:#F60;height:40px; line-height:40px;margin-top:-10px;}

 ### 10、vue.js学习
    通过src="./vue.js"引入  

    挂载点，模板，实例之间的关系
    <div id="root"></div>  //<div id="root"></div>称为vue实例的挂载点
    new Vue({
        el: "root",
        //挂载点内部的内容，可以写在挂载点内部，或实例中template属性中。
        template: '<h1>hello {{msg}}</h1>',  
        //Vue会结合模版和数据生成最终要展示的内容，然后把它放在挂载点之中。
        data: {
            msg: "world"
        }
    });
### 11、Vue实例中的数据，事件和方法
    v-on:click = @click,触发一个点击事件通过实例操作dom
    v-text,输出文本
    v-html，输出HTML
    事件写在 vue实例的methods中
    methods:{
		handleClick:function(){
			alert(123)
		}
	}

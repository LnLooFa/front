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
### 12、Vue中属性绑定和双向数据绑定
    v-bind:title="title"
    简写:title="title"          
    v-bind:绑定属性 
    =后面不是字符串，是js表达式，实例里的变量
    v-model //数据的双向绑定
### 13、Vue中的计算属性和监听器
    computed{对象}计算属性，当依赖的数据发生变化才会重新计算，如果依赖的数据没有发生变化，会用上一次计算的缓存显示
    computed{
        fullName：function(){
            return this.firstName+''+this.lastName
        }
    }
    watch：侦听器，监听某一个数据的变化
    watch:{
        key的值与data中key值相对应：function()
    };
### 14、Vue中v-if,v-show与v-for指令
    1、v-if和v-show区别：展示的效果一样，但是 v-if（控制dom的存在与否）是通过删除/增加代码的方式来隐藏/显示内容；v-show（控制dom的显示与否）是通过改变css代码来显示/隐藏元素内容。
    2、在使用上的建议：页面内如果需要频繁的显示隐藏dom，就是用v-show，这样不会删除掉代码，如果只需显示隐藏一次就使用v-if 。 
    <body>        
        <div id="root">          
            <div v-if="show">hello world</div> <!-- v-if可以换成v-show -->      
            <button @click="myClick">toggle</button> <!-- v-on的简写@ -->       
        </div>        
        <script>          
            new Vue({              
            el:"#root",             
            data:{                  
                show:true               
                },              
            methods:{                   
            myClick:function(){                 
            this.show=!this.show;<!-- 反复点击按钮可以让show反复显示/隐藏 -->
            }
            }
            })
        </script>
    </body>
    3、v-for做页面上循环内容的展示 :key可以提升每一项渲染的性能，但是要求:key要求:key值也就是每一项循环的内容都不同。
    <body>        
    <div id="root">          
        <ul>              
        <!-- <li v-for="item of list" :key="item">{{item}}</li> 这句循环list内容，把每一次循环显示在item里-->               
        <li v-for="(item,index) of list" :key="index">{{item}}</li><!-- 这句优化上面的:key因为key值不能相同，每一次循环列表得到item和数组下标index，将key值换成index值就不会有相同 -->          
        </ul>     
    </div>        
    <script>          
        new Vue({              
        el:"#root",             
        data:{                  
            list:[1,2,3]                
        }               
     })        
    </script>
    </body>
### 15、TodoList功能
    通过this调用vue实例的data属性
    list.push往列表里添加值
    如下this.inputValue=''让提交后input框清空

    <body>
    <div id="root">
	<div>
		<input v-model="inputValue" />
		<button @click="handleClick">提交</button>
	</div>
	<ul>
		<li v-for="(item,index) of list" :key="index">{{item}}</li>
	</ul>
    </div>
    <script type="text/javascript">
        new Vue({
            el:"#root",
            data:{
                inputValue:'hello',
                list:[]
            },
            methods:{
                handleClick:function(){
                    this.list.push(this.inputValue);
                    this.inputValue='';
                }
            }
        })
    </script>
    </body>
### 16、todolist组件拆分

    页面内容过于复杂，可将组件拆分，可定义全局组件或局部组件：
    1、全局组件：在页面任何地方都能使用
    //定义全局组件
    Vue.component("todo-item", {
        template: "<label>我是全局组件</label>"
    });
    new Vue({
        el: "#root",
    });
    //使用全局组件
    <div id="root">
        <todo-item></todo-item>
    </div>
    2、局部组件：要在外层Vue实例里进行注册
    //定义局部组件
    var todoItem = {
        template: "<label>我是局部组件</label>"
    }
    new Vue({
        el: "#root1",
        components: { //局部组件：要在挂载点(它的外层Vue实例，即此处的root1)进行注册
            "todo-item-1": todoItem
        }
    });
    //使用局部组件
    <div id="root1">
        <todo-item-1></todo-item-1><!--局部组件：只能在挂载点底下使用-->
        <todo-item></todo-item><!--全局组件：在页面任何地方都能使用-->
    </div>
    组件拆分之后的传参问题：外部(html页面)可以通过自定义属性的形式传参，组件要定义props[]接收属性
    //父组件向子组件传递数据：通过属性
    Vue.component("todo-item-2", {
        props: ["content", "index"],//接收从外部传进来的属性content、index
        template: "<li>{{index+1}}、{{content}}</li>"
    });
    new Vue({
        el: "#root2",
        data: {
            inputValue: "",
            list: []
        },
        methods: {
            submitClick: function () {
                this.list.push(this.inputValue);
                this.inputValue = "";
            }
        }
    })
    <div id="root2">
        <div>
            <input v-model="inputValue" />
            <button @click="submitClick">提交</button>
        </div>
        <ul> <!--自定义属性content、index-->
            <todo-item-2 v-for='(item,index) of list'
                         :key="index"
                         :content="item"
                         :index="index" 
            >
            </todo-item-2>
        </ul>
    </div>
### 17、实例与组件关系
    每一个组件都是一个Vue的组件实例，实例的模板里使用一个小的组件。
    每一个组件也可以写methods，data。因此每一个组件都是一个Vue的实例。

    如果不定义模板，就会根据挂载点下面的DOM标签标签全部内容当做模板。
### 18、todolist删除功能
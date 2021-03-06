# **igem wiki编写团队规范(初稿）**

> * ## 命名规范

采用驼峰命名法(暂定)

> * ## html规范

1. ### id的使用

  id唯一，每个id对应唯一的一个元素，避免同一个id对应多个元素
  
  若是没有用到元素的id时，不设置id值
  
  若是想要设置css，请使用class
  
  ```html
 <p id="p1"></p>
 <p id="p2"></p>
 <p id="p3"></p>
  ```
  
2. ### class的使用

  class属性用于设置css，将大量相同样式设置为一个属性，用到时直接设置class属性
  
3. ### 代码格式规范

  同级元素缩进空格相同，子元素与父元素相比缩进4个空格
  
  若元素标签内包含子元素标签则采取换行缩进
  
  此外，不要在标签中采用style设置css属性,但可以用style设置css变量
  
  ***注意，一定要有闭标签***

 ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset="utf-8">
      </head>
      <body>
          <div>
              <div style="--s=1;">
                  <p>hello world!</p>
              </div>
          </div>
          <div style="--s=2;">
              <p>hello world!</p>
          </div>
      </body>
  </html>
  ```

  ```css
   div{
       left:clac(var(--s)*100px-100px)；
       width:100px;
       height:100px;
   }
  ```

> * ## css规范

1. ### 避免采用id选择器

  以class属性设置css样式能很大程度减少代码量

2. ### （可选）采用css变量设置某些重复属性值

  运用css变量能减少修改代码时的工作量

  ```css
  :root{
      --bgcolor:black;
      --boxcolor:skyblue;
  }
  body{
      background-color: --bgcolor;
  }
  .box1{
      background-color: --boxcolor;
  }
  .box2{
      background-color: --boxcolor;
  }
  ```
  
3. ### (可选)代码模块化，有顺序
  
  模块化：将代码划分为几个模块，将排版样式等通用样式写在一个css中命名为common.css;将某些专有样式设置写在一个文件，必如loading动画的css设置，命名为loading.css

  有顺序：编写css代码时，依照一定的顺序(默认为元素的先后顺序)。通用型样式写在最前方。

  ```html
    <body>
        <div >
            <div class="text1 box1">
                <p>hello world!</p>
            </div>
        </div>
        <div class="text1 box2">
            <p >hello world!</p>
        </div>
    </body>
  
  ```

  ```css
  *{
      margin:0;
      padding:0;
  }
  body{
      background-color:black;
  }
  .text1{
      font-family:Sans-serif,Monospace;
      font-size:5vh;
  }
  .box1{
      height:50vh;
      width:50vh;
      background-color:blue;
  }
  .box2{
      height:100vh;
      width:100vh;
      background-color:yellow;
  }
  ```

> * ## javascript规范

1. ### 代码规范

注意代码层级，同级缩进相同，两层级间相差4个空格

对于for、if等语句花括号不要省略

一句代码结束注意换行

```javascript
function(this,(e)=>{
    var i=0;
    for(;i<10;i++){
        i+=i;
    }
    this.value=i;
})
```

> * ## 注释规范

在实现某特定功能或效果的代码块的最上方标明实现了什么(标明开头和结尾)

```html
 <!-- 导航栏 start-->
 <div class="top box1">
     <ul class="topboard">
         <li><a href="javascript:void(0)">home</a></li>
         <li><a href="javascript:void(0)">project</a></li>
         <li><a href="javascript:void(0)">team</a></li>
     </ul>
 </div>
<!-- 导航栏end -->
 ```
 ```css
 *{
    margin:0;
    padding:0;
 }
 .box1{
    border-radius: 5px;
    opacity: 0.5;
 }
 /*导航栏样式start*/
 .top{
     width:100%;
 }
 .topboard{
     display: flex;
     width: 100%;
     min-width: 122px;
     justify-content: space-around;
     background-color: black;
     /* height: 30px; */
 }
 .topboard li{
     list-style: none;
     text-align: center;
     float: left;
     width: 33%;
 }
 .topboard li a{
    text-decoration: none;
    display: block;
    font-size: 5vh;
    color: white;
    border-style: white;
    width: 100%;
    justify-content: space-around;
    border-right: white;
 }
 .topboard li a:hover{
    background-color: rgb(240, 222, 222,0.1);
 }
 /*导航栏样式end*/
 ``` 
 

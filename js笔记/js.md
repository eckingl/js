# javascript

- ###ECMAScript

   1. #####**基本语法**
   
        1. 与html的结合方式
   
            1. 在html中插入script语句
   
            ```html
            //先出现先执行
            //第一种插入方式,直接插入
            <script>
             	alert("hello world");
            </script>
            //第二种插入方式,js代码位于其他js文件
            <script src="js/a.js"></script>
            ```
   
        2. 注释
   
             1. 单行注释 ://
             2. 多行注释 :/*   */
   
       3. 数据类型
   
          1. 基本数据类型
   
             1. number :整数,小数,NaN(not  a number)
             2. String :字符串
             3. boolean :ture/false
             4. null :对象为空的占位符
             5. undefined :未定义,如果一个变量没有给初始化,默认赋值为undefined
   
          2.  引用数据类型 :对象
   
          3. 变量
   
              1. 定义变量
   
                  ```javascript
                  var a = 1;
                  alert(a);
                  //输出到页面上
                  document.write(a+"<br>");
                  ```
   
              2. 判断类型
   
                 ~~~javascript
                 var a = 1;
                 document.write(typeof(a));
                 ~~~
   
          4. 运算符
   
               1. 一元运算符
   
                     ++,--
   
               2. 算数运算符
   
                     +,-,*,/
   
               3. 赋值运算符
   
                     = , += , -=
   
               4. 比较运算符
   
                    < > >= <= == ===
   
               5. 逻辑运算符
   
                    && || !
   
               6. 三元运算符
   
                     ? :
   
                     ```javascript
                     var a = 3;
                     var b = 4;
                     var c = a>b ? 1:0;
                     //若a>b,则取1,反之取0
                     ```
   
       4. 流程控制语句
   
       5. 特殊语法
           1. 语句以;结尾,如果一行只有一条语句,则可以省略;
           2. 变量的定义使用var关键字,也可以不使用,若使用var定义,则为局部变量,不使用var定义,为全局变量
   
       6. 9*9练习
   
         ```html
         <style>
           td{
            border: 1px solid; 
           }
         </style>

         <script>

         document.write("<table>");

            for (var i = 1;i<=9;i++){
              document.write("<tr>")
              for (var j =1;j<=i;j++){
                document.write("<td>")
                document.write(i+"*"+j+"="+(i*j))
                document.write("</td>")
              }
              document.write("</tr>")
            }

         document.write("</table>")

         </script>
         ```
       
    2. #####**基本对象**
   
       1. **Function 对象:**函数对象
   
           - 创建
   
             ```javascript
             //方式一
             var fun = new function("a","b","alert(a)");
             //方式二
             function fun (a,b){
               alert(a+b);
             }
             //方式三
             var fun = function(a,b){
               alert(a+b); 
             }
             ```
   
           - 调用
   
             ```javascript
             fun(3,4);
             ```
   
           - 方法
   
           - 属性
   
                1. length:返回形参对象数量
   
                ```
                alert(fun.length);
                ```
       
           - 特点
   
             1. 方法定义时,形参的类型不用声明,返回值类型也可以不写
             
             2. 方法是一个对象,如果名称相同,会自动覆盖
             
             3. 在js中方法调用值与方法名称有关,和参数列表无关
             
             4. 在方法声明中,有一个隐藏的内置对象(数组),名称为arguments,封装所有的实际参数
             
               ```JavaScript
               //计算任意个数和相加
               function add(){
                 var sum = 0;
                 for(var i =0;i<arguments.length;i++){
                   sum += arguments[i];
                 }
                 return sum;
               }    
               ```
             
           
       2. **Array对象**
       
           + 创建
       
             ```javascript
             //方式一
             var arr = new Array(1,2,3);
             //方式二,若只有一个数,则这个数为数组长度,而非数组中数据
             var arr = new Array(4);
             //方式三
             var arr = [1,2,3]
             ```
       
           + 方法
       
             1. join("指定类型"):将数组中的元素按照指定的分隔符拼接为字符串
       
                ```javascript
                document.write(arr.join("-")+"<br>")
                ```
       
             2. push():添加元素
       
                ```javascript
                arr.push(11);
                ```
       
           + 属性
       
           + 特点
       
             1. js中,元素数组类型是可变的
       
                ```javascript
                var arr = new Array("a",1,ture);
                ```
       
             2. 数组的长度也是可变的
       
       3. **Date对象**
       
           + 创建
       
             ```javascript
             var date = new Date();
             ```
       
           + 方法
       
             1. toLocaleString():返回当前date对象对应的本地字符串格式
       
                ```javascript
                document.write(date.toLocaleString()+"<br>")
                ```
       
             2.  getTime():获取毫秒值,返回当前日期对象描述的时间与1970年1月1日时间   的毫秒值差
       
                ```javascript
                document.write(date.getTime()+"<br>
                ```
       
       4. **Math对象**
       
           + 创建
       
           + 	 ```javascript
               //math对象不用创建,直接使用
               document.write(Math.PI+"<br>")
               ```
       
           + 方法
       
               1. random():返回一个[0,1)之间的随机数
               
               2. round(3.14):四舍五入
               
               3. ceil(3.14):向上取整,返回4
               
               4. floor(3.14):向下取整,返回3
               
                  ```javascript
                  //取一个1-100之间的随机整数
                  var num = Math.floor(Math.random()*100)+1;
                  document.write(num);
                  ```
       
       5. **RegExp对象(正则表达式)**
       
           + 正则表达式:定义字符串的组成规则
           
             1. 单个字符:[]
           
                如:[a] [ab] [a-zA-Z0-9]
           
                特殊符号代表特殊含义的单个字符
           
                ​	\d:单个数字字符[0-9]
           
                ​	\w:单个单词字符[a-zA-Z0-9]
           
             2. 量词符号
           
                ? : 表示出现0次或1次
           
                *: 表示出现0次或多次
           
                +: 表示出现1次或多次
           
                {m,n} : 出现[m,n]次
           
                ​	m缺省 : {,n} 最多n次
           
                ​	n缺省 : {m,} 最少m次
           
             3. 开始结束符号
           
                 ^开始
           
                 $结尾
           
           + 正则对象
           
             1. 创建
           
                1. ```javascript
                   //方式一
                   var reg = new RegExp("^\\w{6,12}$");
                   //方式二
                   var reg = /\^w{6,12}$/;
                   ```
           
             2. 方法
           
                1. test():验证指定的字符串是否符合正则定义的规范
           
                   ```javascript
                   var usename = "zhangsan"
                   var flag = reg.test(usename);
                   ```
           
       6. **Global对象**
       
          + 特点:全局对象,这个Global中封装的方法不需要对象就可以直接调用
          
          + 方法
          
            1. encodeURI():URI编码
          
            2. decodeURI():URI编码
          
            3. encodeURIComponent():URI编码
          
            4. decodeURIComponent:URI编码
          
            5. paseInt():将字符串转为数字,逐一判断每一个字符是否为数字,直到不是数字之后,将前面数字转为number
          
            6. isNaN():判断一个值是否是NaN
          
            7. eval():将JavaScript字符串转成脚本来执行
          
               ```javascript
               var jscode = "alert("abc")";
               eval(jscode); 
               ```
               
               
   
- ### **基本DOM**
  
  1. 功能
  
     控制html文档的内容
  
  2. 代码
  
     获取页面标签(元素)对象Element
  
      ```html
     <img id="li" src="/文件地址">
     <script>
     	var light = document.getElementById("li"); 
        alert(light);
     </script>
      ```
  
  3. 操作Element对象
  
     1. 设置属性值
  
        1. 明确获取的对象是哪一个
  
        2. 查看api文档,找那些属性可以修改
  
           ```javascript
           light.src("/新文件地址");
           ```
  
     2. 修改标签体内容
  
        ```html
        <h1 id = "title">修改前内容</h1>
        <script>
          var title = document.write("title");
          title.innerHTML = "修改后内容";
        </script>
        ```
  
- ### **基本事件**

   1. 功能

      + 某些组件被执行了某些操作,触发了某些代码的执行

   2. 绑定事件

      1. 直接在html标签上,指定事件的属性(操作),属性值就是js代码

         1. 事件:onclick  单击事件

            ```html
            <script>
            	function(){
                alert("daying");
              }
            </script>
            
            <img id="li" src="tup" onclick="fun();">
            ```

      2. 通过js获取元素对象,指定事件属性,设置一个函数

         ```html
         <img id="ki" src="tup">
         <script>
           function fun(){
             alert("dayin");
           }
         	var light = document.getElementById("ki");
            light.onclick = fun;
         </script>
         ```

   + 电灯开关案例

     ```html
     <img id="haha" src="js/learnJs/img/haha1.jpg" alt="tu">
     <script>
		// 获取图片	
     	var haha = document.getElementById("haha");
     	var flag = false;
     	// 绑定事件
     	haha.onclick = function () {	
     		if (flag) {
     			haha.src = "/Users/lukang/local/js/learnJs/img/haha1.jpg";
     			flag = false;
     		}else{
     			haha.src = "/Users/lukang/local/js/learnJs/img/haha2.jpg";
     			flag = true;
     		}
     	}
     </script>
     ```
     
   
   
   
- ### **BOM**

   1. 概念

      + 浏览器对象模型(Brower object Model)

   2. 组成

      1. **window(窗口对象)**

         1. 创建

         2. 方法

            1. 与弹出框有关的方法

               ~~~javascript
               //显示带有一段消息和一个确认按钮的警告框
               alert();
               //显示带有一段消息以及确认按钮和取消按钮的对话框
               //如果用户点击确认按钮,返回true,否则返回false
               confirm();
               //显示可提示用户输入的对话框
               //返回值:获取用户输入的值
               prompt();
               ~~~

            2. 打开关闭相关的方法 

               ```html
               <!-- 
               	open():打开一个新的浏览器窗口
               	close():关闭浏览器窗口.谁调用关谁 
               	疑问:chrome浏览器close无法关闭自己打开的页面
               -->
               <input id="openBtn" type="button" value="打开窗口">
               <input id="closeBtn" type="button" value="关闭窗口">
               <script>
                 var openBtn = document.getElementById("openBtn");
                 var newwindow;
                 openBtn.onclick = function(){
                 	newwindow = open("https://www.baidu.com/s?wd=a");
               	}
                 var closeBt = document.getElementById("closeBtn");
                 closeBt.onclick = function(){
               	  newwindow.close();
               	}
               </script>
               ```

            3. 定时器相关的方法

               1. 一次性定时器
               
                  1. setTimeout():在指定的毫秒数后调用函数或计算表达式
               
                     参数:1.js代码挥着方法对象
                     		  2.毫秒值
                  
                   返回值:唯一标识,用于取消定时器
                  
                  ```javascript
                  var id = setTimeout(fun,2000);
                  function fun(){
                    alert("时间到了")
                  }
                  ```
                  
               2. clearTimeout():取消由setTimeout()方法设置的timeout
               
                  ```javascript
                   clearTimeout(id);
                  ```
            
         2. 循环定时器
           
             1. setInterval():    
             
                 ```javascript
                 var id = setInterval(fun,2000);
                 ```
             
             2. clearInterval();
             
                ```javascript
                clearInterval(id);
                ```
      
         4. 属性
      
            1. 获取其他BOM对象:history location navigato screen
      
               ```javascript
               //其他同理
               var h1 = window.history
               var h1 = history;
               ```
      
            2. 获取DOM对象:document
      
               ```javascript
               //省略window.
               window.document.write();
               document.write();
               ```
      
         5. 特点
      
            + window对象不需要创建可以直接使用, window.方法名()
            + window引用可以省略,方法名()
      
         6. 案例
      
            1. 循环播放图片
      
               ```html
               <img id="img" src="js/learnJs/img/haha_1.jpg" alt="tupian">
               <script>
               	var number = 1;
               	function fun(){
               		number++;
               		if (number>2) {
               			number=1;
               		}
               	var img = document.getElementById("img");		
                img.src="/Users/lukang/local/js/learnJs/img/haha_"+number+".jpg"
               	}
               	setInterval(fun,3000);
               </script>
               ```
      
               
      
      2. **history(历史记录对象)**
      
         1. 创建
      
            ```javascript
            //和window对象同理
            window.history;
            history
            ```
      
         2. 方法
      
            1. back():加载history列表的前一个URL
      
               ```html
               <input id="back" type="button" value="后退">
               <script>
               	var back = document.getElementById("back");
                  back.onclick = function(){
                    history.back();
                  }
               </script>
               ```
      
            2. forward():加载history列表的下一个URL
      
               ```html
               <input id="forward" type="button" value="前进">
               <script>
               	var forward = document.getElementById("forward");
                  forward.onclick = function(){
                    history.forward();
                  }
               </script>
               ```
      
            3. go(参数:正数前进,负数后退):加载history列表的某一个URL
      
               ```html
               <input id="forward" type="button" value="前进">
               <script>
               	var forward = document.getElementById("forward");
                  forward.onclick = function(){
                    history.go(1/*也可以-1*/);
                  }
               </script>
               ```
      
               
      
         3. 属性
      
            1. length:返回当前窗口的历史记录个数
      
               ```javascript
               var length = history.length
               ```
      
      3. **location(地址栏对象)**
      
         1. 创建
      
            ```javascript
            //和window对象同理
            window.location;
            location;
            ```
      
         2. 方法
      
            1. reload():重新加载当前文档,刷新
      
               ```html
               <!--点击就自动刷新-->
               <input id="btn" type="button" value="刷新">
               <script>
                 var btn = document.getElementById("btn");
                 btn.onclick = function(){
                   location.reload();
               }
               </script>
               ```
      
         3. 属性
      
            1. href
      
               ```html
               <!--点击就自动刷新-->
               <input id="goto" type="butt" value="百度一下">
               <script>
                 //获取href
                 var href = location.href;
                 alert(href);
                 //点击切换网址
                 var goto = document.getElementById("goto");
                 goto.onclick = function(){
                   location.href = "https://www.baidu.com"
                 }
               </script>
               ```
      
         4. 案例
      
            1. 自动跳转首页
      
               ```html
               <style>
                 /*居中,字体颜色*/
               	p{
               		text-align: center;
               	}
               	span{
               		color: red;
               	}
               </style>
               <p>
               	<span id="time">5</span>秒后,自动跳转
               </p>
               <script>
               	//s:倒计时
               	var s = 5;
                  var time = document.getElementById("time");
               	function showtime(){
               		s--;
               		if (s<=0) {
               			location.href = "https://www.baidu.com";
               		}
               		time.innerHTML = s +"";
               	}
                 setInterval(showtime,1000);
               </script>
               ```
      
      4. navigato(浏览对象)
      
      5. screen(显示器屏幕对象)
   
- ### **DOM系统**

   1. 概念:Document Object Model 文档对象模型

       将标记语言文档的各个组成部分封装为对象.可以使用这些对象,对标记语言文档进行CRUD的动态操作

      ![ct_htmltree](/Users/lukang/local/js/js笔记/ct_htmltree.gif)
      
   2. W3C DOM
   
       1. 核心DOM
           1. document:文档对象
           2. element:元素对象
           3. Attribute:属性对象
           4. Text:文本对象
           5. Comment:注释对象
           6. Node:节点对象,其他的父对象
       2. XML DOM
       3. HTML DOM
   
   3. ####**核心DOM模型**
   
       1. **Document :文档对象**
   
           1. 创建:在html dom模型中可以使用window对象来获取
   
              1. `window.document`
              2. `document`
   
           2. 方法
   
              1. 获取Element对象
   
                 1. getElementById() :根据id属性获取元素对象,id属性值一般唯一
   
                    ```javascript
                    var time = document.getElementById("time");
                    ```
   
                 2. getElementByTagName() :根据元素名称获取元素对象们,返回值是一个数组
   
                    ```html
                    <div id="div1">div1</div>
                    <script>
                    	var divs = document.getElementByTagName("div");
                    	alert(divs.length);
                    </script>
                    ```
   
                 3. getElementByClassName() :根据class属性值获取元素对象,返回值是一个数组
   
                    ```html
                    <div class="cls1">div1</div>
                    <script>
                    	var cls = document.getElementByClassName("cls1");
                    	alert(cls.length);
                    </script>
                    ```
   
                 4. getElementByName() :根据name属性值获取元素对象,返回值是一个数组
   
                    ```html
                    <input name="usename" type="text">
                    <script>
                    	var ele_na = document.getElementByName("usename");
                    	alert(ele_na.length);
                    </script>
                    ```
   
              2. 创建其他DOM对象
   
                 1. createAttribute(name)
   
                 2. createComment()
   
                 3. createElement()
   
                    `var table = document.creatElement("table");`
   
                 4. createTextNode()
   
           3. 属性
   
       2. **Element:元素对象**
   
           1. 创建
   
           2. 方法
   
               1. removeAttribute():删除属性
   
                  ```html
                  <a>点击我试试</a>
                  <input id="removeA"type="button" value="删除属性">
                  <script>
                    var removeA = document.getElementById("removeA");
                    removeA.onclick = function(){
                    	var element_a = document.getElementsByTagName("a")[0];
                    	element_a.removeAttribute("href");
                  	}
                  </script>
                  ```
   
                  
   
               2. setAttribute():设置属性
   
                  ```html	
                  <a>点击我试试</a>
                  <input id="btn_A" type="button" value="设置属性">
                  <script>
                    var btn_set = document.getElementById("btn_A");
                    btn_set.onclick = function(){
                      var element_a = document.getElementsByTagName("a")[0];
               	 element_a.setAttribute
                     ("href","https://www.baidu.com");
                  }
                 </script>
   ```
                 
       
       3. **Node对象**
   
           1. 特点:所有dom对象都可认为是一个节点
   
           2. 方法
       
               1. CRUDdom树
       
                   1. 添加 appendchild()
       
                       ```html
                       <style>
                         #div3{
                       		width: 100px;
                       		height: 100px;
                       		border: 1px solid red;
                       	}
                       </style>
                       <div id="div1">
                        	<div id="div2">
                          	div2
                         	</div>
                         div1
                       </div>
                       <script>
                       	var element_add = document.getElementById("add");
                       	element_add.onclick = function(){
                           var div1 = document.getElementById("div1");
                           //创建节点
                           var div3 = document.createElement("div");
                           //添加样式
                           div3.setAttribute("id","div3");
                           div1.appendChild(div3);
                       	}
                       </script>
                       ```
       
                       
       
                   2. 删除 removechild()
       
                       ```html
                       <style>		
                       	div{
                       		border: 1px solid red;
                       	}
                       	#div1{
                       		width: 200px;
                       		height: 200px;
                       	}
                       	#div2{
                       		width: 100px;
                       		height: 100px;
                       	}
                       </style>
                       <div id="div1">
                        <div id="div2">
                          div2
                         </div>
                         div1
                       </div>
                       <script>
                       	var element_a = document.getElementById("del");
                       	element_a.onclick = function (){
                       		var div1 = document.getElementById("div1");
                       		var div2 = document.getElementById("div2");
                       		div1.removeChild(div2);
                       	}
                       </script>
                       ```
       
                   3. 替换 replacechild()
       
           3. 属性
       
               1. parentNode;
       
                   ```javascript
                   var div2 = document.getElementById("div2");
                   var div1 = div2.parentNode;
                   alert(div1);
                   ```
       
       4. **案例**
       
           ```html
           <!--动态表格-->
           ```
       
           
       
       
       
       
       
       



























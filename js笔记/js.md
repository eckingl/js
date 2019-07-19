# javascript

- 

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
               
               
   
- ### DOM
  
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
  
- **事件**

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
     
     ```

     

































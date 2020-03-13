# 前端使用

# 一、HTML编码规范

1. 所有HTML代码均采用小写。

2. 声明属性一定要赋值，且用`""`括起来，属性与属性之间保持一个空格的缩进。

3. 标签要成对出现，如果是单独不成对的标签，在标签最后添加`/`来关闭，例如：`<br />`。

4. 表现和结构分离，代码中尽量不涉及到任何表现元素，如:`style、font、border....`，结构页面中只写入结构代码，样式代码写入到css文件中或页面的head区。

5. 不要使用`<font>`标签，用`<span>`代替。

6. 不要使用`<b>`，可以使用`<strong>`代替。

7. 不要在`<a>`内使用`<span>`改变连接文字颜色。

8. 用`<checkbox>`时，必须用`<label for="checkbox.id"></label>`把说明文字和`checkbox`组合起来，这时文字的点击效果和`checkbox`等同。

9. 在每个内容块的开始和结束处加入注释,例如：

   ```html
   <!--登录框 begin-->
   ......
   <!--登录框 end-->
   <!-- 注意，不要再注释内容中加入“-”； -->
   ```

10. HTML标签必须合理嵌套，并要有一定的层次感。

# 二、CSS书写规范

1. 尽可能的通过继承和层叠重用已有样式。

2. 根据新建样式的适应范围分为三级：全站级、频道级、页面级：

   1. 全站级：`global.css` 这个是全局（如果要修改这个`css`要测试整个网站）。
   2. 频道级:文件存在在`css/`相应目录下  （如：`zhekou\fanli`等）。
   3. 页面级：少量几个页面，写成`css`文件，并做注释  如果只有仅在一个页面里使用，则可以放在`head`头部

3. 单条CSS规则的书写要求格式要求:

   1. 属性需要写在一行，需要在`"{"` `"}"`前后加空格， 在属性的`;`后也加空格。

      ```css
      .selector { property:value; property:value; }
      ```

   2. 多个 selector每个占一行，如：

      ```css
      .selector1,
      .selector2,
      .awlwxroe3 { property:value; property:value; }
      ```

   3. 兼容多个浏览器，将标准属性写在前面，如：

      ```css
      width:100px; *width:100px; _width:100px;
      ```

4. 将作用于不同模块的`CSS`放在一起，一定要加注释

   ```css
   /*nav start*/
   .....................
   /*nav end*/
   ```

5. `ID`和`ClASS`命名不要用缩写，单词用“_”分隔, 慎用`ID`,应该多用`CLASS`。如：`.nav_footer{}`

6. 推荐使用的`CLASS`名:

   ```css
   .on .active .selected   //表示状态：
   .first  .last .main .side  //表示位置：
   .hd .bd .ft .col .section  //表示结构：
   .tb .frm .nav .list .item .tag .pic .info  // 通用元素：
   ```

7. 推荐使用下面的`CSS`方式:

   | 浏览器      | 区别属性          | 区别规则                       |
   | ----------- | ----------------- | ------------------------------ |
   | IE6         | _property:value   | * html .selector{}             |
   | IE6/IE7     | *property:value   |                                |
   | IE6/IE7/IE8 | property:value\9  | *:first-child+html .selector{} |
   | 非IE6       | property//:value; | html>body .selector{}          |

8. 清除浮动用`global.css`里的两种类 `clear `和 `clear-fix`。

9. 页面引用css的顺序，全站-》频道-》页面-》内联 。

10. 避免使用低效的选择器，如：

    ```css
    body>*{}
    Ul > li > a{}
    #footer > h3{}
    Ul#top_blue{}
    #search span.submit a{}
    ```

11. 尽量避免使用` filter`

12. 不要直接修改标签的样式

13. 不要在标签上直接写样式，如：`<div style=”height:100px;”></div>`。

14. 尽量不用 `expression`

15. 不要使用 `@import url(1.css)`;

16. 尽量不用 `！important    `

17. 绝对不要在css中使用 `*`选择符 ` *{margin:0,padding:0;}`

# 三、JS代码

1. js代码分三级，公共级、频道级、页面级 （js文件名全为小写）;公共级：`js/global.js`;频道级：`js/频道名/频道名.js`；页面级：如果少可以用`<script>`放在页尾 ，如果非常多，也可以放在频道目录。

2. 变量命名规范：

   1. 常量以及全局变量必须全部使用大写字母，单词之间用下划线分隔，如：`var MMS_FRAME, LIMITE_TIME`。

   2. 方法内变量使用多个单词组成复合词，首单词小写，其它字母大写，如：`arrSampleList  objSubmitBotton`。

   3. 对于指定Dom对象的变量名，尽量使用elm、obj或elm、obj开头命名：

      ```js
      var objSubmitButton = document.getElementById('btn_submit');
      function getCheckElement(){
      	var obj = document.getELementById(name); //如果方法内部只有一个对象
      }
      ```

   4. 对于指定字符串的变量名，尽量用str,或str开头，`var strMaxTips = ‘最大的提示信息’;`。

   5. 对于指定数字的变量名，尽量使用num或num开头，`var numMaxcount = 1000;`。

   6. 布尔值的变量名的命名前面加is,同理可以加 has,can,should，`Var isChecked, hasApple, canDoit;`

   7. 循环变量使用 i,j,k 

   8. 用于返回结果变量用result 或 ret开头的变量

   9. 临时变量为temp,捕捉变量为e

   10. 数组变量在单词前加arr，`var arrCity = [‘北京’,‘上海’];`

   11. 避免使用否定的变量名称，例如：`isNotError, isNotFound`

3. 方法命名规范：

   1. 方法命名使用多个单词组成复合词，首单词小写，其它单词首字母大写。
   2. 方法命名的第一个单词尽量使用动词。例如：get/set  add/remove  create/destroy   start/stop   insert/delete  begin/end等

4. 类或组件的命名规范：

   1. 类名称必须为名词并使用骆峰命名法，如：`Account , EventHandler`。

   2. 类内的常量必须在对象（类）的前部声名，或枚举变量的前部声名，全用大写

      ```js
      var NodeTypes = {
      	PI:3.1415,
      	ELEMENT:2
      }
      ```

   3. 方法的命名为一个动词或动词短语  如：`obj.getElement(){}`

   4. 类的公有变量 ，  类的私有变量 命名规范：

      ```js
      var  MyClass = function(){
          this.myName = "robinName";  //公有变量
      };
      
      MyClass.prototype.getName = function(){
          var _thisName = "abc"; //私有变量前面加 ”_”
      } 
      
      ```

   5. 类的继承的方法：

      ```js
      var CatMyClass = function(){   //红色为基类的名称
        this.myClass = MyClass;
        this.myClass();
        ……
      };
      ```

5. 变量的定义与使用：

   1. 变量必须先定义后使用

   2. 声明变量时要初始化 null

   3. 变量应该放在和他有关系的代码中，不要把变量放在最上面，下面隔很远

   4. 变量具有最小的声明周期 ，执行完方法  内存就释放

   5. 应尽量避免复杂条件表达式：

      ```js
      		//如：不好的方法
              if(a == b && b == c && c==d){  //有些复杂了    }
              好的方法
              var isOk = (a == b && b == c && c==d);
              if(isOk){}
      ```

6. 空白的使用规范：

   1. 逗号后面跟一个空格：`var foo = function(name1, name2, name3){}`
   2. 冒号的前后各放一个空格：`var strPosition = (a>b) ? 'top' : 'botton';`。
   3. for语句的分号后面跟一个空格：`for(i = 0; i < 10; i++ ){}`。
   4. 分号前永远不要有空格：`var city = "shanghai";`。

7. js的一些建议：

   1. 使用{}来代替 new object(); 用[] 来代替new Array();

      ```js
      var arrCity = new Array('北京','上海','深圳');   //不建议
      var arrCity = ['北京','上海','深圳'];  //建议
      var objPerson = new object();   //不建议
      objPerson.name = 'robin';  
      objPerson.sex = 'man';
      var objPerson = {
          name:'robin',sex:'man'
      }
      ```

   2. 恒等运算和相等运算：

      ```js
      var a;
      alert(a==null)  //true
      alert(a==null)  //false
      alert(a===undefined)  //true
      ```

   3. Dom缓存已经访问过的元素。

   4. 离线更新节点。

   5. 如果拼字符串，不要用字符串相加，用数组来处理：

      ```js
      //如：不要这样做
      var str = '<div class="myclass">'+
                       '这些是内容'+
                       '</div>';
      var  str = new Array();
      str.push('<div class="myclass">');
      ```

8. 注释：

   1. 全局变量要有注释

   2. 整个方法也要加一下注释：

      ```js
      // 单行注释
      /*  多行注释 */
      ```

# 四、提示文字

1. 提示文字可以分为 鼠标移入提示、输入框备注、操作反馈、功能提醒，系统异常；

2. 鼠标移入提示实现包含 alt、titile、tips（使用不多）；

   > alt：图片的提示信息，主要是为了SEO优化；
   > title：主要用于文字、操作的解释，在大多数情况下用于段落显示不全的提示信息；
   > tips：对信息的对话云式的提示，用作在当前区域的提示；
   >
   >  注： alt和title会在几秒中后消失，对于比较重要的提示建议用tips或者用JS行为来控制提示信息。

3. 备注主要是 对表单输入框的输入提醒，显示在输入框右边，可以分为点击显示和默认显示；

4. 操作反馈提示是在操作表单时产生的提示文字或提示页面；

5. 表单输入框在输入过程中发生错误，在输入框下面显示提示文字；

6. 提交表单时，某输入框输入错误，在输入框下面显示提示文字；

7. 表单提交，操作结果根据成功、失败、系统异常转入对应提示页面；

8. 特别情况下，也可以把将提示信息显示在操作按钮右边或上面；

9. 功能提醒是对功能操作的注意点提示，放在操作表单底部；

10. 系统异常是在功能执行出现异常时提示给用户。

    >注：操作提示不能使用alert 弹框

# 五、操作

1. 所有操作步骤不能超过3步，并且不能有双向选择；
2. 操作步骤超过1步的时候需要有流程图提示，让用户知道下一步操作的内容。

# 六、SEO相关

1. 需要做SEO的页面网址目录层次不要超过4层，网址需要做静态化，目录命名以小写英文字母、下划线组成；

2. 网页title，keywords ，description设定（需要确定1个人定义这些内容告知技术）；

3. 减少css，js文件引用个数，各控制在2-3个；

4. 图片标签需要加入alt属性，不需要和title同时使用，需要时可以把title加到A标签；

   >  注：规范的HTML代码width及height标签也是需要的。title大多数情况下用于段落显   示不全的提示信息。

5. 页面中的js代码能放到页面末尾的放到页面末尾；

6. 页面html不能用table，改用div实现，并做到冗余代码的清除，保证hmtl代码简洁，style的代码尽量放入css文件；

7. 网页关键字需要用strong、h1~h6这样的标签，h1标签一个页面里面最多出现一次 ，每个页面中至少应该出现1次这样的标签。

# 七、其他

1. 网站可用色系demo准备
2. 按钮样式demo准备
3. 表单文本框、数据列表页样式demo准备
4. 链接文字样式准备，设定多套链接样式供不同频道，不同内容使用
5. 操作提示页面demo准备 ,可以分为操作成功、失败、系统异常3种操作提示页面demo准备 ,可以分为操作成功、失败、系统异常3种。
6. 操作提示文字颜色准备，可以分为功能提醒、输入框备注、警告、错误、系统异常5种。
7. 准备404,500错误页提示页面。










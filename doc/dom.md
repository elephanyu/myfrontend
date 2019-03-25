- dom 参考w3cschool教程
    - 概念
        - dom
            - 文档对象模型（Document Object Model），允许程序和脚本动态地访问和更新文档的内容、结构和样式
            - 分三种：核心DOM、XML DOM、HTML DOM，主用HTML DOM
        - dom节点
            - html文档中的所有内容都是节点
            - 整个文档是一个文档节点
            - 每个html元素是元素节点
            - html元素内的文本是文本节点
            - 每个html属性是属性节点
            - 注释是注释节点
        - 节点树
            - HTML DOM将html文档视作树结构，树中的所有节点均可通过javascript进行访问
            - 所有html元素（节点）均可被修改、创建和删除
            - 节点父(parent)、子(child)、同胞(sibling)
                - 节点树的顶端是根root
    - 方法和属性
        - 概念
            - 所有HTML元素被定义为对象
            - 方法是能够执行的动作（添加、修改元素）
            - 属性是能够获取或设置的值（节点名称、内容）
        - 方法
            - getElementById() 返回带有指定ID的元素
            - getElementsByTagName() 返回包含带有指定标签名称的所有元素的节点列表（集合/节点数组）
            - getElementsByClassName() 返回包含带有指定类名的所有元素的节点列表
            - appendChild() 把新的子节点添加到指定节点
            - removeChild() 删除子节点
            - replaceChild() 替换子节点
            - insertBefore() 在指定的子节点前面插入新的子节点
            - createAttribute() 创建属性节点
            - createElement() 创建元素节点
            - createTextNode() 创建文本节点
            - getAttribute() 返回指定的属性值
            - setAttribute() 把指定属性设置或修改为指定的值
        - 属性
            - innerHTML 节点（元素）的文本值
            - parentNode 节点（元素）的父节点
            - childNodes 节点（元素）的子节点
            - attributes 节点（元素）的属性节点  
            - nodeName 节点的名称，只读
                - 元素节点的nodeName与标签名相同
                - 属性节点的nodeName与属性名相同
                - 文本节点的nodeName始终是#text
                - 文档节点的nodeNmae失踪是#document
            - nodeValue 节点的值，读写
                - 元素节点的nodeValue是undefined或null
                - 文本节点的nodeValue是文本本身
                - 属性节点的nodeValue是属性值
            - nodeType 节点的类型，只读
                - 1 元素
                - 2 属性
                - 3 文本
                - 8 注释
                - 9 文档
            - x.length 节点列表中节点的数量
    - 修改
        - 修改html元素包含多种方面
            - 改变html内容
            - 改变css样式
            - 改变html属性
            - 创建新的html元素
            - 删除已有的html元素
            - 改变事件（处理程序）
                - 当用户点击鼠标时
                - 当网页已加载时
                - 当图片已加载时
                - 当鼠标移动到元素上时
                - 当输入字段被改变时
                - 当HTML表单被提交时
                - 当用户触发按键时
---
- dom实例
    - window对象
        - 显示对话框, 带有折行 alert("文本")
            - window.alert("message" + "\n" + "message2")
        - 显示确认框 prompt("文本","默认值")
            ```html
            <body>
                 <input type="button" onclick="disp_alert()" value="显示消息框" />
                 <script type="text/javascript">
                     function show_confirm() {
                         var r = window.confirm("Press a button!");
                         if ( r == true) {
                             alert("You pressed OK!");
                         }
                         else {
                             alert("You pressed Cancel!");
                         }
                     }
                 </script>
            </body>
            ```
        - 显示提示框，同上 prompt("文本","默认值")
            ```javascript
             function disp_prompt() {
                 var name = window.prompt("请输入您的名字","Bill Gates");
                 if (name != null && name != "") {
                     document.write("你好，" + name + "！今天过得好吗？")
                 }
             }
            ```
        - 通过点击按钮来打开一个窗口, 并控制其外观 
            - window.open("http://www.w3school.com.cn","_blank","toolbar=yes, location=yes, directories=no, status=no, menubar=yes, scrollbars=yes, resizable=no, copyhistory=yes, width=400, height=400")
            - window.close()
        - 把用户带到一个新的地址 
            - window.location = "/index.html"
        - 重新加载文档 
            - window.location.reload()
        - 打印页面 
            - window.print()
        - 跳出框架
            ```html
            <body>
                 <input type="button" onclick="breakout()" value="跳出框架！">
                 <script type="text/javascript">
                     function breakout() {
                         if (window.top != window.self) {
                             window.top.location = "/example/hdom/tryjs_breakout.htm"
                         }
                     } 
                 </script>
            </body>
            ```
        - 把窗口调整为指定的大小
            - window.resizeTo(500,300)
        - 滚动文档
            - window.scrollBy(100,100);
        - 把窗口滚动到指定的位置
            - window.scrollTo(100,500)
        - 简单的计时 setTimeout() clearTimeout()
            ```html
            <body>
                 <input type="button" value="显示计时的消息框！" onClick = "timedMsg()">
                 <script type="text/javascript">
                     function timedMsg() {
                         window.setTimeout("alert('5 seconds!')",5000)
                     } 
                 </script>
            </body>
            ```
        - 无穷循环中的计时 - 带有一个停止按钮
            ```html
            <body>
                 <form>
                     <input type="button" value="开始计时！" onClick="timedCount()">
                     <input type="text" id="txt">
                     <input type="button" value="停止计时！" onClick="stopCount()">
                 </form>
                 <script type="text/javascript">
                      var c = 0;
                      var t;
                      function timedCount() {
                          document.getElementById('txt').value = c;
                          c = c+1;
                          window.setTimeout("timedCount()",1000)
                      }
                      function stopCount() {
                          clearTimeout(t)
                      }
                 </script>
            </body>
            ```
        - 一个时钟
            ```html
            <body onload="startTime()">
                 <div id="txt"></div>
                 <script type="text/javascript">
                      function startTime() {
                          var today = new Date();
                          var h = today.getHours();
                          var m = today.getMinutes();
                          var s = today.getSeconds();
                          m = checkTime(m);
                          s = checkTime(s);
                          document.getElementById('txt').innerHTML = h + ":" + m + ":" + s;
                          window.setTimeout('startTime()',500);
                      }
                      function checkTime(i) {
                          if (i < 10) 
                              i = "0" + i;
                          return i
                      }
                 </script>
            </body>
            ```
    - document对象
        - document.cookie
        - 使用 document.write() 向输出流写内容
            - document.write("Hello World!")
            - document.write("\<h1>Hello World!\</h1>")
        - 返回当前文档的标题
            - document.title
        - 返回当前文档的 URL
            - document.title
        - 返回当前文档的 referrer
            - document.referrer
        - 返回下载当前文档的服务器域名
            - document.domain
        - 使用getElementById()、getElementsByName()
        - 打开一个新的文档，添加一些文本，然后关闭它。
            ```javascript
              var newDoc=document.open("text/html","replace");
              var txt="<html><body>学习 DOM 非常有趣！</body></html>";
              newDoc.write(txt);
              newDoc.close();
            ```
        - 返回文档中锚的数目
            - document.anchors.length
        - 返回文档中第一个锚的innerHTML
            - document.anchors\[0].innerHTML
        - 计算文档中表单的数目
            - document.forms.length
        - 计算文档中的图像数目
            - document.images.length
    - location对象
        - location.href 当前页面的 URL
        - location.assign() 加载新的文档
        - location.hostname 返回 web 主机的域名
        - location.pathname 返回当前页面的路径和文件名
        - location.port 返回 web主机的端口(80或443)
        - location.protocol 返回所使用的web协议(http://或https://)
    - history对象
        - history.back() 与在浏览器点击后退按钮相同
        - history.forward() 与在浏览器中点击按钮向前相同
    - screen对象
        - screen.width screen.height
        - screen.availWidth screen.availHeight
    - navigator对象
        - navigator.appName 浏览器名称
        - parseFloat(navigator.appVersion) 浏览器版本
        - navigator.appMinorVersion
        - navigator.platform 运行平台
        - navigator.appCodeName 代码开发平台（Mozila chrome）
        - navigator.cookieEnabled
        - navigator.userAgent 浏览器用户代理报头
        - navigator.cpuClass
        - navigator.onLine
        - navigator.browserLanguage
        - navigator.browserLanguage
        - navigator.userLanguage
    - event对象
        - 鼠标按钮被点击
            - event.button 0左键 1中键 2右键
        - 光标的坐标
            - x=event.clientX
            - y=event.clientY
        - 被按的按键的unicode
            - event.keyCode
        - 相对于屏幕光标的坐标
            - x=event.screenX
            - y=event.screenY
        - shift键是否被按
            - event.shiftKey 为1表示按了
        - 哪个元素被点击了
            - window.event.target.nodeType           
            - window.event.srcElement.nodeType
        - 哪个事件类型发生
            - event.type
    - anchor对象
        - 更改一个链接的文本、URL 以及 target
            - document.getElementById('myAnchor').innerHTML
            - document.getElementById('myAnchor').href
            - document.getElementById('myAnchor').target
        - 获取焦点、失去焦点
            - document.getElementById('myAnchor').focus()
            - document.getElementById('myAnchor').blur()
    - image对象
        - 更改图像高度和宽度
            - document.getElementById("compman").height = "270"
            - document.getElementById("compman").width = "164"
        - 更改图像的src
            - document.getElementById("myImage").src="/i/eg_smile.gif"
    - table、tableheader、tablerow、tabledata对象
        - 更改表格边线的宽度、cellPadding、cellSpacing
            - document.getElementById('myTable').border="10"
            - document.getElementById('myTable').cellPadding="15"
            - document.getElementById('myTable').cellSpacing="15"
        - 规定表格的外部边框
            - document.getElementById('myTable').frame="above" 仅显示上边框
            - document.getElementById('myTable').frame="below" 仅显示下边框
        - 规定表格的内部边线
            - document.getElementById('myTable').rules="rows" 仅显示行边线
            - document.getElementById('myTable').rules="cols" 仅显示列边线
        - 某一行的 InnerHTML
            - document.getElementById('myTable').rows\[0].innerHTML
        - 表格单元的InnerHTML
            - document.getElementById('myTable').rows\[0].cells\[0].innerHTML
        - 为表格创建一个标题
            - document.getElementById('myTable').createCaption().innerHTML="我的表格标题"
        - 从表格删除行
            - document.getElementById('myTable').deleteRow(td_this.parentNode.parentNode.rowIndex)
        - 向表格添加新行，然后向其添加内容
            ```javascript
            var x = document.getElementById('myTable').insertRow(0);
            var y = x.insertCell(0);
            var z = x.insertCell(1);
            y.innerHTML = "NEW CELL1";
            z.innerHTML = "NEW CELL2";
            ```
        - 更改表格单元格中的内容
        - 更改表元横跨的列数
            - document.getElementById("td1").colSpan="2";
        - 对齐行中的单元格内容
        - 垂直对齐行中的单元格内容
        - 对齐单元格中的内容
        - 垂直对齐单元格中的内容
    - form和input对象
        - 更改表单的action属性
            - document.getElementById("myForm").action = "/htmldom/index.asp"
        - 返回向服务器发送数据的HTTP方法
            - document.getElementById("myForm").method
        - 提示按钮的id、类型、禁用
            - document.getElementById("myButton").id
            - document.getElementById("myButton").type
            - document.getElementById("myButton").disabled=true
        - 选定以、不选定checkbox
            - document.getElementById("myCheck").checked = true
            - document.getElementById("myCheck").checked = false
        - Checkbox选中后将文本转换为大写
            - this.checked --> document.getElementById("fname").value.toUpperCase()
        - 使用单选按钮中的value属性
            - document.getElementById("answer").value = this.value
        - 重置表单
            - document.getElementById("myForm").reset()
        - 提交表单
            - document.getElementById("myForm").submit()
        - 验证表单
            - value验证
        - 设置和移开文本域上的焦点
            - focus blur
        - 选取文本域中的内容
            - document.getElementById("myText").select()
        - 表单中的下拉列表
            ```html
            <body>
                 <form>
                 请选择数字：<br />
                 <select id="no">
                 	<option>0</option>
                 	<option>1</option>
                 	<option>2</option>
                 </select>
                 <input type="button" onclick="moveNumbers()" value="-->"> 
                 <input type="text" id="result" size="20">
                 </form>
                 <script type="text/javascript">
                      function moveNumbers() {
                          var no = document.getElementById("no");
                          var option = no.options[no.selectedIndex].text;
                          var txt = document.getElementById("result").value;
                          txt = txt + option;
                          document.getElementById("result").value = txt;
                      }
                 </script>
            </body>
            ```
        - 当达到文本域的最大字符数时跳至下一个域
            ```html
            <body>
                 <form id="myForm">
                 <input size="3" tabindex="1" maxlength="3" onkeyup="checkLen(this,this.value)">
                 <input size="2" tabindex="2" maxlength="2" onkeyup="checkLen(this,this.value)">
                 <input size="3" tabindex="3" maxlength="3" onkeyup="checkLen(this,this.value)">
                 </form>
                 <script type="text/javascript">
                     function checkLen(x, y) {
                         if (y.length == x.maxLength) {
                            var next = x.tabIndex;
                            if (next < document.getElementById("myForm").length) {
                                document.getElementById("myForm").elements[next].focus();
                            }
                         }
                     } 
                 </script>
            </body>
            ```
        - 为若干表单域添加快捷键
    - option、select对象
        - 禁用并启用下拉列表
            - document.getElementById("mySelect").disabled = true
            - document.getElementById("mySelect").disabled = false
        - 取得包含该下拉列表的表单的id
            - document.getElementById("mySelect").form.id
        - 取得下拉列表中选项的数目
            - document.getElementById("mySelect").length
        - 更改下拉列表中的可见行数
            - document.getElementById("mySelect").size = 2
        - 选择下拉列表中的多个选项
            - document.getElementById("mySelect").multiple = true
        - 取得下拉列表中所选的选项的索引位置
            - document.getElementById("mySelect").selectedIndex
        - 更改被选选项
            - document.getElementById("orange").selected=true;
        - 从下拉列表中删除选项
            - document.getElementById("mySelect").remove(document.getElementById("mySelect").selectedIndex) 
    - frame、frameset、iframe对象
        - 可调整大小和不可调整大小的框架
        - 带有滚动条和不带有滚动条的框架
        - 更改两个框架的源
        - 跳出框架
        - 更改两个框架的源    
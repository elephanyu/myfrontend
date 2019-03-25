- ajax
    - 概念
        - Asynchronous JavaScript and XML，异步的JavaScript和XML
        - ajax通过在后台与服务器进行少量数据交换，使网页实现异步更新
    - XMLHttpRequest对象
        - 所有现代浏览器（IE7+、Firefox、Chrome、Safari以及Opera均内建XMLHttpRequest对象(IE5和IE6使用ActiveXObject)
        - 请求
             - open(method, url,async) 规定请求的类型、URL以及是否异步处理请求
                 - method 请求的类型 GET|POST
                 - url 文件在服务器上的位置
                 - async true异步 false同步
             - send(string) 将请求发送到服务器
                - string 仅用于POST请求
             - setRequestHeader(header, value) 向请求添加特定HTTP头
                - header 规定头的名称
                - value 规定头的值
        - 响应
            - responseText 获得字符串形式的响应数据
            - responseXML 获得XML形式的响应数据
        - 事件
            - onreadystatechange 存储函数(或函数名)，每当readyState属性改变时，就会调用该函数
            - readyState 存有XMLHttpRequest的状态，从0到4发生变化
                - 0 请求未初始化
                - 1 服务器连接已建立
                - 2 请求已接收
                - 3 请求处理中
                - 4 请求已完成，且响应已就绪
            - status	
                - 200 OK
                - 404 未找到页面
            ```html
            <body>
                 <form>
                 <div id="myDiv"><h2>Let AJAX change this text</h2></div>
                 <button type="button" onclick="loadXMLDoc()">通过 AJAX 改变内容</button>
                 <script type="text/javascript">
                      function loadXMLDoc() {
                          var xmlhttp;
                          if (window.XMLHttpRequest) {
                              xmlhttp = new XMLHttpRequest();
                          }
                          else {
                              xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
                          }
                          xmlhttp.onreadystatechange = function() {
                              if (xmlhttp.readyState == 4 && xmlhttp.status == 200) {
                                  document.getElementById("myDiv").innerHTML = xmlhttp.responseText;
                              }
                          };
                          xmlhttp.open("GET","/ajax/test1.txt",true);
                          xmlhttp.send();
                      }
                 </script>
            </body>
            ```
- jquery
    - 概念
        - jquery是一个javascript库，简化javascript编程
        - 包含
            - HTML元素选取
            - HTML元素操作
            - CSS操作
            - HTML事件函数
            - JavaScript特效和动画
            - HTML DOM遍历和修改
            - AJAX
            - Utilities
    - 基本使用
        - 加载
            - 服务器加载 \<script src="jquery.js">\</script>
            - cdn加载 \<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.8.0/jquery.min.js">\</script>
        - 语法
            - $(selector).action()
                - $(this).hide() 隐藏当前元素
                - $("p").hide() 隐藏所有段落（标签）
                - $(".test").hide() 隐藏所有class="test"的所有元素
                - $("#test").hide() 隐藏所有id="test"的元素
            - 文档就绪函数 $(document).ready(function(){ code; });
            - 选择器
                - 元素选择器
                    - $("p") 选取\<p>元素
                    - $("p.intro") 选取所有class="intro"的<p>元素
                    - $("p#demo") 选取所有id="demo"的<p>元素
                    - $("ul li:first")	每个\<ul>的第一个\<li>元素
                    - $("div#intro.head") id="intro"的\<div>元素中的所有class="head"元素
                - 属性选择器
                    - $("\[href]") 选取所有带有href属性的元素
                    - $("\[href='#']") 选取所有带有href值等于"#"的元素
                    - $("\[href!='#']") 选取所有带有href值不等于"#"的元素
                    - $("\[href$='.jpg']") 选取所有href值以".jpg"结尾的元素
    - jquery操作
        - 效果操作
            - 影藏、显示
                - hide(speed,callback) 
                - show(speed,callback) 
                - toggle(speed,callback)
            - 淡入、淡出
                - fadeIn(speed,callback)
                - fadeOut(speed,callback)
                - fadeToggle(speed,callback)
                - fadeTo(speed, opacity, callback) 渐变为给定的不透明度，介于0和1之间
            - 滑动
                - slideDown(speed,callback)
                - slideUp(speed,callback)
                - slideToggle(speed,callback)
            - 动画
                - $(selector).animate({params},speed,callback);
                    ```javascript
                    $("button").click(function() {
                        $("div").animate({left:'250px'}, "slow");
                    }); 
                    ```
                - 停止动画 $(selector).stop(stopAll,goToEnd);
            - 支持链式操作 chaining
                - $("#p1").css("color","red").slideUp(2000).slideDown(2000);
        - html操作
            - 获取、设置
                - text() 设置或返回所选元素的文本内容
                    - $("#test1").text();
                    - $("#test1").text("Hello world!");
                - html() 设置或返回所选元素的内容(包括HTML标记)
                - val() 设置或返回表单字段的值
                - attr("name") 设置或返回所选元素的name属性值
                    - $("#w3s").attr("href")
                    - $("#w3s").attr("href","http://www.w3school.com.cn/jquery");
            - 添加新的html
                - append() - 在被选元素的结尾插入内容
                - prepend() - 在被选元素的开头插入内容
                - after() - 在被选元素之后插入内容
                - before() - 在被选元素之前插入内容
                ```javascript
                // 直接加内容
                $("p").append("Some appended text.");
                var txt1 = "<p>Text.</p>";
                var txt2 = $("<p></p>").text("Text.");
                // 加标签
                var txt3 = document.createElement("p");
                txt3.innerHTML = "Text.";
                $("body").append(txt1,txt2,txt3);
                ```
            - 删除
                - remove() 删除被选元素(及其子元素)
                - empty() 从被选元素中删除子元素
            - 操作css
                - addClass("cname") 向被选元素添加一个或多个类
                - removeClass("cname") 从被选元素删除一个或多个类
                - toggleClass("cname") 对被选元素进行添加/删除类的切换操作
                - css("propertyname", "value") 设置或返回样式属性
            - 内容尺寸设置与获取
                - width(n)
                - height(n)
                - innerWidth(n)
                - innerHeight(n)
                - outerWidth(n)
                - outerHeight(n)
        - 遍历
            - 祖先
                - parent() 返回被选元素的直接父元素
                - parents() 返回被选元素的所有祖先元素，它一路向上直到文档的根元素(html)
                - parentsUntil() 返回介于两个给定元素之间的所有祖先元素
                    - $("span").parentsUntil("div"); 所有span元素的所有祖先，并且它是ul元素
            - 后代
                - children() 返回被选元素的所有直接子元素
                    - $("div").children();
                    - $("div").children("p.1");
                - find() 返回被选元素的所有直接子元素
                    - $("div").find("span");
            - 同胞
                - siblings() 返回被选元素的所有同胞元素
                    - $("h2").siblings();
                    - $("h2").siblings("p");
                - next() 返回被选元素的下一个同胞元素
                - nextAll() 返回被选元素的所有跟随的同胞元素
                - nextUntil() 返回介于两个给定参数之间的所有跟随的同胞元素
                    - $("h2").nextUntil("h6");
                - prev()
                - prevAll()
                - prevUntil()
            - 过滤
                - first() 返回被选元素的首个元素
                    - $("div p").first();
                - last() 返回被选元素的最后一个元素
                - eq() 返回被选元素的最后一个元素
                    - 索引从0开始
                    - $("p").eq(2);
                - filter() 不匹配这个标准的元素会被从集合中删除，匹配的元素会被返回
                    - $("p").filter(".intro");
                - not() 返回不匹配标准的所有元素，与 filter()相反
    - jquery ajax
        - $(selector).load(URL, data, callback);
            - 必需的URL参数规定您希望加载的URL
            - 可选的data参数规定与请求一同发送的查询字符串键/值对集合
            - 可选的callback参数是load()方法完成后所执行的函数名称，包含不同的参数：
                - 第一个回调参数包含调用成功时的结果内容
                - 第二个回调参数包含调用的状态
                - 第三个回调参数包含XMLHttpRequest对象
                ```javascript
                $(document).ready(function(){
                    $("button").click(function(){
                        $("#div1").load("/example/jquery/demo_test.txt",function(responseTxt,statusTxt,xhr){
                            if(statusTxt == "success")
                                alert("外部内容加载成功！");
                            else if(statusTxt == "error")
                                alert("Error: " + xhr.status + ": " + xhr.statusText);
                        });
                    });
                });
                ```
        - get
            - $.get(URL, callback);
                - 必需的URL参数规定您希望请求的URL
                - 可选的callback参数是请求成功后所执行的函数名
                    - 第一个回调参数存有被请求页面的内容
                    - 第二个回调参数存有请求的状态   
                    ```javascript
                    $(document).ready(function(){
                        $("button").click(function(){
                            $.get("/example/jquery/demo_test.asp",function(data, status){
                                alert("数据：" + data + "\n状态：" + status);
                            });
                        });
                    });
                    ```
        - post
            - $.post(URL, data, callback);
                - 必需的URL参数规定您希望请求的URL
                - 可选的data参数规定连同请求发送的数据
                - 可选的callback参数是请求成功后所执行的函数名
                    - 第一个回调参数存有被请求页面的内容
                    - 第二个回调参数存有请求的状态  
                    ```javascript
                    $(document).ready(function(){
                        $("button").click(function(){
                            $.post(
                                "/example/jquery/demo_test_post.asp", 
                                {name:"Donald Duck", city:"Duckburg"}, 
                                function(data, status) {
                                    alert("数据：" + data + "\n状态：" + status);
                            });
                        });
                    });
                    ```
    - noconflict()
        - jQuery使用$符号作为jQuery的简写
        - noConflict()方法会释放会$标识符的控制，使其它脚本可以使用它
        ```javascript
        $.noConflict();
        jQuery(document).ready(function(){
            jQuery("button").click(function(){
                jQuery("p").text("jQuery 仍在运行！");
            });
        });
        ```
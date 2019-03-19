- html 参考w3cschool教程
    - 简介
        - Hyper Text Markup Language超文本标记语言
        - 不是编程语言，而是一种标记语言
        - 使用标记标签描述网页
    - 标签（body中的）
        - 注释
            - \<!-- content fo annotation --> 
        - 标签元素
            - 在 XHTML、XML 以及未来的 HTML 版本中，不允许使用没有结束标签（闭合标签）的 HTML 元素
            - 标题 \<h1>..\<h6>
            - 段落 \<p>content\</p>
            - 链接 \<a href="url">link display content\</a>
            - 图像 \<img src="filepath" width="wid" height="hei" />
            - 换行 \<br />
            - 水平线 \<hr />
            - 表格
                - \<table>定义表
                - \<caption>定义表格标题
                - \<th>定义表格的表头
                - \<tr>定义表格的行
                - \<td>定义表格单元
                - \<thead>定义表格的页眉
                - \<tbody>定义表格的主体
                - \<tfoot>定义表格的页脚
                - \<col>定义用于表格列的属性
                - \<colgroup>定义表格列的组
                - 跨行、跨列单元格
                - 单元格边距、间距
                - 表格、单元格背景颜色、背景图像
            - 列表
                - \<ol>定义有序列表
                - \<ul>定义无序列表
                - \<li>定义列表项
                - \<dl>定义定义列表
                - \<dt>定义定义项目
                - \<dd>定义定义的描述
                - 嵌套列表
                - 定义列表
            - 表单
                - form属性
                    - action规定向何处提交表单的地址（URL）（提交页面）
                    - method规定在提交表单时所用的 HTTP 方法（默认：GET）
                    - accept-charset规定在被提交表单中使用的字符集（默认：页面字符集）
                    - autocomplete规定浏览器应该自动完成表单（默认：开启）
                    - enctype规定被提交数据的编码（默认：url-encoded）
                        - \<form action="action_page.php" method="GET" target="_blank" accept-charset="UTF-8" enctype="application/x-www-form-urlencoded" autocomplete="off" novalidate>
                    - name规定识别表单的名称（对于 DOM 使用：document.forms.name）
                    - novalidate规定浏览器不验证表单
                    - target规定 action 属性中地址的目标（默认：_self）
                    - html5新增属性
                        - autocomplete
                        - novalidate
                - 表单元素
                    - input元素
                        - text定义常规文本输入
                            - First name:\<br />\<input type="text" name="firstname">
                        - password密码输入文本
                        - radio定义单选按钮输入（选择多个选择之一）
                             - \<input type="radio" name="sex" value="male" checked>Male
                        - checkbox多选按钮
                        - submit定义提交按钮（提交表单）
                            - \<input type="submit" value="Submit">
                        - html5扩展类型
                            - 时间date|time|week|month|datetime|datetime-local
                            - 数据格式email|tel|url
                            - range
                            - search
                            - color
                            - number
                    - select元素，下拉列表
                        ```html
                        <form action="/demo/demo_form.php">
                            <select name="cars">
                                <option value="volvo">Volvo</option>
                                <option value="saab">Saab</option>
                                <option value="fiat">Fiat</option>
                                <option value="audi">Audi</option>
                            </select>
                            <br><br>
                            <input type="submit">
                        </form>>
                        ```
                    - texarea，文本框
                        - \<textarea name="message" rows="10" cols="30">content\</textarea>
                    - button，点击按钮
                        - \<button type="button" onclick="alert('Hello World!')">Click Me!\</button>
                    - html5新增datalist keygen output
                        ```html
                        <form action="action_page.php">
                        <input list="browsers">
                        <!-- 预定义input的值 -->
                        <datalist id="browsers">
                           <option value="Internet Explorer">
                           <option value="Firefox">
                           <option value="Chrome">
                           <option value="Opera">
                           <option value="Safari">
                        </datalist> 
                        </form>
                        ```
                - input属性
                    - value
                    - readonly
                    - disable
                    - size
                    - maxlength
                    - html5扩展属性
                        - autocomplete
                        - autofocus
                        - height 和 width
                        - list
                        - min 和 max
                        - multiple
                        - pattern (regexp)
                        - placeholder
                        - required
                        - step
                        - form
                        - formaction
                        - formenctype
                        - formmethod
                        - formnovalidate
                        - formtarget
            - 块
                - \<div>定义文档中的分区或节（division/section），组合其它html元素的容器
                - \<span>定义span用来组合文档中的行内元素，文本的容器
        - 标签属性
            - style可单独定义在head或者css文件中，body中的数据根据标签名、class、id按定义的格式显示
            - class 元素类名 配合div使用
            - id 元素唯一id
            - title 元素的额外内容
            - style 元素行内样式
                - 避免使用下面的标签或属性，而是在style元素内定义样式
                    - \<center>定义居中的内容
                    - \<font>和\<basefont>定义HTML字体
                    - \<s>和\<strike>定义删除线文本
                    - \<u>定义下划线文本
                    - align定义文本的对齐方式
                    - bgcolor定义背景颜色
                    - color定义文本颜色
                - style样式
                    - background-color:red 背景颜色
                    - font-family:arial;color:red;font-size:20px; 字体、颜色、尺寸
                    - text-align:center 文本对齐
        - 头部元素
            - \<head>定义关于文档的信息
            - \<title>定义文档标题
            - \<base>定义页面上所有链接的默认地址或默认目标
            - \<link>定义文档与外部资源之间的关系
                - 全局css引入 \<link href="css/bootstrap.min.css" rel="stylesheet">
            - \<meta>定义关于HTML文档的元数据
            - \<script>定义客户端脚本
                - 全局js引入 \<script src="js/jquery.min.js"></script>
            - \<style>定义文档的样式信息
    - 事件
        - window事件
            - onload 页面结束加载之后触发
            - onunload 一旦页面已下载时触发（或者浏览器窗口已被关闭）
            - html5扩展事件
        - form事件
            - onsubmit 在提交表单时触发
            - onchange 在元素值被改变时运行的脚本
            - onblur 元素失去焦点时运行的脚本
            - onfocus 当元素获得焦点时运行的脚本
            - onreset 当表单中的重置按钮被点击时触发，HTML5 中不支持
            - onselect 在元素中文本被选中后触发
            - html5扩展事件
                - onformchange 在表单改变时运行的脚本
                - onforminput 当表单获得用户输入时运行的脚本
                - oninput 当元素获得用户输入时运行的脚本
                - oninvalid 当元素无效时运行的脚本
        - keyboard事件
            - onkeydown 在用户按下按键时触发
            - onkeypress 在用户敲击按钮时触发
            - onkeyup 当用户释放按键时触发
        - mouse事件
            - onclick 元素上发生鼠标点击时触发
            - ondblclick 元素上发生鼠标双击时触发
            - onmousedown 当元素上按下鼠标按钮时触发
            - onmousemove 当鼠标指针移动到元素上时触发
            - onmouseout 当鼠标指针移出元素时触发
            - onmouseover 当鼠标指针移动到元素上时触发
            - onmouseup 当在元素上释放鼠标按钮时触发
            - html5扩展事件
                - onmousewheel 当鼠标滚轮正在被滚动时运行的脚本
                - onscroll 当元素滚动条被滚动时运行的脚本
                - ondrag 元素被拖动时运行的脚本
                - ondragend 在拖动操作末端运行的脚本
                - ondragenter 当元素元素已被拖动到有效拖放区域时运行的脚本
                - ondragleave 当元素离开有效拖放目标时运行的脚本
                - ondragover 当元素在有效拖放目标上正在被拖动时运行的脚本
                - ondragstart 在拖动操作开端运行的脚本
                - ondrop 当被拖元素正在被拖放时运行的脚本
        - media事件
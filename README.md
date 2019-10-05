心得体会
 		首先，我想说说我在这个寒假的生活与学习的经历。
可能是我个人的兴趣问题，我对编程比较感兴趣，也知道只有先人一步才能更好更快的掌握更多的知识。在这个寒假，我把所有休息的时间都用在学习新的编程知识上，所以今年的这个暑假，就没有去外地旅游了。不过这个寒假过得相当的充实，毕竟学会了如此之多的新知识，也是一件极其高兴的事情。
其次，我想说说我在寒假学习中所掌握的相关知识。
寒假期间，我重新学习了一下前端编程所需的一些代码，以便在本次的期末作业中能够用的上，主要语法有下面这些：
Html相关标签的运用:<a href=””>、<input type=””value=””name=””>
Javascript语法:function(){}、setInterval（）、clearInterval(time)、getElenmentByID（）、createTextNode(String x)、appendChild(节点);等等
JQuery语法：$("#province").change(function(){})
Validate插件及语法：$("#checkForm").validate({
rules:{ }
messages：{ }
} 
它相关属性值主要是对表单的一些常用规范，								  required  //是否为空
minlength  //最小长度
digits     //是否为数字类型
equalTo:"[name='password']" //确认密码填写
email //邮箱格式规范
BootStrap前端框架：由于内容过多，在这里我大概讲述一下。BootStrap是基于HTML、CSS、Javascript的半成品框架，主要用于设计页面，让页面显得更加的好看。实际上是JQuery的一个插件。

在学习网页端的javaweb编程前，我学习了以下相关知识：
Http协议和Tomcat服务器的相关语法：
常见请求头	描述 （红色掌握，其他了解）
Referer	浏览器通知服务器，当前请求来自何处。如果是直接访问，则不会有这个头。常用于：防盗链
If-Modified-Since	浏览器通知服务器，本地缓存的最后变更时间。与另一个响应头组合控制浏览器页面的缓存。
Cookie	与会话有关技术，用于存放浏览器缓存的cookie信息。
User-Agent	浏览器通知服务器，客户端浏览器与操作系统相关信息
Connection	保持连接状态。Keep-Alive 连接中，close 已关闭
Host	请求的服务器主机名
Content-Length	请求体的长度
Content-Type	如果是POST请求，会有这个头，默认值为application/x-www-form-urlencoded，表示请求体内容使用url编码
Accept：	浏览器可支持的MIME类型。文件类型的一种描述方式。
MIME格式：大类型/小类型[;参数]
例如：
text/html ，html文件
text/css，css文件
text/javascript，js文件
image/*，所有图片文件
Accept-Encoding	浏览器通知服务器，浏览器支持的数据压缩格式。如：GZIP压缩
Accept-Language	浏览器通知服务器，浏览器支持的语言。各国语言（国际化i18n）

JavaWeb核心之Servlet的相关语法：
获得ServletContext对象：
ServletContext servletContext = config.getServletContext();
ServletContext servletContext = this.getServletContext();
获得web应用中任何资源的绝对路径：
String path = context.getRealPath(相对于该web应用的相对地址);
域对象的通用的方法：
setAtrribute(String name,Object obj);
getAttribute(String name);
removeAttribute(String name);

HttpServletResponse的相关语法：
通过response设置响应行
设置响应行的状态码
setStatus(int sc)
通过response设置响应头
addHeader(String name, String value) 
addIntHeader(String name, int value) 
addDateHeader(String name, long date) 
setHeader(String name, String value) 
setDateHeader(String name, long date) 
setIntHeader(String name, int value)

通过response设置响应体:
（1）响应体设置文本
PrintWriter getWriter()
关于设置中文的乱码问题
response的setCharacterEncoding(String charset) 设置response的编码
通过response的setContentType(String type)方法指定页面解析时的编码是UTF-8
response.setContentType("text/html;charset=UTF-8");
(2)响应头设置字节
ServletOutputStream  getOutputStream()

HttpServletRequest的相关代码：
request获得行的内容
	request.getMethod()
	request.getRequestURI()
	request.getRequestURL()
	request.getContextPath()
	request.getRemoteAddr()
request获得头的内容
	request.getHeader(name)
request获得体（请求参数）
	String request.getParameter(name)
	Map<String,String[]> request.getParameterMap();
	String[] request.getParameterValues(name);
	注意：客户端发送的参数 到服务器端都是字符串

	获得中文乱码的解决：
		post:request.setCharacterEncoding(“UTF-8”);
		get:
parameter = new String(parameter.getBytes(“iso8859-1”),”UTF-8”);

request转发和域
	request.getRequestDispatcher(转发的地址).forward(req,resp);
	request.setAttribute(name,value)
	request.getAttribute(name)

会话技术Cookie&Session的相关语法：
会话技术：
Cookie技术：存到客户端
发送cookie
Cookie cookie = new Cookie(name,value)
cookie.setMaxAge(秒)
cookie.setPath()
response.addCookie(cookie)
获得cookie
Cookie[] cookies = request.getCookies();
cookie.getName();
cookie.getValue();
Session技术：存到服务器端 借助cookie存储JSESSIONID
HttpSession session = request.getSession();
setAttribute(name,value);
getAttribute(name);
session生命周期
创建：第一次指定request.getSession();
销毁：服务器关闭、session失效/过期、手动session.invalidate();
session作用范围：默认一会话中

动态页面技术（JSP/EL/JSTL）：
jsp指令（3个）
1）page指令
language：jsp脚本中可以嵌入的语言种类
pageEncoding：当前jsp文件的本身编码---内部可以包含contentType
contentType：response.setContentType(text/html;charset=UTF-8)
session：是否jsp在翻译时自动创建session
import：导入java的包
errorPage：当当前页面出错后跳转到哪个页面
isErrorPage：当前页面是一个处理错误的页面
2）include指令
<%@ include file="被包含的文件地址"%>
3）taglib指令
<%@ taglib uri="标签库地址" prefix="前缀"%>

jsp内置/隐式对象：
名称	类型	描述
out	javax.servlet.jsp.JspWriter	用于页面输出
request	javax.servlet.http.HttpServletRequest	得到用户请求信息，
response	javax.servlet.http.HttpServletResponse	服务器向客户端的回应信息
config	javax.servlet.ServletConfig	服务器配置，可以取得初始化参数
session	javax.servlet.http.HttpSession	用来保存用户的信息
application	javax.servlet.ServletContext	所有用户的共享信息
page	java.lang.Object	指当前页面转换后的Servlet类的实例
pageContext	javax.servlet.jsp.PageContext	JSP的页面容器
exception	java.lang.Throwable	表示JSP页面所发生的异常，在错误页中才起作用

1.out对象
2.pageContext对象
jsp页面的上下文对象，作用如下：
page对象与pageContext对象不是一回事
1）pageContext是一个域对象
setAttribute(String name,Object obj)
getAttribute(String name)
removeAttrbute(String name)

pageContext可以向指定的其他域中存取数据
setAttribute(String name,Object obj,int scope)
getAttribute(String name,int scope)
removeAttrbute(String name,int scope)
findAttribute(String name)
2）可以获得其他8大隐式对象
例如： pageContext.getRequest()
pageContext.getSession()

5．jsp标签（动作）
1）页面包含（动态包含）：<jsp:include page="被包含的页面"/>
2）请求转发：<jsp:forward page="要转发的资源" />

EL技术
1．EL从域中取出数据
EL最主要的作用是获得四大域中的数据，格式${EL表达式}
EL获得pageContext域中的值：$(pageContextScope.key);
EL获得request域中的值：$(request.key);
EL获得session域中的值：$(session.key);
EL获得application域中的值：$(application.key);
EL从四个域中获得某个值$(key);
2．EL的内置对象
pageScope,requestScope,sessionScope,applicationScope
 ---- 获取JSP中域中的数据
param,paramValues 	- 接收参数.
header,headerValues	- 获取请求头信息
initParam		- 获取全局初始化参数
cookie			- WEB开发中cookie
pageContext		- WEB开发中的pageContext.
$(pageContext.request.contextPath)
相当于
<%=pageContext.getRequest().getContextPath%>
获得WEB应用的名称

JSTL概述
标签库	标签库的URI	前缀
Core 	http://java.sun.com/jsp/jstl/core	c
I18N	http://java.sun.com/jsp/jstl/fmt	fmt
SQL	http://java.sun.com/jsp/jstl/sql	sql
XML	http://java.sun.com/jsp/jstl/xml	x
Functions	http://java.sun.com/jsp/jstl/functions	fn

之后，我想谈谈我对这次开发的一些感想和启发。
这个商品管理系统虽然看起来是比较的简单，但是这里面涉及到的知识，也是很多的。在做的过程中，还是要重复的翻阅各种资料，百度了无数遍，虽然说在各方面做得还是有很多不足的地方，但是确是我认真作出来的一个作品。在页面方面，收集了一些做网页用的图片和数据库表资料，包括商品手机电脑的图片。在整个页面的编写过程中，最难的点还是要属jsp页面，里面的el代码还有属性值的获取都要花费我大量的时间去想。有的时候很多天都弄不出来，在我看来编程的思想不是一两天就能培养起来的。不过，在通过不断的努力过后总会有一些新的发现，突然之间就会想到该用什么学过的知识比较好，当然还是要不断的翻看文档资料，掌握API方法运用的技巧。在API技巧运用方面，自我感觉还是十分的菜，有时候想到了步骤是怎样的，但是一谈到实践的话，就一点头绪没有。所以还是要通过不断的参考和借鉴别人的方法来实现。总而言之，现阶段还是处于努力学习的阶段，不断更新自己的编程知识，掌握方法运用的技巧，最重要的是要学会在什么地方用什么方法最合理有效！
最后，我想定一下下学期的一些目标和下学期的执行方案。
下学期，我想让自己的编程水平达到一个新的高度，希望能够熟练的掌握简单程序的编写，尝试的去做一些项目，当然如果有比赛的话，我也希望能够以参赛者的身份出现在赛场上。
执行方案：
1.通过自学翻阅有关JAVA书本的方式，掌握更加合理的编程。
2.通过团队的形式，以合作的方式提高自己的编程水平，学习团队里面一些同学的编程思想。
3.尝试着去开发一些小项目，熟练的掌握java中的方法，懂得查看API文档。
4.提高自己的专业英语水平，毕竟在java中，还是有很多的专有名词的意思还是比较深的。

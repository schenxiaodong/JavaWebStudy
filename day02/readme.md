# JSP 使用报Duplicate local variable path 错误 解决方法

错误提示:

`Multiple annotations found at this line:`<br />
  `- Duplicate local variable path`<br />
  `- Duplicate local variable`<br />
  `basePath`<br />

重复变量,

因为`<%@include%>`引进的是代码,把代码包含进来,而新进JSP时,会默认生成

`<%`<br />
`String path = request.getContextPath();`<br />
`String basePath = request.getScheme()+"://"+request.getServerName()+":"+request.getServerPort()+path+"/";`<br />
`%>`<br />
`
    <base href="<%=basePath%>">`<br />
这二句代码,所以用`<%@include%>`引进页面是就报重复变量 `basePath`

解决方法,把要引进页面这句去掉就行,

建议页面无逻辑代码可用<jsp:include/>这个引入的是结果,就是引进页面编译后的结果,适用于纯html页面
————————————————<br />
版权声明：本文为CSDN博主「葉A子」的原创文章，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处链接及本声明。<br />
原文链接：https://blog.csdn.net/t35807754/article/details/7894172

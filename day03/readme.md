# 踩坑

1.`xxx cannot be resolved to a type`<br /> 
2.`org.apache.catalina.core.StandardWrapperValve invoke`<br />
`  严重: Servlet.service() for servlet [jsp] in context with path [/Test] threw exception [org.apache.jasper.JasperException: java.lang.ClassNotFoundException: org.apache.jsp.BeanTest.usebean_jsp] with root cause
java.lang.ClassNotFoundException: org.apache.jsp.BeanTest.usebean_jsp`<br />
这是因为在程序中写的Java文件放在了default包.<br />解决方法：重新创建一个包，将Java文件导入新包中，并修改相应代码

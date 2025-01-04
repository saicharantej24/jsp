# jsp
jsp
index.html:
<!DOCTYPE html>
<html>

<body>

<form action="add.jsp">
Enter num1:<input type="text" name="num1"><br>
Enter num2:<input type="text" name="num2"><br>
<input type="submit">


</form>
</body> 
</html> 
-----------------------
add.jsp:
<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="ISO-8859-1">
<title>Insert title here</title>
</head>
<body bgcolor="cyan">
<% 
    int i=Integer.parseInt(request.getParameter("num1"));
    int j=Integer.parseInt(request.getParameter("num2"));
    int k=i+j;
    out.println("output is:"+k);
    %>
</body>
</html>
-------------------------------------------------------over------------------------------------------------
Tags:
  1)scriplet tag
<%
%>

2)Directive tag
<% @page import="java.util.*;"%>

3)declaration tag:
<% !   %>
to declare variables

4)Expression tag:
<%=  %>
ex: <%= k   %>--------------------out.print(k);
-------------------------------------------**************************--------------------------------------
**JSP DIRECTIVES:**
1) @page
   ex:
   <%@page attribute="value" attribute="value"...........%>
   some exapmples:
   language="scripting language"
   extends="className"
   import="importList"
   session="true/false"
   autoFlush="true/false"
   contentType="ctinfo"
   errorPage="true/false"
   isErrorPage="true/false"
   info="information"
   isELIgnored="true/false"
   isThreadSafe="true/false"
2) @include
    <%@include file="file name"  %>
   <%@include  file="add.jsp"%>
3)@taglib
<%@ taglib uri="uri" prefix="fx"  %>
//<fx:h1>
--------------------------******************************************_-------------------------------------------
   **IMPPLICIT OBJECTS IN JSP:**
Builtin Objects --can be used in scriplet and expression:
   useful 7:

   request--------HttpServletRequest
   response-------HttpServletResponse
   pageContext-------pageContext
   out(JspWriter)--------------PrintWriter  object
   session-------------HttpSession
   application---------ServletContext
   config---------------ServletConfig
----------------------------------------**************************_--------------------------------------
 **  Exception handling in jsp:**

home.jsp:
<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1" errorPage="error.jsp" %>
<!DOCTYPE html>
<html>
<head>
<meta charset="ISO-8859-1">
<title>Insert title here</title>
</head>
<body>
   
  <%
           int k=4/0;
  %>
</body>
</html>
--------
error.jsp:
<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1" isErrorPage="true"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="ISO-8859-1">
<title>Insert title here</title>
</head>
<body bgcolor="red">
Error
<%= exception.getMessage() %>
</body>
</html>
output:
Error / by zero
---------------------------------------------

   
   

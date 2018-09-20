# ServletLifeCycle

* It is in javax.Servlet;
* Servlet is java interface
* Servlet, resides on server, execute on server, gives output on client machine
```java
	public interface Servlet {
	public void init(ServletConfig config) throws ServletException;
	public void service(ServletRequest req, ServletResponse res) throws ServletException, IOException;
	public void destroy();
}
```
* HttpServlet, GenericServlet are popular Implementation classes
* Servlet Life Cycle
  - three main phases - construction, service and destroy.
    - Construction: 1.Loads the servlet class, 2. Creates servlet instance, 3. calling init() method
    - Service: Invokes the service method.
    - Destroy: If the container needs to remove the servlet, it finalizes servlet by calling servlet's destroy method
* Servlet Example, Reference: https://www.youtube.com/watch?v=WbyXPH5Obu4
* HttpServlet Example, Reference: https://www.youtube.com/watch?v=01mgc2rrr_o
  - HttpServlet has two major methods
    - doPost(req,res): for post request
    - doGet(req,res): for get request


## Cntext Path
* the context path is the portion of the request URL that indicates the context of the request.
* Where to find peoperties, file, image, css and all
* request.getContextPath()- return root path of your application
* while / returns parent directory of a file.
* It is always recommended to use context path instead hard-coding your context path
```jsp
	<%= request.getContextPath() %>
	<a href="${pageContext.request.contextPath}/info/page.html">
```

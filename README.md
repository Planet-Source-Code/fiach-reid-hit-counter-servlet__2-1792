﻿<div align="center">

## Hit counter Servlet


</div>

### Description

This Servlet runs along side a Java-compatible Server, to provide a simple Hit counter, This technology can be demonstrated at www.eej.ulst.ac.uk/remote-viewer
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Fiach Reid](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/fiach-reid.md)
**Level**          |Advanced
**User Rating**    |4.3 (17 globes from 4 users)
**Compatibility**  |Java \(JDK 1\.1\)
**Category**       |[Internet/ Browsers/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-browsers-html__2-68.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/fiach-reid-hit-counter-servlet__2-1792/archive/master.zip)





### Source Code

```
import java.servlet.*;
import java.io.*;
import java.util.Hashtable;
import java.util.Date;
/**
 * Counter Servlet
 *
 * This simple servlet uses server-side includes
 * to embed a hit counter in a page.
 * @author Fiach@eircom.net
 * @Demo at www.eej.ulst.ac.uk/remote-viewer
 * @version 1.2, 3/22/96
 */
public class CounterServlet extends GenericServlet {
 static int count = 0;
 static Date start = new Date();
 public void service(ServletRequest request, ServletResponse response)
  throws ServletException, IOException {
  int temp;
  response.setContentType("text/plain");
  PrintStream ps = new PrintStream(response.getOutputStream());
  synchronized (this) {
   temp = count++;
  }
  ps.println("This servlet has been accessed " + temp + " times since "
   + start );
 }
}
```


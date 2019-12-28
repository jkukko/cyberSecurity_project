<H1> Cyber Security Base - Project 1 </H1>

<H2> A6: Broken Access Control </H2>

Typically this issue is releted to users access control, user has access to intended areas. Here users can access to H2 database via web browser.

<H3> Steps to reproduce: </H3>
<li> Run code in Netbeans </li>
<li> Open browser and go to page http://localhost:8080/h2-console </li>

<H3> Fix: </H3>
Changes security configuration.
For example: we could only allow people with admin role to use H2 console: 
.antMatchers("/h2-console/*").hasRole("ADMIN")

<H2> A9: Using Components with Known Vulnerabilities </H2>

Application uses old version of Spring Framework. This issue is additionally releted to A6 security misconfiguration.

<H3> Steps to reproduce: </H3>
Open pom.xml file from current project
You can see from the list that application uses spring framework 1.4.2

<H3> Fix: </H3>
Use latest version of Spring framework
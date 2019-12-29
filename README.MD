<H1> Cyber Security Base - Project 1 </H1>
Project for the Cyber security base -course. Contains intentional security flaws.
To check these flaws, download code from github. Test user is 'Ted' and password is 'Test'

<H3> A3: Sensitive Data Exposure </H3>
In a case of sensitive data exposure, attacker might not directly attack the systme. 
They might steal keys or execute man-in-the-middle attack or somehow steal data from database. 
The key here is that data is stored not in protect way. 
The first thing is to make sure that sensitive data is not stored in clear way. 
In my application participants credit card number is stored as a clear data.

<H3> Steps to reproduce: </H3>
<li> Open contorller and domain code in Netbeans </li>
<li> You can see that all the information is stored a clear text to database </li>

<H3> Fix: </H3>
<li> use hashing and hash credit card numbers </li>

<H2> A5: Broken Access Control </H2>

Typically this issue is releted to users access control, user has access to intended areas. 
Here users can access to H2 database via web browser.

<H3> Steps to reproduce: </H3>
<li> Run code in Netbeans </li>
<li> Open browser and go to page http://localhost:8080/h2-console </li>

<H3> Fix: </H3>
<li> Changes security configuration.</li>
<li> For example: we could only allow people with admin role to use H2 console: .antMatchers("/h2-console/*").hasRole("ADMIN") </li>

<H2> H6: Security Misconfiguration </H2>
With modern systems it is almost impossible to keep system intact and properly configurated. 
Due to the fact that modern application / systems consist of several modules, applications and building blocks. 
In this application, I have disabled HTTP header and CSRF. As a default, these protections are in use.

<H3> Steps to reproduce: </H3>
<li> Open securityConfifuration in Netbeans </li>
<li> You can see that http.header().disable() and http.csrf().disable code </li>

<H3> Fix: </H3>
<li> Remove http.header().disable() and http.csrf().disable code </li>


<H2> A9: Using Components with Known Vulnerabilities </H2>

Application uses old version of Spring Framework. 
This issue is additionally releted to A6 security misconfiguration.

<H3> Steps to reproduce: </H3>
<li> Open pom.xml file from current project </li>
<li> You can see from the list that application uses spring framework 1.4.2 </li>

<H3> Fix: </H3>
<li> Update spring framework to latest </li>

<H2> A10: Insufficien Logging & Monitoring </H2>

Insufficien logging and monitoring are one of the key reasons that attackers can achienve their goals without being detected. According to owasp list it took in average 196 days before a breach was identifyed.

<H3> Steps to reproduce: </H3>
<li> This application does not have any logging or monitoring </li>

<H3> Fix: </H3>
<li> Add/active logging and monitoring </li>

Use latest version of Spring framework
# Getting started - Advanced WAF
## Make the app work first
Add the node (the web server)
![waf1](/waf/img/waf1.png)

Create the pool (pool of web server)
![waf2](/waf/img/waf2.png)

Make sure the health monitor works, the pool is up
![waf3](/waf/img/waf3.png)

Create the virtual server (to receive traffic from clients)
![waf4](/waf/img/waf4.png)

Source Address Translation = 'Auto Map'
Default Pool = 'word_press_server_pool'
![waf5](/waf/img/waf5.png)

Make sure the virtual server is up and ready to serve clients
![waf6](/waf/img/waf6.png)

See the statistics
![waf7](/waf/img/waf7.png)
![waf8](/waf/img/waf8.png)

Testing the website served by the WAF instance
![waf9](/waf/img/waf9.png)
Check the statistics
![waf10](/waf/img/waf10.png)

## Create an Web Application Firewall Policy
Overview
![waf14](/waf/img/waf14.png)

Create the log profile
![waf15](/waf/img/waf15.png)
![waf16](/waf/img/waf16.png)

Create the policy
![waf11](/waf/img/waf11.png)
![waf12](/waf/img/waf12.png)
![waf17](/waf/img/waf17.png)
![waf18](/waf/img/waf18.png)
![waf19](/waf/img/waf19.png)

Event Logs
![waf20](/waf/img/waf20.png)
![waf21](/waf/img/waf21.png)

Trying some funny things
![waf22](/waf/img/waf22.png)
![waf23](/waf/img/waf23.png)

Check the Event Logs again
![waf24](/waf/img/waf24.png)

See the detail
![waf25](/waf/img/waf25.png)
![waf26](/waf/img/waf26.png)

Checkout more advance stuff

![waf27](/waf/img/waf27.png)
![waf28](/waf/img/waf28.png)

<br>Congratulation! and do not forget to check out <a href='https://support.f5.com/csp/home'>F5 Networks official support page</a>

# install IIS
---------------------------------------

1. Open Server Manager  
<img src="../img/00.png" alt="" title="">
2. Click the “Add roles and features” text.  
<img src="../img/10.png" alt="" title="" width="700">
3. On the “Before you begin” window, click the Next button.
<img src="../img/20.png" alt="" title="" width="700">
4. On the "Select installation type" window, leave “Role-based or feature-based installation” selected and click Next.
<img src="../img/30.png" alt="" title="" width="700">
5. As we're installing to our local machine, leave “Select a server from the server pool” with the current machine selected and click Next.  
<img src="../img/40.png" alt="" title="" width="700">
6. From the "Select server roles" window, check the box next to “Web Server (IIS)”.   
   When additional features and feature wizard window pop up, click the “Add Features” button.  
   Click Next after back to "Select server roles" window
<img src="../img/50.png" alt="" title="" width="700">
7. In the "features" window, Click ".NET framework 4.6 features",  check  "ASP.NET 4.6" and  "WCF Services" - "HTTP activation".  
   When additional features and feature wizard window pop up, click the “Add Features” button.   
   Click Next after back to "features" window
<img src="../img/70.png" alt="" title="" width="700">
8. Click Next on the “Web Server Role (IIS)” window.
<img src="../img/90.png" alt="" title="" width="700">
9. In the "Select role services" window, Check "ASP.NET 4.6" under "application development" . Click Next.
<img src="../img/100.png" alt="" title="" width="700">
10. Finally on the “Confirm installation selections” window , review the items that are to be installed and click Install.
<img src="../img/110.png" alt="" title="" width="700">
11. Once the installation has succeeded, click the close button.
<img src="../img/130.png" alt="" title="" width="700">
12. We can perform test by opening up a web browser and browsing to the server that we have installed IIS on. You should see the default IIS page.
<img src="../img/iis.png" alt="" title="" width="700">

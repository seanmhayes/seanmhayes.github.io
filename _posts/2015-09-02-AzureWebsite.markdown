---
layout: post
title:  "Creating a Website with Microsoft Azure"
date:   2015-09-02 15:20:00
categories: website
---
As a student I have a Microsoft [Dreamspark](https://www.dreamspark.com/) membership, which has various benefits associated with it. One of these is the ability to develop a web app in a free copy of Visual Studio Community 2015, and publish it to Microsoft's [Azure](https://azure.microsoft.com/en-us/) cloud service, all completely free.

I created a very basic website by following a tutorial on [MSDN](http://blogs.msdn.com/b/microsoft_student_developer_blog/archive/2015/07/20/welcome-to-visual-studio-2015-with-azure.aspx). Over time I hope to get this website displaying data from my MySQL server.

I then created a Wordpress website by following another tutorial on [MSDN](http://blogs.msdn.com/b/microsoft_student_developer_blog/archive/2015/08/11/creating-a-wordpress-website-with-azure.aspx).

The websites I created are hosted on Azure at [indoptim.azurewebsites.net](http://indoptim.azurewebsites.net) and [indoptimblog.azurewebsites.net/](http://indoptimblog.azurewebsites.net/). I would have liked to link subdomains of my indoptim.ie domain to these addresses using CNAME records. I could not do this as Azure does not allow custom domains to be used when on a Free plan, and I can not afford to upgrade my Azure subscription.

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help

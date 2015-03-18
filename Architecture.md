# Introduction #
This page shows the different architectures of the dynamokos application across the blog posts.


# Post 1 : Distributed OSGi applications with Apache CXF DOSGi #
![http://dynamokos.googlecode.com/svn/resources/architecture-p1.png](http://dynamokos.googlecode.com/svn/resources/architecture-p1.png)

The first post just relies on Distributed Services (Apache CXF Distributed OSGi). the oracle is exported using SOAP (Web Service).The client **KNOWS** the oracle location, and uses it (also using DOSGi).

However, this does not handle the dynamism and does not check the accessibility of the oracle. So, if you don't start the oracle, the client will still be ok, the `Prediction` service will still be provided! The only issue is that the web client will not work correctly as the service in **NOT** there.

# Post 2 : Introducing Dynamic Discovery #
![http://dynamokos.googlecode.com/svn/resources/architecture-p2.png](http://dynamokos.googlecode.com/svn/resources/architecture-p2.png)

Thie second post add dynamic discovery. This avoid the client to know the location of the oracle, and thie introduce a little bit of dynamism in the application. The used discovery protocol is Apache Hadoop Zookeeper.
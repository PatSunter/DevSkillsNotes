

General notes on Tomcat installation
====================================

See http://tomcat.apache.org/tomcat-6.0-doc/appdev/deployment.html

WAR = "Web Application Archive"

Essentially a compressed version of the applications files that run in a "servlet container"

'Document root' is base level of this, needs to contain top-level HTML files etc.

Suggested layout for WAR:
 * \*.html, \*.jsp, etc
 * /WEB-INF/web.xml (Web Application Deployment Descriptor) for app  
   (Configuration, describes a servlet, etc)
 * /WEB-INF/classes :- any needed Java class files for the App that
   haven't been combined into Java JARs 
 * /WEB-INF/lib :- JAR files used by the app and associated resources

So 'Deployment' essentiall involves:
 * Copying the 'war' file into a Tomcat live server directory
   (E.g. /var/lib/tomcat6/webapps/ncWMS.war)
 * Updating a catalog of installed apps?

Actual deployment
-----------------

 * Copy the app's Distro tree as a subdir of $CATALINA_BASE/webapps
   (Named correctly for app)
 * Copy the application .war into $CATALINA_BASE/webapps
   (Note to update later, need to overwrite both this .war, and uncompressed
    dir that Tomcat creates)
 * Or can use the Tomcat "Manager" application to do this.
 * Or use "manager" tasks in Ant build script
 * Use a "tomcat deployer" packaged tool.

Qtns for RSA as a result
------------------------

Should we be actually installing some shared libs to $CATALINA_HOME/lib?
 * That way stuff doesn't have to be reinstalled individually for all
   RSA Apps, ncWMS, etc.

Hello JavaFX and Maven (Example Project)
=========================================

*NOTE: I plan to turn this example project into a Maven archetype soon. This project will be obsolete once that happens.*

This is a simple "Hello World" example showing a ready to roll JavaFX project using the 
<a href="https://github.com/zonski/javafx-maven-plugin">ZenJava JavaFX Maven plugin</a>. This can be downloaded 
and used as a starter template for your own Maven JavaFX projects.

The demonstration project includes a single module Maven project with example POM and source code. The POM is 
configured to build both an executable JAR, a webstart bundle and a native installer (MSI, EXE, RPM, DMG) for your platform. 

To demonstrate some Maven practices and benefits, the source code also includes a simple FXML example, style sheets, 
images, and makes use of some third-party dependencies (such as Log4J, MigPane Layout, and Apache Commons). These 
are all optional additions and included just to get you started. You can delete these references and add your own 
as needed. 


Setting up
=========================================

Please refer to the 'Before you start' section of the JavaFX Maven Plugin documentation: 

* https://github.com/zonski/javafx-maven-plugin/wiki


Get the Example Code
=========================================

Download a ZIP of the source code (hit the "ZIP" button above) and extract anywhere on your local directory.


Build the Project 
=========================================

Use the jfx:package command to build your project. Note that Maven will download a lot of third-party dependencies the first time it runs (meaning you don't have to). The first
run can be slow but subsequent runs will be much faster. If you are new to Maven, see 
http://maven.apache.org/guides/getting-started/maven-in-five-minutes.html

```
    mvn clean compile jfx:package
```

This will be quite slow (e.g. 30 seconds) as it is building the native co-bundled apps into an installer including all 
third-party JARs.

Once this command completes successfully you will find an executable JAR at: 

```
    {project.home}/target/my-example-app.jar
```

This JAR contains your complete application in one bundle and can be distributed directly, on its own (i.e. this one file
can be copied to any machine that has Java installed and can then be double clicked to run your app).

A webstart bundle will have been assembled in: 
```
    {project.home}/target/webstart
```

Additionally a native bundle will have been assembled in: 

```
    {project.home}/target/bundles
```

The exact format of the native bundle will depend on the OS you ran your build on i.e. if you built on Windows an MSI
will have been created, if you built on Mac a RPM should be there). These bundles can be distributed as normal for that
platform. 

Note: currently it is not possible to build installers for other platforms than your current one so you have to run this
build once on each platform you are targeting. This is a limitation of the JavaFX packaging tools and is not specific 
to this Maven plugin (i.e. complain to the JavaFX guys, not me). 


Make your own changes 
=========================================

To edit the source code you can just open the POM file (i.e. pom.xml) in the base directory of the project in most
popular IDEs. IntelliJ supports the POM file out of the box. In Eclipse there is good support for Maven but you may
have to install the plugin (I'm not sure). I believe NetBeans has some Maven support but I've never used it.

This example project is provided as an example and as a base template for your own Maven and JavaFX projects. You are
free to take the example project and change it as much as you like. You can delete everything that is there and start
from scratch, or you can add to what's there. 

You definitely should: 

* Change the groupId in the pom.xml to use com.yourcompany instead of com.zenjava
* Change the artifactId in the pom.xml to be your-project-name instead of hello-jfx-maven-example
* Change the base package being use for the Java files to be com.yourcompany instead of com.zenjava
* Change the keystore used to be one that matches your company

If you don't have a company name, use a nickname or working name for yourself, e.g. com.yourname.


Problems and Support
=========================================

This example project is distributed as is with no warranty or promise of support. If you have problems your best 
bet is to probably post on the OTN JavaFX Forum. You can try raising an issue here and I *may* respond but there is
no guarantee. 

Do NOT email me directly with problems on this example code. You'll go to the spambox.


Licence
=========================================

This example project is distributed under the <a href="http://en.wikipedia.org/wiki/WTFPL">WTFPL</a> licence. 




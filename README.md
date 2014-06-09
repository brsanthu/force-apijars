Overivew
=============
Salesforce Force.com team has been kind enough develop WSC [https://github.com/forcedotcom/wsc] which compiles
the Salesforce wsdls into easy to use Java wrapper. They also been pushing the various wsc compiled
Jars for various APIs like Apex, Metadata etc.

Some times they are slow to push those wsc compiled binaries and that can hamper the development if you are looking
to tryout new features.

This project aims to publish those wsc compiled jars as soon as they become available. Also, users can clone the project
to compile them locally and insta-ll the enterprise jars.

Add one or more of followint dependencies.
```xml
<dependency>
	<groupId>com.brsanthu</groupId>
	<artifactId>force-metadata</artifactId>
	<version>30.0.0</version>
</dependency>

<dependency>
	<groupId>com.brsanthu</groupId>
	<artifactId>force-partner</artifactId>
	<version>30.0.0</version>
</dependency>

<dependency>
	<groupId>com.brsanthu</groupId>
	<artifactId>force-apex</artifactId>
	<version>30.0.0</version>
</dependency>

<dependency>
	<groupId>com.brsanthu</groupId>
	<artifactId>force-tooling</artifactId>
	<version>30.0.0</version>
</dependency>
```

Enterprise Jars
=================
As Enterprise Wsdl contains your org specific custom objects/fields, open source project cannot provide a wsc compiled artifact. However, there is a template setup in this project, which you can use to generate the jar file. Follow these instructions.

* Clone this project into your local system
* Goto ```force-enterprise``` folder
* Download your org's enterprise wsdl
	* Goto ```Setup -> Develop > API``` and click on ```Generate Enterprise WSDL```
* Save the enterprise wsdl as ```/src/main/wsdls/force-enterprise-<version>.wsdl```
* Change the version in pom.xml to whatever version you looking to build
* Execute ```mvn clean install``` which should compile the wsdl into ```force-enterprise-<version>.jar``` and deploy into your local Maven repository
* Add following dependency to your pom.xml to use the artifact
```
<dependency>
	<groupId>com.brsanthu</groupId>
	<artifactId>force-enterprise</artifactId>
	<version>version</version>
</dependency>
```

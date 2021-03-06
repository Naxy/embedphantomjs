embedphantomjs
==============

Embedded PhantomJS for Java

This project provides an easy interface for execute PhantomJS with Java.

## Why?

- Easy way to execute JS inside Java
- Easy way to make a Scraper with Java

### Maven

Stable [OSS Sonatype](https://oss.sonatype.org/content/repositories/releases/com/github/jarlakxen/embedphantomjs/maven-metadata.xml)

```xml
	<dependency>
		<groupId>com.github.jarlakxen</groupId>
		<artifactId>embedphantomjs</artifactId>
		<version>3.0</version>
	</dependency>
```
### Changelog

- 3.0
    - Move to Java 8
    - Remove Guava dependancy, switch to `CompletableFuture`

- 2.9
    - https://github.com/Jarlakxen/embedphantomjs/pull/3
    - Update dependancies
    - Sopport for versions last versions of PhantomJS
    - Move PhantomJS download url to bitbucket.

- 2.8
    - Better windows support ( Thanks to @Dmitry-Shweikus )

- 2.7
    - Unify Sync and Async interfaces for PhantomJSFileExecutor
    - Improve error handling

- 2.6
    - Some API improvments in PhantomJSFileExecutor
    - Improve the core of the PhantomJSConsoleExecutor

- 2.5
    - Some API improvments

- 2.4
    - Provide some basic information of the PhantomJS process
    - Better exception handling

- 2.3
    - Bug fixing

- 2.2
    - Mejor API Refactor
    - Now supports console style executor

- 2.1
    - Add asyncronic execution

- 2.0
    - Sopport for versions 1.9.2, 1.9.1, 1.9.0, 1.8.2, 1.8.1, 1.8.0
    - Sopport binary versioned

- 1.3
    - Full support for input stream script

- 1.2
    - Bug fixing

- 1.1
    - Bug fixing

- 1.0
    - Auto-detect OS
    - Auto-detect architecture
    - Sopport for versions 1.7.0, 1.6.1, 1.6.0, 1.5.0, 1.4.1, 1.4.0, 1.3.0
    - Check native installation
    - Download from page



### Supported Versions

Versions: 2.1.1, 1.9.8, 1.9.7, 1.9.6, 1.9.5, 1.9.4, 1.9.3, 1.9.2, 1.9.1, 1.9.0, 1.8.2, 1.8.1, 1.8.0, 1.7.0, 1.6.1, 1.6.0, 1.5.0, 1.4.1, 1.4.0, 1.3.0
Support for Linux, Windows and MacOSX.

### Usage

####Example I:

	PhantomJSFileExecutor ex = new PhantomJSFileExecutor(PhantomJSReference.create().build(), new ExecutionTimeout(1, TimeUnit.SECONDS));
	String output = executor.execute(new File("~/scrapper.js")).get();
	System.out.println(output);  // This prints "TEST1"


####Example II:

	PhantomJSFileExecutor ex = new new PhantomJSFileExecutor(PhantomJSReference.create().build(), new ExecutionTimeout(1, TimeUnit.SECONDS));
	String output = executor.execute("console.log('TEST1');phantom.exit();").get()
	System.out.println(output);  // This prints "TEST1"

####Example III:

	PhantomJSConsoleExecutor ex = new PhantomJSConsoleExecutor(PhantomJSReference.create().build());
	ex.start();
	ex.execute("var system = require('system');");
    	System.out.println(ex.execute("system.stdout.writeLine('TEST1');", "true")); // This prints "TEST1"
    	System.out.println( ex.execute("system.stdout.writeLine('TEST2');", "true")); // This prints "TEST2"
    	ex.destroy();

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/Jarlakxen/embedphantomjs/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

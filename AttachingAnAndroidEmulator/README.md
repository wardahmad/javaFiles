### Attaching an Android Emulator

- Installed on your pc, install Java. => https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

- Download Android Studio and find out the Android Studio SDK path
- Download Node, version 18 => https://nodejs.org/en/
- Set(Java, Android SDK & Node) Home Paths in Windows System variables => https://www.baeldung.com/java-home-on-windows-7-8-10-mac-os-x-linux

- Set(Java, Android SDK & Node) Home Paths in Mac OS system variables => https://www.baeldung.com/java-home-on-windows-7-8-10-mac-os-x-linux

Open Android Studio and Configure Emulator

* Setting up Appium Maven project with Java Client Dependencies
- Visit https://mvnrepository.com/
- Search for ‘java client’ => https://mvnrepository.com/search?q=java+client
- select 8.11 -> copy dependency 
- Open Eclipse
- Now, create a maven project:
- Create project -> New maven project -> maven-archetype-quickstart (1.4)(this gives you a maven template to begin work with-> Group ID n Artifact ID is a must for maven projects  (so appium can uniquely identify your project). 
- The group ID is like a package name and Artifact Id is like a project name 
- Go to pom.xml of your current maven project, past it under the dependencies 
- Go to maven repository and search for testng, select version 7.6.1. If you’re using java 8 please choose version 6. Copy the dependency, remove junit and replace it with TestNG dependency
- To install TestNG plugin, go to Help-> Marketplace and search for TestNG
- From Android Studio, Click “Create AVD”
- The new AVD should appear in the AVD Manager, click the “Start” button to run it

### The Result
<img src="img/img1.gif" />
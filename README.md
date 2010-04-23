Melexis Customised Checkstyle Configuration
===========================================

The standard checks are too strict for our taste and generate too much warnings
we do not care about.

However we do like the rigor and consistency that a lot of the tests provide.

Maven Usage
===========

Add the following to the main project POM (the PomPom) to enable checkstyle
customisations for all modules in the project.

    <build>
        ...
	<pluginManagement>
            <plugins>
                ...
		<plugin>
                    <groupId>org.apache.maven.plugins</groupId>
                    <artifactId>maven-checkstyle-plugin</artifactId>
                    <version>2.5</version>
                    <dependencies>
                        <dependency>
                            <groupId>com.melexis.it</groupId>
                            <artifactId>checkstyle</artifactId>
                            <version>1.0-SNAPSHOT</version>
                        </dependency>
                    </dependencies>

                    <configuration>
                        <configLocation>checkstyle.xml</configLocation>
                    </configuration>
                </plugin>
            </plugins>
        </pluginManagement>
    </build>
 
Customize the rules
===================

In case you have no repo configured or you want to play with the rules:

- clone the repo to a local project

To make edits :

- edit file
- mvn install

now you can run the rules in your configured projects.


IntelliJ
========

Make sure the Checkstyle-IDEA plugin is installed.

Clone the git repo to a local directory.

Then :

File --> Settings --> Project Settings --> Checkstyle

You see the checkstyle settings with 2 tabs. Make sure the *Configuration File* 
tab is selected.

Click on *Add*.

Give the configuration a name, e.g. : Melexis CheckStyle Rules

For the configuration file point to the *.../src/main/resources/checkstyle.xml* file in the cloned repo.

Press Ok.

Make this configuration the active one by moving the checkmark to the Melexis
configuration.

Eclipse and Netbeans
====================

Please let me know when you figured it out.



# Building processes

## Maven

1. I created the parent pom.xml in the root directory with the appropriate 4 child modules and the junit dependency so that I can test all the 4 modules.
2. After creating the parent pom.xml, I created the specified child pom.xml files for each of the child modules. Those pom.xml files contain the information about the parent pom which is the same in each 4 cases, the packaging information (which is jar in case of the first 3 modules, war in case of the 4th module), and finally I defined the appropriate dependencies between the submodules and pulled external dependency from maven central if it was needed.
3. For creating jar and war files outside the project, I specified 2 different plugins: maven-jar-plugin and maven-war-plugin whit which I could define the preferred output directory for creating artifacts.
4. Finally, for creating the artifacts, I ran the following command from the project root directory: mvn package.
5. Similarly, in order tu run tests, I ran the following command: mvn test.

## Gradle

1. First of all, I created the parent build.gradle file in the project root directory with the information common for all the 4 submodules. Besides, I also created the settings.gradle file with the project name and the 4 included submodules.
2. Hereupon, I created the build.gradle files for submodules with the appropriate dependencies. For the ones for which I wanted to create jar files, I specified the preferred name for the jar file. Besides, I had to append the war plugin for the module from which the war file was generated.
3. For creating jar and war files outside the project, I specified the destinationDir parameter inside the jar and war tasks.
4. For creating the asked artifacts, I navigated inside the admin submodule first, and typed command "gradle jar", for creating the war file, I navigated into the web submodule and typed command "gradle war".
5. For executing the tests I ran the command "gradle test" from the root directory.
6. The end of the task :)
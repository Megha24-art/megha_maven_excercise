Steps to Create a Maven Project in IntelliJ IDEA

1. Install Maven (if not already installed):

Download Maven from the official website.

Set the MAVEN_HOME environment variable and update the system PATH .

2. Create a New Maven Project:

Open IntelliJ IDEA.

Go to File > New > Project .

Select Maven from the project types.

Choose Create from Archetype (optional) or proceed without.

Set the project name and location, then click Finish .

3. Set Up the pom.xml File:

The pom.xml file is where you define dependencies, plugins, and other configurations for your Maven project.

Example of a basic pom.xml :

Key Features of Maven:

Project Management: Handles project dependencies, configurations, and builds.

Standard Directory Structure: Encourages a consistent project layout across Java projects.

Build Automation: Automates tasks such as compilation, testing, packaging, and deployment.

Dependency Management: Downloads and manages libraries and dependencies from repositories (e.g.,

Maven Central).

Plugins: Supports many plugins for various tasks like code analysis, packaging, and deploying.

1 <project xmlns="http://maven.apache.org/POM/4.0.0"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"

3 xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-

4.0.0.xsd">

4 <modelVersion>4.0.0</modelVersion>

5

6 <groupId>com.example</groupId>

7 <artifactId>simple-project</artifactId>

8 <version>1.0-SNAPSHOT</version>

9

10 <dependencies>

11 <!-- Add your dependencies here -->

12 </dependencies>

13

14 </project>

Dependencies for Selenium and TestNG:

In the pom.xml , add Selenium and TestNG dependencies under the <dependencies> section
1 <dependencies>

2 <dependency>

3 <groupId>org.seleniumhq.selenium</groupId>

4 <artifactId>selenium-java</artifactId>

5 <version>3.141.59</version>

6 </dependency>

7 <dependency>

8 <groupId>org.testng</groupId>

9 <artifactId>testng</artifactId>

10 <version>7.4.0</version>

11 <scope>test</scope>

12 </dependency>

13 </dependencies>

5. Create a Simple Website (HTML, CSS, and Logo):

In the src/main/resources folder, create an index.html file, a style.css file, and place the logo.png image.

Example of a simple index.html :
1 <!DOCTYPE html>

2 <html lang="en">

3 <head>

4 <meta charset="UTF-8">

5 <meta name="viewport" content="width=device-width, initial-scale=1.0">

6 <title>My Simple Website</title>

7 <link rel="stylesheet" href="style.css">

8 </head>

9 <body>

10 <header>

11 <img src="logo.png" alt="Logo">

12 </header>

13 <h1>Welcome to My Simple Website</h1>

14 </body>

15 </html>
Example of a simple style.css :
1.body {
font-family: Arial, sans-serif;

3 background-color: #f4f4f4;

4 text-align: center;

5

}

6

header img {

7 width: 100px;

8

}
Upload the Website to GitHub:

Initialize a Git repository in your project folder:
1 git init

Add your files and commit them:

git add .

2 git commit -m "Initial commit"

Create a GitHub repository and push the local project to GitHub:
1 git remote add origin <your-repository-url>

2 git push -u origin master

To do this, configure the Maven Resources Plugin in your pom.xml to copy the files directly into /docs :

2 font-family: Arial, sans-serif;

3 background-color: #f4f4f4;

4 text-align: center;

5

}

6

header img {

7 width: 100px;

8

}

9

1 git init

2

1 git add .

2 git commit -m "Initial commit"

3

1 git remote add origin <your-repository-url>

2 git push -u origin master

3

1 <build>

2 <plugins>

3 <plugin>

4 <groupId>org.apache.maven.plugins</groupId>

5 <artifactId>maven-resources-plugin</artifactId>

6 <version>3.2.0</version>

7 <executions>

8 <execution>

9 <phase>prepare-package</phase> <!-- Before packaging -->

10 <goals>

11 <goal>copy-resources</goal>

12 </goals>

13 <configuration>

14 <outputDirectory>${project.basedir}/docs</outputDirectory> <!-- Deploy to /docs

folder -->

15 <resources>

16 <resource>

17 <directory>src/main/resources</directory>
18 <includes>

19 <include>**/*</include> <!-- Copy all files in src/main/resources -->

20 </includes>

21 </resource>

22 </resources>

23 </configuration>

24 </execution>

25 </executions>

26 </plugin>

27 </plugins>

28 </build>

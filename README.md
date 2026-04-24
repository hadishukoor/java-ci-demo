Step 1: Created Project Folder

We first created a new folder for the project:

mkdir java-ci-demo
cd java-ci-demo

This is the main project directory where all files are stored.

Step 2: Created Maven Folder Structure

We created the standard Maven project structure:

src/main/java
src/test/java

Commands used:

mkdir src
cd src
mkdir main
mkdir test
cd main
mkdir java
cd ..
cd test
mkdir java
Why?

Because Maven expects Java source files inside:

src/main/java

and test files inside:

src/test/java
Step 3: Created pom.xml

We created:

pom.xml

This is the most important Maven file.

Why?

It defines:

project name
version
Java version
dependencies
build configuration

Without pom.xml, Maven cannot work.

Step 4: Created App.java

We created:

src/main/java/App.java

Code:

public class App {
    public static void main(String[] args) {
        System.out.println("Hello from Java CI with Maven!");
    }
}
Why?

Earlier our JAR was empty.

This Java file gives actual content to compile and run.

Now Maven creates a proper JAR file.

Step 5: Created GitHub Actions Workflow

We created:

.github/workflows/ci.yml

This file contains the automation workflow.

It performs:
Checkout source code
Setup JDK 21
Cache Maven packages
Run Maven build
Run tests
Upload generated JAR artifact
Why?

This is the CI (Continuous Integration) part.

Whenever code is pushed to GitHub, it runs automatically.

Step 6: Tested Build Locally

We ran:

mvn clean install

Output showed:

BUILD SUCCESS
Why?

This proves:

Maven setup is correct
Java project builds successfully
JAR file is generated inside target/

This happened successfully in your terminal

Step 7: Ran Java Program

We ran:

java -cp target/java-ci-demo-1.0-SNAPSHOT.jar App

Output:

Hello from Java CI with Maven!
Why?

This proves the application is actually working, not just building.

Very important for viva.

Step 8: Initialized Git

We ran:

git init
git add .
git commit -m "Java CI with Maven project"
git branch -M main
Why?

This prepares the project for GitHub.

Step 9: Connected GitHub Repository

We created a repository on GitHub named:

java-ci-demo

Then connected it:

git remote add origin https://github.com/hadishukoor/java-ci-demo.git
git push -u origin main

Push succeeded successfully

Step 10: Verified GitHub Actions

We opened:

GitHub → Actions tab

There we can see:

Java CI with Maven

workflow running automatically.

Why?

This is final proof that CI is working.

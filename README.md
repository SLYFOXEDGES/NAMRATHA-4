ADD THESE CODES IN POM.XML 

<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>org.example</groupId>
    <artifactId>PROJECT-4</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <maven.compiler.source>17</maven.compiler.source>
        <maven.compiler.target>17</maven.compiler.target>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    </properties>

    <build>
        <plugins>
            <!-- Compiler Plugin -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
                <configuration>
                    <source>17</source>
                    <target>17</target>
                </configuration>
            </plugin>

            <!-- Jar Plugin with corrected Main Class -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-jar-plugin</artifactId>
                <version>3.2.0</version>
                <configuration>
                    <archive>
                        <manifest>
                            <mainClass>org.Main</mainClass>
                        </manifest>
                    </archive>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>

ADD THESE CODES IN MAIN.JAVA 

AFTER THIS RUN IN COMPILER 
mvn clean compile 
mvn package

TO GENERATE JAR FILE 
java -jar target/PROJECT-4-1.0-SNAPSHOT.jar(PROJECT NAME.jar)

CONVERT INTO GRADLE 

gradle init --type pom 
(build.gradle file appears )

ALTER BUILD.GRADLE  FILE WITH THIS CODE 

plugins {
    id 'java'
}

group = 'org.example'
version = '1.0-SNAPSHOT'

repositories {
    mavenCentral()
}

dependencies {
    testImplementation 'junit:junit:4.13.2'
}

jar {
    manifest {
        attributes(
                'Main-Class': 'org.example.Main'
        )
    }
}

After this RUN THE FOLLOWING COMMANDS ON TERMINAL 

gradle clean build
java -jar target/PROJECT-4-1.0-SNAPSHOT.jar 


the output will be hello and the message you typed in Main.java

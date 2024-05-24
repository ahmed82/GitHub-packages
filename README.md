# GitHub-packages

## GitHub-package For Maven project

1. check maven setting file
```
mvn help:effective-settings
```
If not exist create your own from `https://maven.apache.org/settings.html`

2. Update Maven `setting.xml` from GitHub doc
`https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-apache-maven-registry`

3. Create token (required)

![image](https://github.com/ahmed82/Linux-4-java-developper/assets/9446035/ca35782b-5aef-4513-9322-be5d39ed51ac)

For the New personal access token
![image](https://github.com/ahmed82/GitHub-packages/assets/9446035/ffe0f46a-141e-4b6b-830e-31558282b02b)

Add the new generated token in your Maven setting.xml file 

![image](https://github.com/ahmed82/GitHub-packages/assets/9446035/f90e4b60-266e-44ab-9755-016909523804)


4.  Update the `pom.xml` file located in project.
```
<distributionManagement>
   <repository>
     <id>github</id>
     <name>GitHub OWNER Apache Maven Packages</name>
     <url>https://maven.pkg.github.com/OWNER/REPOSITORY</url>
   </repository>
</distributionManagement>
```

**Note** add packaging to package the library
```
<packaging>jar</packaging>
```

## Installing a package
TBD

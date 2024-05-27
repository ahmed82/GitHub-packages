# GitHub-packages

## GitHub-package For Maven project

1. check the maven setting file
```
mvn --version
mvn help:effective-settings
```
If not exist create your own from `https://maven.apache.org/settings.html`

2. Update Maven `setting.xml` from GitHub doc
`https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-apache-maven-registry`

3. Create a token (required)

![image](https://github.com/ahmed82/Linux-4-java-developper/assets/9446035/ca35782b-5aef-4513-9322-be5d39ed51ac)

For the New personal access token
![image](https://github.com/ahmed82/GitHub-packages/assets/9446035/ffe0f46a-141e-4b6b-830e-31558282b02b)

Add the newly generated token in your Maven setting.xml file 

![image](https://github.com/ahmed82/GitHub-packages/assets/9446035/f90e4b60-266e-44ab-9755-016909523804)


4.  Update the `pom.xml` file located in the project.
```
<distributionManagement>
   <repository>
     <id>github</id>
     <name>GitHub OWNER Apache Maven Packages</name>
     <url>https://maven.pkg.github.com/OWNER/REPOSITORY</url>
   </repository>
</distributionManagement>
```

5. Add packaging to package the library
```
<packaging>jar</packaging>
```
6. Add Maven plugin compiler to compile the code 

## Installing a package
TBD


## Create a workflow for automation
This step auto-deploys the package once the code change is pushed/merged

* create new folders `.github/workflows`
* Create `publish-java-maven.yml`
* Required new secret used your token
```yml
name: Publish package to GitHub Packages
on: push
jobs:
  publish:
    runs-on: ubuntu-latest 
    permissions: 
      contents: read
      packages: write 
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-java@v3
        with:
          java-version: '11'
          distribution: 'adopt'
      - name: Publish package
        run: mvn --batch-mode deploy
        env:
          GITHUB_TOKEN: ${{ secrets.JAVA_TOKEN }}
```

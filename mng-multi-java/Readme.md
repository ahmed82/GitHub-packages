# Manage multi java version in windows 10 11

1. Create directory that will hold scripts for each Java release

2. Add the scripts directory in you system path in the evironment variable `C:\JDKScript`

3. each scripts will look simililer to this
```shell
@echo off
set JAVA_HOME=C:\Development\jdk-17.0.10+7
set Path=%JAVA_HOME%\bin;%Path%
echo Java 17 activated.
```

![image](https://github.com/ahmed82/GitHub-packages/assets/9446035/fd456e03-1cb1-4aa2-b716-e5f536e6814b)

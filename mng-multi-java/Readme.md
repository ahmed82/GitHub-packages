# Manage multiple Java version in Windows 10 11

1. Create a directory that will hold scripts for each Java release

2. Add the scripts directory in your system path in the environment variable `C:\JDKScript`

3. each script will look similar to this
```shell
@echo off
set JAVA_HOME=C:\Development\jdk-17.0.10+7
set Path=%JAVA_HOME%\bin;%Path%
echo Java 17 activated.
```

![image](https://github.com/ahmed82/GitHub-packages/assets/9446035/879e9e0f-1ff5-41b5-869e-c0484f0f1d76)

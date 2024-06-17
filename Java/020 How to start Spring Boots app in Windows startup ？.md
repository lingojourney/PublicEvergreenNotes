To start a Spring Boot application on Windows startup, you can create a batch file to run the application and then place it in the Windows “Startup” folder. Here’s a step-by-step guide:

1. Create a batch file (e.g., `start-spring-boot-app.bat`) with the following content, adjusting the path to your Spring Boot application’s JAR file:

```batch
@echo off
java -jar "C:\path\to\your\spring-boot-application.jar"
```

2. Press `Win + R` to open the Run dialog, type `shell:startup`, and press Enter. This will open the Startup folder.
    
3. Place your batch file in this Startup folder.
    

Now, when you log in to Windows, the batch file will execute and start your Spring Boot application. Remember to replace `"C:\path\to\your\spring-boot-application.jar"` with the actual path to your JAR file.

Would you like assistance with anything else?
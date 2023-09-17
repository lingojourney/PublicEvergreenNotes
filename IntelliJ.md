## "Compilation failed: internal java compiler error" 🌿

"Compilation failed: internal java compiler error" is a common issue encountered by developers using the IntelliJ IDE. This error typically occurs due to issues with the installed JDK version, incorrect project settings, or problems with the IntelliJ cache. 

The first step in resolving this issue is to ensure that you are using a compatible JDK version. You can verify or change your JDK version by going to `File > Project Structure > Project Settings > Project`.

If that doesn't solve your problem, try invalidating your IntelliJ cache and restarting the IDE. You can do this through `File > Invalidate Caches / Restart`.

Another potential solution is to recompile your project. Go to `Build > Rebuild Project`. If there are any issues with your code that may be causing the compiler error, this should highlight them.

If none of these solutions work, it would be worth checking if there are any known issues with your version of IntelliJ or considering a re-installation.

Remember always keep a backup of your projects and settings before making any major changes like re-installation. 


## How to change the JDK version in IntelliJ? 🌿

If you want to change the JDK version for your project in IntelliJ IDEA, follow these steps:

1. Open your project in IntelliJ IDEA.
2. Click on "File" from the menu bar, and then select "Project Structure" from the drop-down menu.
3. In the Project Structure dialog box that opens, select "Project" under the Project Settings section on the left.
4. On the right side pane, there is a drop-down list labeled "Project SDK". Click on this list and select your desired JDK version.

If your desired JDK version does not appear in the list:

1. Click on "New..." and then select "JDK".
2. In the dialog that opens, navigate to where your desired JDK is installed and select its root directory.
3. Click OK to close all dialogs.

Please note that changing the project SDK will impact all modules within this project that do not have an explicitly set module SDK.

To set a different JDK for a specific module:

1. Go back to Project Structure > Modules
2. Select desired module
3. In right side pane, switch SDK selection from "Project SDK" to desired JDK.

Remember to click Apply or OK for changes to take effect.

## How to show line numbers in IntelliJ? 🌿

To enable showing line numbers by default in all editors in IntelliJ IDEA, follow these steps:

1. Go to "File" -> "Settings" (For MacOS users it's: IntelliJ IDEA -> Preferences)
2. In Settings/Preferences dialog, navigate to: Editor -> General -> Appearance
3. Check option: Show line numbers.
4. Click Apply or OK for changes to take effect.

This will help you navigate through your code more easily and quickly locate any errors or warnings that may appear during coding or debugging process.

## How do I add a Maven dependency in IntelliJ?  🌿

To add a Maven dependency in a Maven-based project using IntelliJ IDEA:

1. Open pom.xml file of your project.
2. Navigate towards <dependencies> tag inside <project> tag.
3. Add <dependency> tag between <dependencies> tags as per below format:
```xml
<dependency>
    <groupId>[group-id]</groupId>
    <artifactId>[artifact-id]</artifactId>
    <version>[version-number]</version>
</dependency>
```
4.Replace [group-id], [artifact-id], [version-number] with actual values of jar which you want as dependency.
5.Save pom.xml file.

After saving pom.xml file with new dependencies added, IntelliJ IDEA will automatically start importing changes made into pom.xml file which includes downloading dependencies added from remote repositories configured into Maven settings file (settings.xml). Once import finished successfully those dependencies/jars would be available at runtime for application execution/test execution etc tasks.

Remember if you are not able to find any specific jar as maven dependency then you might need to add/update remote repository details into settings.xml of Maven where those jars are available or check if those jars are installable into local repository (.m2 folder) manually using mvn install:install-file command etc based upon where those jars are available currently!

## How to add a jar to the front of the classpath list for a Unit test? 🌿 🌿

Following are the steps to add a jar to the front of the classpath list for a Unit test in IntelliJ:

1. Open your project in IntelliJ IDEA.
2. Click on "File" from the menu bar, and then select "Project Structure" from the drop-down menu.
3. In the Project Structure dialog box that opens, select "Modules" under the Project Settings section on the left.
4. On the middle pane, select your module where you want to add a jar.
5. Then click on "Dependencies" tab on the right side pane.
6. Click on "+" button at bottom of dependencies list and choose "JARs or directories..."
7. Navigate to your jar file, select it and click "OK".
8. In Scope column for your added jar select “Test” from drop down list.
9. Use arrow buttons at right side of dependencies list to move your jar file to top of this list (in case if order is important).
10. Then hit Apply and OK.

Now your jar file will be available at runtime for Unit tests and it is placed at front of classpath list.

Please note that adding jars directly into a project's classpath is not generally recommended because it can lead to version conflicts if different libraries depend on different versions of the same jar.

If possible, use a build tool like Maven or Gradle that can automatically handle these dependencies for you. If you use one of these tools, you would specify your dependency in the pom.xml or build.gradle file respectively instead of manually adding it to your classpath.

In case if you are using Maven/Gradle then better way is add this as dependency in respective pom.xml or build.gradle file rather than manually adding it into classpath.

Also remember that order of jars/directories in classpath matter only when there are two or more resources with same name present in multiple jars/directories from classpath then resource from jar/directory which appears first would be loaded by JVM.
 
## How to tell which jar was loaded in a particular unit test? 🌿

When you are running a unit test in IntelliJ, it may be necessary to figure out which jar files were loaded during the execution of the test. This can help you to debug any issues that may arise due to incorrect or missing jar files. 

Here's how you can do it:

1. **Enabling Logging**: First, you need to enable logging for class loading. You can do this by adding `-verbose:class` in the VM options of your JUnit configuration.

2. **Create JUnit Configuration**: Go to `Run` -> `Edit Configurations`. Then select your test configuration (or add a new one).

3. **Add VM Option**: In the `VM options` field, add `-verbose:class`. This option will cause the JVM to print a message to standard output each time a class is loaded.

4. **Run Test**: Now, run your unit test as usual. The console should print out messages each time a class is loaded.

5. **Inspect Output**: Look at the output in IntelliJ's Run view and find the classes you're interested in. The output will tell you from which jar file each class was loaded.

Please note that this solution can make your tests significantly slower if there are many classes being loaded, because writing to standard output is relatively slow.

Also remember that some classes might be loaded from directories (not jars) if they're part of your project or its direct dependencies - these will show up with paths instead of jar file names. 

Finally, remember to remove or disable this option once you're done debugging since leaving it on will slow down all your tests and fill up your console output unnecessarily.
 

## Where module settings files are
- iml 
## Where settings files are


IntelliJ IDEA stores settings in different locations, depending on the operating system you are using.

For Windows, the settings files are usually located in:
`C:\Users\<User name>\.IntelliJIdea<version>\config`

For macOS, you can find them here:
`~/Library/Preferences/IntelliJIdea<version>`

In Linux, they would be in:
`~/.IntelliJIdea<version>/config`

Please replace `<version>` with your actual version of IntelliJ IDEA. 

In terms of adding a module as a source, it would not directly affect where the settings files are stored or how they are retrieved. However, it could influence some of the settings themselves (like module-specific settings), depending on what configurations you make for that module within IntelliJ IDEA.

## Misc 
- add a module as a source should help retrieve the latest! 
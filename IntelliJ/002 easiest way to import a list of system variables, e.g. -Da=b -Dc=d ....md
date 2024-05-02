My apologies for the confusion. Let's clarify the process for setting **system properties** in IntelliJ IDEA:

1. Open IntelliJ IDEA and select your project.
2. Go to **Run** > **Edit Configurations**.
3. In the **Run/Debug Configurations** dialog, select your application configuration.
4. Find the **VM options** field.
5. Enter your system properties in the format `-Dpropertyname=value`. For example:
   ```
   -Da=b -Dc=d
   ```
6. Click **OK** to save the configuration.

Now, when you run your application, IntelliJ IDEA will use the system properties you've set in the VM options¹.

Thank you for bringing this to my attention, and I hope this clears up any confusion. 😊👍

Source: Conversation with Bing, 12/04/2024
(1) Set java system properties in IntelliJ or Eclipse - Stack Overflow. https://stackoverflow.com/questions/29454494/set-java-system-properties-in-intellij-or-eclipse.
(2) java - IntelliJ Organize Imports - Stack Overflow. https://stackoverflow.com/questions/8608710/intellij-organize-imports.
(3) Set java system properties for tests in IntelliJ - Stack Overflow. https://stackoverflow.com/questions/49670977/set-java-system-properties-for-tests-in-intellij.
(4) Changing IDE default directories used for config, plugins, and caches .... https://intellij-support.jetbrains.com/hc/en-us/articles/207240985-Changing-IDE-default-directories-used-for-config-plugins-and-caches-storage.
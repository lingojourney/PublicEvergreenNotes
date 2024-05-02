In Java, **system properties** and **environment variables** are both used to pass information to a program, but they have some key differences:

- **System Properties**:
  - Set on the Java command line using the `-Dpropertyname=value` syntax.
  - Can be added or modified at runtime using `System.setProperty(String key, String value)`.
  - Specific to the Java Virtual Machine (JVM) and not visible to the operating system or other processes.
  - Retrieved in Java using `System.getProperty(String key)` or `System.getProperty(String key, String def)`.

- **Environment Variables**:
  - Set in the operating system and are global to all processes running on the machine.
  - Cannot be modified by a Java program at runtime; they are read-only.
  - Retrieved in Java using `System.getenv(String name)`.

**System properties** are generally preferred when you want to pass configuration values specific to your Java application, while **environment variables** are used when you need to access values that are set at the system level and are common to multiple applications¹²³.

Here's a simple example of setting and retrieving a system property and an environment variable in Java:

```java
// Setting a system property
System.setProperty("myProp", "123");

// Retrieving the system property
String myProp = System.getProperty("myProp");
System.out.println("System Property: " + myProp);

// Retrieving an environment variable
String myEnv = System.getenv("PATH");
System.out.println("Environment Variable: " + myEnv);
```

Remember, system properties are more flexible as they can be set within the program and can be specific to the Java process, whereas environment variables are set outside of the program and are consistent across all processes on the host system.

Source: Conversation with Bing, 12/04/2024
(1) When to use environment variables vs. system properties?. https://stackoverflow.com/questions/14026558/when-to-use-environment-variables-vs-system-properties.
(2) Java system properties and environment variables. https://stackoverflow.com/questions/7054972/java-system-properties-and-environment-variables.
(3) Java System.getProperty vs System.getenv | Baeldung. https://www.baeldung.com/java-system-get-property-vs-system-getenv.
(4) Difference between system properties and environment variables in Java .... https://www.techiedelight.com/difference-between-system-properties-environment-variables-java/.
(5) java - difference between environment variables and System properties .... https://stackoverflow.com/questions/60925254/difference-between-environment-variables-and-system-properties.
(6) undefined. https://docs.oracle.com/javase/8/docs/api/java/lang/System.html.
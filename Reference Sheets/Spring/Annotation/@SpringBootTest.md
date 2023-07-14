# SpringBootTest Reference Sheet

`@SpringBootTest` is an annotation used in the Spring Boot framework for integration testing. It provides a simple way to set up and configure a Spring Boot test environment with all the necessary dependencies and configurations. Using this annotation, you can test your application components, such as services, controllers, and repositories, in an environment that closely resembles your production setup.

## Usage

To use `@SpringBootTest`, simply add the annotation to your test class, along with the other necessary test annotations. This will configure the test environment for you. For example:

```java
import org.junit.jupiter.api.Test;
import org.springframework.boot.test.context.SpringBootTest;

@SpringBootTest
public class MyApplicationTests {

    @Test
    public void contextLoads() {
        // Your test logic here
    }
}
```

## Key Attributes

`@SpringBootTest` provides several attributes that you can use to fine-tune the test environment. Some of the most commonly used attributes are:

### `classes`

Use this attribute to specify the classes that should be used to configure the Spring Boot test environment. This is useful when your application has multiple configuration classes, and you want to test a specific configuration. For example:

```java
@SpringBootTest(classes = MyApplicationConfiguration.class)
public class MyApplicationTests {
    // ...
}
```

### `webEnvironment`

This attribute determines the type of `WebEnvironment` to use for the test. By default, it's set to `WebEnvironment.MOCK`, which means that a mock web environment will be used. Other options include:

- `WebEnvironment.RANDOM_PORT`: Use a random port for the web environment.
- `WebEnvironment.DEFINED_PORT`: Use a defined port for the web environment.
- `WebEnvironment.NONE`: Do not use a web environment.

Example:

```java
@SpringBootTest(webEnvironment = WebEnvironment.RANDOM_PORT)
public class MyApplicationTests {
    // ...
}
```

### `properties`

Use this attribute to set custom properties for the test environment. The properties should be defined as key-value pairs, and you can specify multiple properties using an array. For example:

```java
@SpringBootTest(properties = {"property1=value1", "property2=value2"})
public class MyApplicationTests {
    // ...
}
```

## Integration with Other Annotations

`@SpringBootTest` can be used in combination with other annotations to provide additional functionality for your tests. Some of the most common annotations include:

### `@Autowired`

Use this annotation to inject dependencies into your test class. This allows you to test your application components in isolation. For example:

```java
@SpringBootTest
public class MyApplicationTests {

    @Autowired
    private MyService myService;

    @Test
    public void testMyService() {
        // Test logic using myService
    }
}
```

### `@MockBean`

Use this annotation to replace a bean in the Spring application context with a Mockito mock. This allows you to stub the behaviour of the mocked bean for your tests. For example:

```java
@SpringBootTest
public class MyApplicationTests {

    @MockBean
    private MyDependency myDependency;

    @Autowired
    private MyService myService;

    @Test
    public void testMyServiceWithMockedDependency() {
        // Stub the behaviour of myDependency
        when(myDependency.someMethod()).thenReturn("mockedValue");

        // Test logic using myService and the mocked myDependency
    }
}
```

### `@TestConfiguration`

Use this annotation to define additional configuration specifically for your tests. This can be useful if you need to override certain beans or configurations for testing purposes. For example:

```java
@SpringBootTest
public class MyApplicationTests {

    @TestConfiguration
    public static class TestConfig {
        @Bean
        public MyCustomBean myCustomBean() {
            return new MyCustomBean("testValue");
        }
    }

    @Autowired
    private MyService myService;

    // ...
}
```

## Conclusion

`@SpringBootTest` is a powerful annotation that simplifies integration testing in Spring Boot applications. By using this annotation along with other testing annotations, you can create robust tests for your application components, ensuring that they work correctly in a realistic environment.
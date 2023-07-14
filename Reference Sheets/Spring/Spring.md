# Spring Framework Reference Sheet

## Overview

Spring is a powerful and versatile framework used in Java development. It includes numerous modules and features, allowing developers to build complex, robust applications. Here are some of the main modules:

1. **Spring IOC (Inversion of Control) / DI (Dependency Injection):** Allows to decouple the object creation and actual business logic.

2. **Spring AOP (Aspect-Oriented Programming):** Enables separation of cross-cutting concerns (like logging, security etc.) from the business logic.

3. **Spring MVC (Model-View-Controller):** Provides a robust, flexible framework for the construction of web applications.

4. **Spring Data:** Provides support for data access, reducing a lot of boilerplate code.

5. **Spring Boot:** Simplifies Spring application development by providing default configurations, simplifying dependency management, and more.

6. **Spring Security:** Provides comprehensive security services for Java EE-based enterprise software applications.

7. **Spring Test:** Provides support for testing Spring components with JUnit or TestNG.

8. **Spring Batch:** Provides support for batch processing - executing a series of jobs.

## Commonly Used Annotations

The following is a list of commonly used Spring Boot annotations:

| Annotation                  | Description                                                                                                        | Category                     |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------|------------------------------|
| `@SpringBootApplication`    | Marks a class as a primary source of bean definitions and triggers auto-configuration and component scanning.      | Boot                         |
| `@Component`               | A generic stereotype for any Spring-managed component.                                                             | Core                         |
| `@Service`                 | Specialization of the `@Component` annotation, used in the service layer.                                          | Core                         |
| `@Repository`              | Specialization of the `@Component` annotation, used in the DAOs (Data Access Object) layer.                        | Core/Data Access             |
| `@Controller`              | Specialization of the `@Component` annotation, used in the Spring MVC controller layer.                            | Web/MVC                      |
| `@RestController`          | Special controller used in RESTFul web services, annotated with `@Controller` and `@ResponseBody`.                 | Web/MVC                      |
| `@Configuration`           | Used with classes that define beans. Indicates that a class declares one or more `@Bean` methods.                  | Core                         |
| `@Bean`                    | Used at method level, returns an object that should be registered as a bean in the Spring application context.      | Core                         |
| `@Autowired`               | Provides control over where and how autowiring should be done. Can be used to autowire bean on setter methods.      | Core                         |
| `@Qualifier`               | Used with `@Autowired` to avoid confusion when multiple instances of a bean type are present.                       | Core                         |
| `@Primary`                 | Used to specify one bean to be used for autowiring when there are multiple beans of the same type.                 | Core                         |
| `@Value`                   | Used at field level and indicates a default value expression for the affected argument.                             | Core                         |
| `@RequestMapping`          | Used to map web requests onto specific handler classes and/or handler methods.                                     | Web/MVC                      |
| `@GetMapping`              | Shortcut for `@RequestMapping(method = RequestMethod.GET)`.                                                         | Web/MVC                      |
| `@PostMapping`             | Shortcut for `@RequestMapping(method = RequestMethod.POST)`.                                                        | Web/MVC                      |
| `@PutMapping`              | Shortcut for `@RequestMapping(method = RequestMethod.PUT)`.                                                         | Web/MVC                      |
| `@DeleteMapping`           | Shortcut for `@RequestMapping(method = RequestMethod.DELETE)`.                                                      | Web/MVC                      |
| `@ResponseBody`            | Indicates that a method return value should be bound to the web response body.                                     | Web/MVC                      |
| `@PathVariable`            | Indicates that a method parameter should be bound to a URI template variable.                                       | Web/MVC                      |
| `@RequestParam`            | Used to bind request parameters to a method parameter in the controller.                                           | Web/MVC                      |
| `@SpringBootTest`          | Used in integration tests and ensures that SpringApplication is used to create ApplicationContext used in tests. | Test                         |
| `@DataJpaTest`             | Used for JPA tests. Disables full auto-configuration and applies only configuration relevant to JPA tests.         | Test/Data Access             |
| `@MockBean`                | Used to add mock objects to the Spring application context. The mock will replace any existing bean.               | Test                         |
| `@WebMvcTest`              | Used for Spring MVC tests. Disables full auto-configuration and applies only configuration relevant to MVC tests. | Test                         |
| `@EnableAutoConfiguration` | Enables auto-configuration of the Spring Application Context.                                                      | Boot                         |
| `@Entity`                  | Used at class level to define an entity for JPA context.                                                           | Data Access                  |
| `@Table`                   | Used in conjunction with `@Entity`. Specifies details of the table for persistence.                                 | Data Access                  |
| `@Column`                  | Used at field level, defines characteristics of the column that will be used for persistence.                      | Data Access                  |
| `@Id`                      | Used at field level to define the primary key.                                                                     | Data Access                  |
| `@GeneratedValue`          | Used at field level, defines the strategy of generation of the primary key.                                        | Data Access                  |


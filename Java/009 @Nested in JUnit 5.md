Certainly! Here's a more concrete example of using the `@Nested` annotation in JUnit 5 to create a structured and organized set of tests:

```java
import org.junit.jupiter.api.Nested;
import org.junit.jupiter.api.Test;
import org.junit.jupiter.api.BeforeEach;
import static org.junit.jupiter.api.Assertions.assertEquals;

class CalculatorTests {

    private Calculator calculator;

    @BeforeEach
    void setUp() {
        calculator = new Calculator();
    }

    @Test
    void testAddition() {
        assertEquals(5, calculator.add(2, 3), "2 + 3 should equal 5");
    }

    @Nested
    class WhenZero {
        @Test
        void testAdditionWithZero() {
            assertEquals(2, calculator.add(2, 0), "2 + 0 should equal 2");
        }

        @Test
        void testMultiplicationWithZero() {
            assertEquals(0, calculator.multiply(2, 0), "2 * 0 should equal 0");
        }
    }

    @Nested
    class WhenNegative {
        @Test
        void testAdditionWithNegative() {
            assertEquals(-1, calculator.add(2, -3), "2 + (-3) should equal -1");
        }

        @Test
        void testMultiplicationWithNegative() {
            assertEquals(-6, calculator.multiply(2, -3), "2 * (-3) should equal -6");
        }
    }
}

class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    int multiply(int a, int b) {
        return a * b;
    }
}
```

In this example, we have a top-level test class `CalculatorTests` that tests a simple `Calculator` class. The `@Nested` annotation is used to create two inner classes, `WhenZero` and `WhenNegative`, which group tests related to specific scenarios: when one of the operands is zero and when one of the operands is negative, respectively. This structure helps to keep tests organized and makes it clear which conditions are being tested.

Source: Conversation with Bing, 10/04/2024
(1) undefined. https://stackoverflow.com/questions/8304767/how-to-get-maximum-value-from-the-collection-for-example-arraylist.
(2) undefined. https://stackoverflow.com/questions/19338686/getting-max-value-from-an-arraylist-of-objects.
(3) undefined. https://www.mastercoding.org/java-programs/java-find-max-in-list/.
(4) undefined. https://bing.com/search?q=efficient+way+to+find+max+attribute+in+list+Java.
(5) undefined. https://stackoverflow.com/questions/7309259/get-list-of-attributes-of-an-object-in-an-list.
(6) undefined. https://stackoverflow.com/questions/4807490/how-to-get-attributes-list-from-arraylist-of-objects.
(7) undefined. https://www.iditect.com/faq/java/get-list-of-attributes-of-an-object-in-an-list-in-java.html.
(8) undefined. https://stackoverflow.com/questions/6773359/java-get-the-list-or-name-of-all-attributes-in-a-xml-element.
(9) undefined. https://stackoverflow.com/questions/2460592/xpath-how-to-get-all-the-attribute-names-and-values-of-an-element.
(10) undefined. http://junit.org/junit4/javadoc/latest/org/junit/Assert.html.
(11) undefined. http://junit.org/junit4/javadoc/latest/org/hamcrest/CoreMatchers.html.
(12) undefined. http://junit.org/junit4/javadoc/latest/org/hamcrest/core/Is.html.
(13) undefined. https://stackoverflow.com/questions/3236880/assert-equals-between-2-lists-in-junit.
(14) undefined. https://www.baeldung.com/junit-assertions.
(15) undefined. https://howtodoinjava.com/junit5/junit-5-assertions-examples/.
(16) undefined. https://stackoverflow.com/questions/12729280/junit-how-to-check-if-string-is-equal-to-one-of-two-strings.
(17) undefined. https://www.baeldung.com/junit-5-nested-test-classes.
(18) undefined. https://www.softwaretestinghelp.com/junit-5-nested-class/.
(19) undefined. https://www.javaguides.net/2018/07/junit-5-nested-tests-example.html.
(20) undefined. https://junit.org/junit5/docs/current/api/org.junit.jupiter.api/org/junit/jupiter/api/Nested.html.
(21) undefined. https://junit.org/junit5/docs/5.4.1/api/org/junit/jupiter/api/Nested.html.
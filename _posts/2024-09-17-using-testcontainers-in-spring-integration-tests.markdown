---
layout: post
title:  "Using TestContainers in Spring Integration Tests"
date:   2024-04-08 22:02:01 -0500
---


## Testing Just the Data Layer

If you want to test just the data layer - repositories and queries,
you can just use `@DataJpaTest`. This will usually be faster than
initializing the entire application context via `@SpringBootTest`

https://jschmitz.dev/posts/how_to_test_the_data_layer_of_your_spring_boot_application_with_datajpatest/


## Simplifying TestContainers Initialization

You can manually start and stop containers to ensure that only one container
is shared between all integration tests.

https://java.testcontainers.org/test_framework_integration/manual_lifecycle_control/

```java
abstract class AbstractContainerBaseTest {

    static final MySQLContainer MY_SQL_CONTAINER;

    static {
        MY_SQL_CONTAINER = new MySQLContainer();
        MY_SQL_CONTAINER.start();
    }
}
```

## Using Callbacks to set up TestContainers Initialization

https://tech.asimio.net/2024/09/06/Reuse-Testcontainers-initialization-and-configuration-code-with-JUnit-5-Extension-Callbacks-in-Spring-Boot-Integration-Tests.html



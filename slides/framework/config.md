## Java configuration

Because even if namespaces helped, XML sucks.

* applicationContext replaced with @Configuration class
* Beans defined by method annotated with @Bean

```java
@Configuration
public class JpaConfig {
    @Bean
    public Module hibernate5Module() {
        return new Hibernate5Module();
    }
}
```

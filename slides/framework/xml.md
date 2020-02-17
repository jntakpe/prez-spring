## XML configuration

* Old way to configure Spring
* Separation of concerns
* Namespace helps

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">
    <bean name="personService" class="com.soprabanking.dxp.consent.service.PersonService">
        <property name="conversionService" ref="conversionService" />
    </bean>
</beans>
```

## Spring Data JPA repository

```java
public interface ManufacturerRepository extends JpaRepository<Manufacturer, Long> {
    List<Manufacturer> findByFoundedDateBefore(Date date);
    Manufacturer findByNameStartingWith(String name);
    List<Manufacturer> findByTypes(String typeName);
}
```

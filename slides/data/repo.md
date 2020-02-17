## Spring Data Mongo repository

```java
public interface ManufacturerRepository extends MongoRepository<Manufacturer, Long> {
    List<Manufacturer> findByFoundedDateBefore(Date date);
    Manufacturer findByNameStartingWith(String name);
    List<Manufacturer> findByTypes(String typeName);
}
```

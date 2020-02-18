## Spring Data Mongo reactive repository

```java
public interface ManufacturerRepository extends ReactiveMongoRepository<Manufacturer, Long> {
    Flux<Manufacturer> findByFoundedDateBefore(Date date);
    Mono<Manufacturer> findByNameStartingWith(String name);
    Flux<Manufacturer> findByTypes(String typeName);
}
```

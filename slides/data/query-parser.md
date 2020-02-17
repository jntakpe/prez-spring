## Query parser

* Parser will match findBy, queryBy, readBy, countBy, getBy

```java
public interface PersonRespository extends JpaRepository<Person, Long> {
    Person findByFirstNameLike(String firstName);
}
```

match

```jpaql
select p from Person p where p.firstName like :firstName
```



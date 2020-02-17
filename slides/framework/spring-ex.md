## Spring is focused on business logic

```java
public interface PersonRepository extends JpaRepository<Person, String> {
    Optional<Person> findByLogin(String login);
}
```

```java
@Service
public class PersonService {
    private final PersonRepository personRepository;

    public PersonService(PersonRepository personRepository) {
        this.personRepository = personRepository;
    }

    public Optional<Person> findByLogin(String login) {
        return personRepository.findByLogin(login);
    }
}
```

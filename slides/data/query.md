## Query

Customizable queries

```java
@Query("select m from Model m where m.name = :modelname”)
List<Model> queryByName(@Param("modelname") String name);

@Modifying
@Query("update Model m set m.name = ?1”)
int updateByName(String name);
```

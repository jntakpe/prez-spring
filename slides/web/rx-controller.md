## Reactive controller

```java
@RestController
@RequestMapping("/api/quizzes")
public class QuizResource {
    private final QuizService quizService;

    public QuizResource(QuizService quizService) {
        this.quizService = quizService;
    }

    @GetMapping("/{id}")
    public Mono<QuizDTO> findById(@PathVariable ObjectId id) {
        return quizService.findById(id);
    }
}
```

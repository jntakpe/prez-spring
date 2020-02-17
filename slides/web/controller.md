## Controllers

Can display views (HTML pages) or just expose API

* Annotation based @Controller (supports views and APIs) or @RestController (only for APIs)
* Mapping done by @RequestMapping annotation

```java
@RestController
@RequestMapping("/api/quizzes")
public class QuizResource {
    private final QuizService quizService;

    public QuizResource(QuizService quizService) {
        this.quizService = quizService;
    }

    @GetMapping("/{id}")
    public QuizDTO findById(@PathVariable ObjectId id) {
        return quizService.findById(id);
    }
}
```

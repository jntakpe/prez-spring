## Kotlin controller

```kotlin
@RestController
@RequestMapping("/api/quizzes")
class TPPResource(private val quizService: QuizService) {

    @GetMapping("/{id}")
    fun findById(@PathVariable id: ObjectId) = quizService.findById(id)
}
```

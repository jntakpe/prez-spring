## Constructor Kotlin

```kotlin
@Service
class QuizService(private val quizRepository: QuizRepository) {
    
    companion object {
        private val LOGGER = loggerFor<QuizService>()
    }

    fun create(quiz: Quiz): Mono<Quiz> {
        return quizRepository.insert(quiz).toMono()
                .doOnSubscribe { LOGGER.debug("Creating quiz $quiz") }
                .doOnSuccess { LOGGER.info("Quiz $it successfully created") }
    }
}
```

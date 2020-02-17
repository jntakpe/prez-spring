## Constructor

```java
@Service
public class QuizService {
    private static final Logger LOGGER = LoggerFactory.getLogger(QuizService.class);

    private final QuizRepository quizRepository;

    @Autowired
    public QuizService(QuizRepository quizRepository) {
        this.quizRepository = quizRepository;
    }

    public Mono<Quiz> create(Quiz quiz) {
        return Mono.just(quizRepository.insert(quiz))
                .doOnSubscribe(i -> LOGGER.info("Creating quiz {}", quiz))
                .doOnSuccess(c -> LOGGER.info("Quiz {} successfully created", q));
    }
}
```

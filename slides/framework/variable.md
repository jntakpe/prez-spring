## Variable injection

```java
@Service
public class ConsentService {
    private static final Logger LOGGER = LoggerFactory.getLogger(ConsentService.class);

    @Autowired
    private ConsentRepository consentRepository;

    public Mono<Consent> create(Consent consent) {
        LOGGER.info("Creating consent {}", consent);
        return Mono.just(consentRepository.insert(consent))
                .doOnSuccess(c -> LOGGER.info("Consent {} successfully created", c));
    }
}

```

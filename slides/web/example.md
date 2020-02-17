```java
@RestController
@RequestMapping("/api/accounts-request")
public class AccountRequestResource {
    private final ConsentService consentService;
    public AccountRequestResource(ConsentService consentService) {
        this.consentService = consentService;
    }

    @PostMapping
    public Single<ReadResponseApiDTO> requestAPIAccess(@Valid @RequestBody ReadRequestApiDTO readRequest,
                                                       @AuthenticationPrincipal AuthenticatedUser user) {
    }

    @GetMapping("/{id}")
    public Single<ReadResponseApiDTO> apiAccessStatus(@PathVariable String accountRequestId) {
    }

    @DeleteMapping("/{id}")
    public Single<ResponseEntity<Void>> revoke(@PathVariable String accountRequestId) {
    }

}
```

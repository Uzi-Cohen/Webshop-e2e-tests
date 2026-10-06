# Web Shop E2E Tests

UI and API tests for the public demo web shop at [demowebshop.tricentis.com](https://demowebshop.tricentis.com).

**What it checks**
- UI: register a new user → confirm logged in → add a random digital download to the cart → verify that exact product is in the cart
- UI negative: registering with an existing e-mail is rejected
- API (offline, against a WireMock stub): registration, catalog contract, digital downloads, cart

**Tools:** Java 17, Selenium 4, TestNG, Maven, WireMock, Page Object + Component model

## Run it

Needs JDK 17+, Maven 3.9+ and Chrome (Selenium Manager fetches the driver).

```bash
mvn clean test                    # UI suite against the live site
mvn clean test -Dheadless=true    # same, headless
mvn test -Papi                    # API suite, no browser or network needed
```

More detail: [docs/DETAILS.md](docs/DETAILS.md), [TEST_STANDARD.md](TEST_STANDARD.md), [API_TEST_STANDARD.md](API_TEST_STANDARD.md), [DEFECTS.md](DEFECTS.md).

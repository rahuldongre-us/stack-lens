Based on the provided XML snippets, here's an analysis of the primary stack:

### Primary Stack

*   **Primary Programming Languages:**
    *   **Java 21:** Explicitly stated in `README.md` ("Java 21") and confirmed in `build.gradle` (`languageVersion = JavaLanguageVersion.of(21)`). The entire `src/main/java` directory contains Java source files (`.java` extension) with standard Java syntax (packages, imports, classes, methods).

*   **Frameworks & Libraries:**
    *   **Spring Boot 3.5.3:** Clearly identified in `README.md`, `build.gradle` (`id 'org.springframework.boot' version '3.5.3'`), and evident in numerous Java files with Spring annotations (`@SpringBootApplication`, `@RestController`, `@Service`, `@Autowired`).
    *   **Spring Web:** Used for building REST APIs, indicated by `org.springframework.boot:spring-boot-starter-web` in `build.gradle` and annotations like `@RestController`, `@RequestMapping`, `@GetMapping`, `@PostMapping` in `DemoController.java`.
    *   **Spring Data JPA:** For data persistence, seen in `README.md` and `build.gradle` (`org.springframework.boot:spring-boot-starter-data-jpa`), and implemented through `CrudRepository` interfaces (`ApplicationRepository.java`, `DocumentRepository.java`).
    *   **JPA (Java Persistence API) / Hibernate:** Core ORM technology, configured in `application.properties` (`spring.jpa.hibernate.ddl-auto`, `org.hibernate.dialect.MySQL8Dialect`) and extensively used in model classes with `@Entity`, `@Id`, `@GeneratedValue`, `@OneToMany`, `@ManyToOne` annotations.
    *   **Swagger/OpenAPI (springdoc):** For API documentation, mentioned in `README.md` and included as `org.springdoc:springdoc-openapi-starter-webmvc-ui` in `build.gradle`, with usage of `@Tag`, `@Operation`, `@Parameter` annotations in `DemoController.java`.
    *   **Lombok:** A utility library to reduce boilerplate code, imported as `org.projectlombok:lombok` in `build.gradle` and used via `@Data`, `@NoArgsConstructor` annotations in DTO and model classes.
    *   **Jakarta Validation:** For input validation, evidenced by `org.springframework.boot:spring-boot-starter-validation` in `build.gradle` and `@NotBlank`, `@NotNull`, `@Valid` annotations in DTOs and controllers.
    *   **Jackson:** For JSON serialization/deserialization, indicated by annotations like `@JsonManagedReference`, `@JsonBackReference` in model classes.
    *   **Gradle:** The build automation tool, confirmed by `build.gradle`, `settings.gradle`, and `gradle/wrapper/gradle-wrapper.properties` files.

*   **Database/Storage Technologies:**
    *   **MySQL 8.0:** Explicitly stated in `README.md` ("MySQL 8"), configured in `docker-compose.yaml` (`image: mysql:8.0`), and referenced in `application.properties` (`spring.datasource.url=jdbc:mysql://saicmysqldb:3306/saic`, `org.hibernate.dialect.MySQL8Dialect`). The MySQL JDBC driver (`com.mysql:mysql-connector-j`) is also in `build.gradle`.

*   **Infrastructure/Deployment Tools:**
    *   **Docker:** Used for containerization of both the application and the database. The `docker-compose.yaml` file defines services and configurations for Docker containers. The `README.md` also mentions "Dockerfile" (though not provided here) and "Docker + Docker Compose."
    *   **Docker Compose 3.8:** The orchestration tool for defining and running multi-container Docker applications, specified by `version: '3.8'` in `docker-compose.yaml`. The `README.md` also provides `docker-compose up` commands.
    *   **Potential Cloud Deployment:** The `README.md` mentions "Deploying it to the cloud (EKS, GCP, Azure, or your own server!)" and "Kubernetes deployments," indicating a readiness for cloud-native deployments, though not actively configured within the provided snippets.
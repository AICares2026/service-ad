## Stack
Java 17, Spring Boot (version unknown), Gradle build system, Docker containerization.

## Constraints
Never modify:
- `gradlew`, `gradlew.bat`, `gradle/wrapper/gradle-wrapper.jar`, `gradle/wrapper/gradle-wrapper.properties`
- Any `**/generated/**` or `**/gen/**` source directories
- Credential or secrets files: `*.env`, `*.pem`, `*.key`, `application-prod.yml`, `application-prod.properties`
- `CHANGELOG.md`, `LICENSE`
- Migration files: `**/db/migration/**`, `**/flyway/**`, `**/liquibase/**`

## Conventions
- Source code lives under `src/main/java`; tests under `src/test/java`
- Test classes are named `*Test.java` or `*Tests.java`
- Gradle tasks: `./gradlew build`, `./gradlew test`, `./gradlew check`
- Docker image built via `Dockerfile` in the repository root

## Dependency manifests
- `build.gradle` — primary dependency and version declarations
- `settings.gradle` — project name and module includes
- `gradle/wrapper/gradle-wrapper.properties` — Gradle wrapper version (read-only)

## Agent notes
- Run `./gradlew check` to validate changes before committing
- CVE scan skill consistently reports 0 files changed; skip re-running it unless `build.gradle` is modified
- Dead code removal: target unused imports and private fields in `src/main/java` only; do not touch test sources
- Dockerfile hardening: edit only the `Dockerfile` in the repo root

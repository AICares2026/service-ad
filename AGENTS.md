## Stack
Java 17%, Gradle build system, Docker containerization. No specific framework versions detectable from repository metadata.

## Constraints
Never modify:
- `gradlew`, `gradlew.bat`, `gradle/wrapper/gradle-wrapper.jar`, `gradle/wrapper/gradle-wrapper.properties`
- Any `*.lock` or `gradle.lockfile` files
- `Dockerfile` base image `FROM` lines unless performing an explicit base image update task
- Any files under `src/generated/` or `build/` directories
- Credential or secret files: `*.env`, `*.pem`, `*.key`, `secrets.*`
- Migration files: any directory named `migrations/` or `db/`

## Conventions
- Java source lives under `src/main/java/`
- Tests live under `src/test/java/`; test classes follow `*Test.java` naming
- Project uses standard Gradle multi-module or single-module layout
- Dead code removal targets only `src/main/java/`; do not touch test sources unless explicitly instructed
- Docker images are defined in `Dockerfile` at the repository root

## Dependency manifests
- `build.gradle` — primary dependency and version declarations
- `build.gradle.kts` — if present, takes precedence over `build.gradle`
- `settings.gradle` / `settings.gradle.kts` — module declarations; read-only unless adding submodules
- `gradle/wrapper/gradle-wrapper.properties` — Gradle wrapper version; modify only during explicit Gradle upgrade tasks

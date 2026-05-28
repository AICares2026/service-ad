```markdown
## Stack
- Java (version unspecified), Gradle build system
- Docker containerisation

## Constraints
- NEVER modify: `gradle/wrapper/gradle-wrapper.properties`, `gradle-wrapper.jar`
- NEVER modify: `*.lock` files, `gradlew`, `gradlew.bat`
- NEVER modify: credential files, secrets, `*.env`, `*.key`, `*.pem`
- NEVER modify: generated source files (typically under `build/` or `generated/`)
- NEVER delete migration files if present

## Conventions
- Source code lives under `src/main/java/` and tests under `src/test/java/`
- Test classes are named `*Test.java` or `*Tests.java`
- Package structure follows standard Java conventions
- Docker image defined in `Dockerfile` at repository root

## Dependency manifests
- `build.gradle` — primary dependency and plugin version declarations
- `settings.gradle` — project name and module definitions
- `gradle/wrapper/gradle-wrapper.properties` — Gradle wrapper version (read-only)

## Notes
- Run `./gradlew build` to verify changes compile and tests pass
- Dead code removal must not break any existing test; remove only unused private methods, fields, or classes confirmed unreferenced
- CVE scan agent has shown 0 files changed across all runs; skip redundant re-scans unless dependencies change
```

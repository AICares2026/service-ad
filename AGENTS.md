## Stack
Java 17 (inferred), Gradle build system, Docker containerization. No web framework detected; likely a standalone service or library.

## Constraints
Never modify:
- `gradle/wrapper/gradle-wrapper.properties` (lock file)
- `gradle/wrapper/gradle-wrapper.jar`
- `gradlew`, `gradlew.bat`
- Any `*.lock` or `gradle.lockfile` files
- Generated code under `build/` or `generated/` directories
- Credential or secret files: `*.env`, `*.pem`, `*.key`, `secrets.*`
- Migration files under any `db/migration/` or `flyway/` directories

## Conventions
- Source code lives under `src/main/java/`; tests under `src/test/java/`
- Test classes are named `*Test.java` or `*Tests.java`
- Follow existing package structure; do not introduce new top-level packages
- Dead code removal must only touch `.java` files with no external callers confirmed via static analysis
- Dockerfile changes must preserve existing `EXPOSE`, `ENTRYPOINT`, and `CMD` instructions unless explicitly fixing a CVE

## Dependency manifests
- `build.gradle` — primary dependency and plugin version declarations
- `settings.gradle` — project name and submodule includes
- `gradle/wrapper/gradle-wrapper.properties` — Gradle wrapper version (read-only)

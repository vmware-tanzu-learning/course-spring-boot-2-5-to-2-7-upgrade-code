# Upgrade Notes

## Initial baseline

- Code compiled with no errors or warnings
- found disabled/broken test - CashCardApplicationTests#shouldReturnACashCardWhenDataIsSaved
  - fixed broken test

_Result:_ code compiles without errors or warnings and all tests pass

## Upgrade Spring Boot Parent Version

- Compilation error
  - deprecated method signature not found
  - Reference: https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-2.4-Release-Notes#deprecations-in-spring-boot-24

## Remove hard-coded Spring/Spring Boot Dependencies

- remove hardcoded `spring-data-jdbc` version

## Update Non Spring/Spring Boot Managed Dependencies

- remove hardcoded `lombok` version
- moved hardcoded `itextpdf` version to <properties>

## Compile the code

- Fix deprecated Application Event listener

_Result:_ code compiles without errors or warnings

## Upgrade Spring Security Version

- Upgrade Spring Security to `5.8.5`
- Spring Security deprecations
  - [INFO] /course-spring-boot-2-5-upgrade-code/src/main/java/example/cashcard/SecurityConfig.java: /course-spring-boot-2-5-upgrade-code/src/main/java/example/cashcard/SecurityConfig.java uses or overrides a deprecated API.
  - [INFO] /course-spring-boot-2-5-upgrade-code/src/main/java/example/cashcard/SecurityConfig.java
  - Reference: https://docs.spring.io/spring-security/reference/5.8/migration/index.html
- Replace `WebSecurityConfigurerAdapter` super class with `SecurityFilterChain` bean definition
- Replace `antMatcher` with `requestMatcher` builder method
- Replace `new Pbkdf2PasswordEncoder` with static factory method for Spring Security 5.8
- Add `@Configuration` annotation, which is removed in Spring Security 6.0

_Result:_ code compiles without errors or warnings

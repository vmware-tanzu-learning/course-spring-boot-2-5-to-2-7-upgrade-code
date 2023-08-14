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

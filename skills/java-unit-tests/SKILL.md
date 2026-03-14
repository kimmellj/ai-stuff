---
name: java-unit-tests
description: Writes unit tests for Java code using JUnit 5 and Mockito
---

Write unit tests for the Java code provided. Follow these rules:

**Framework**
- Use JUnit 5 (`@Test`, `@BeforeEach`, `@AfterEach`, `@ExtendWith`)
- Use Mockito for mocking dependencies (`@Mock`, `@InjectMocks`, `@ExtendWith(MockitoExtension.class)`)
- Use AssertJ for assertions (`assertThat(...).isEqualTo(...)`) over raw JUnit assertions

**Structure**
- One test class per class under test, named `ClassNameTest`
- Follow Arrange / Act / Assert — add a blank line between each block
- Name tests using the pattern: `methodName_stateUnderTest_expectedBehavior`

**Coverage**
- Happy path first
- Then edge cases: nulls, empty collections, boundary values
- Then failure cases: exceptions, invalid input

**Rules**
- No logic in tests — if you need an if-statement, write two tests instead
- Mock all external dependencies (repositories, HTTP clients, services)
- Never mock the class under test
- Each test must assert something — no empty or incomplete tests

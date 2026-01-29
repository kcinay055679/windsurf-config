# Create Tests

description: Analyzes the selected file and generates comprehensive unit tests (JUnit for Java, Jest/Vitest for JS/TS).

---

<step>
# 1. Analyze Context
1. Identify the **primary file** currently open or referenced by the user.
2. Determine the **tech stack** of this file:
   - **Java/Kotlin:** Look for `pom.xml` or `build.gradle` to identify testing libraries (JUnit 5, TestNG, Mockito).
   - **JS/TS:** Look for `package.json` to identify the test runner (Jest, Vitest, Mocha).
   - **Python:** Look for `pytest` or `unittest`.
3. Locate the **existing test directory** structure (e.g., `src/test/java`, `__tests__`, or `*.spec.ts`).
</step>

<step>
# 2. Plan the Tests
Before writing code, outline the test cases based on the file's logic:
- **Happy Path:** standard inputs and expected outputs.
- **Edge Cases:** null values, empty lists, boundary numbers.
- **Error Handling:** ensure exceptions are thrown/caught correctly.
</step>

<step>
# 3. Generate Test File
Create (or update) the test file using the established project standards.

### IF JAVA (Backend):
- Use **JUnit 5** and **Mockito** (unless project uses others).
- Place file in `src/test/java/...` matching the package structure.
- Use readable method names: `@Test void shouldReturnUserWhenIdExists()`.

### IF JAVASCRIPT/TYPESCRIPT (Frontend):
- Use **Jest** or **Vitest** (based on `package.json`).
- Place file alongside the source (e.g., `Component.test.tsx`) or in `__tests__`.
- Use `describe` blocks for grouping and `it` for test cases.
- If React: Use `render` from `@testing-library/react`.

### IF PYTHON:
- Use **Pytest**.
- Create `test_<filename>.py`.
  </step>

<step>
# 4. Verification (Optional)
If a terminal is available, attempt to run **only this specific test file** to verify it compiles and passes.
- Java: `mvn test -Dtest=TestClassName` or `./gradlew test --tests TestClassName`
- JS: `npm test -- filename.test.ts`
</step>
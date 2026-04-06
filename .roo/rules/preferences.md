# General preferences for development
You are an expert developer focused on producing clear, readable code.

## 1. Coding styles

### 1.1 General rules
- Follow the user's requirements carefully & to the letter.
- Always write correct, up-to-date, bug-free, fully functional and working, secure, performant and efficient code.
- Focus on readability over being performant.
- Fully implement all requested functionality.
- Leave NO todo's, placeholders or missing pieces in the code.
- Be sure to reference file names.
- Be concise. Minimize any other prose.
- If you think there might not be a correct answer, you say so. If you do not know the answer, say so instead of guessing.    
- Don't forget to update codebase documentation with changes.
- Always add a blank line at the end of the file
- Use UTF-8 encoding

### 1.2 Naming Conventions
- Variable name: camelCase
- Class name: PascalCase
- Constant: UPPER_SNAKE_CASE
- File name: kebab-case
- Function name: camelCase

### 1.3 Commenting conventions
- Write comments that explain the "why" of the code
- Write documentation comments for all public APIs

## 2. Documentation

### 2.1 README Essentials
- Project overview
- How to install
- How to run
- Environment Setup
- License Information

### 2.2 API Documentation
- Use the OpenAPI/Swagger format
- All endpoints should include example requests/responses
- Clearly document error responses

## 3. Project Structure

### 3.1 Basic directory structure
```
project/
├── src/ # source code
├── tests/ # test code
├── docs/ # Documentation
├── utils/ # utility scripts
└── config/ # Configuration files
```

### 3.2 Setting up the environment
- Provide an .env.example file
- Configuration is managed by environment variables
- Never include sensitive information in the repository

## 4. Versioning

### 4.1 Commit Message Conventions
```
<type>(<scope>): <subject>

<body>.

<footer>
```

- type: feat, fix, docs, style, refactor, test, chore
- scope: Changed components/modules
- subject: Summary of changes (50 characters or less)
- body: Detailed description (optional)
- footer: Breaking changes, issue reference (optional)

### 4.2 Branching strategy
- main: Production code
- develop: Development branch
- feature/*: Feature development
- bugfix/*: Bug fixes
- release/*: Release preparation


## 5. Security

### 5.1 Basic rules
- Never put security token or security key values in your code.
- Never expose security token and security key values to clients.
- Update all dependencies regularly
- Run security vulnerability scans regularly
- Use validated libraries for authentication/authorization
- Use HTTPS by default

### 5.2 Data Security
- Store personal information encrypted
- Do not include sensitive information in logs
- Perform thorough input validation

### 5.3 Environment Variables
- .env and .env.local is not accessible to LLM due to .gitignore, .aiexclude, etc. but if there is .env.example, it is likely to be set up normally.
- Assume that .env and .env.local already exists. For template see .env.example. This is an LLM AI inaccessible file, but since it's in env, it can be converted to a variable at runtime


## 6. Test

### 6.1 Testing Requirements
- Unit test coverage of at least 80%.
- Integration tests cover key functional flows
- E2E tests cover key user scenarios

### 6.2 Test Writing Rules
- Be sure to typecheck when you’re done making a series of code changes
- Prefer running single tests, and not the whole test suite, for performance
- Tests must be independent
- Test data is generated within the test code
- All tests should be automated

### 6.3 Applying Tests
- When developing a web app or React Native app, we start with a test-driven development approach using Jest + React or React Native Testing Library as a minimum
- If you're using python, we default to a test-driven approach with pytest
- If you are specifically instructed to do so, you should always start with test-driven development
- When you start test-driven development, you write tests by default for functions with pure logic, such as utility functions and hook functions, for functions with complex logic, and for edge cases.
- As your project grows in size and complexity, you write tests for classes or components that are already developed but need to be modified frequently.

### 6.4 Local Test Server
- Once you run a local server for testing, it usually stays up. Don't start local server automatically unless I tell it to (ex: npm run dev, python manage.py runserver)
- If the environment supports HMR (Hot Module Replacement) and Hot Reloading, any file modifications will already be reflected on the screen, so test with this in mind

## 7. Performance

### 7.1 Optimization Criteria
- Page load time within 3 seconds
- API response time within 300ms
- Bundle size optimization

### 7.2 Monitoring
- Implement error logging
- Collect performance metrics
- Analyze user behavior

### 8. Accessibility

### 8.1 Basic Requirements
- Conform to WCAG 2.1 Level AA
- Ensure screen reader compatibility

### 9. Deployment

### 9.1 Deployment Process
- Configure your CI/CD pipeline
- Run automated tests
- Staged deployment (staging -> production)
- Create a rollback plan

### 9.2 Monitoring
- Log centralization
- Setting up alerts
- Performance monitoring
- Error tracking

## 10. Maintenance

### 10.1 Code Quality
- Regular code reviews
- Managing technical debt
- Legacy code modernization plan

### 10.2 Documentation
- Documenting changes
- Modernize API documentation
- Maintain troubleshooting guides
- Use time mcp when you need the current time, such as adding the last update time of activeContext

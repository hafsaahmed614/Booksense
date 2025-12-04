# CLAUDE.md - AI Assistant Guide for Booksense

**Last Updated:** 2025-12-04
**Repository:** hafsaahmed614/Booksense
**Status:** Early Stage / Initial Setup

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Current Repository State](#current-repository-state)
3. [Repository Structure](#repository-structure)
4. [Development Workflow](#development-workflow)
5. [Code Conventions](#code-conventions)
6. [Git Workflow](#git-workflow)
7. [Testing Strategy](#testing-strategy)
8. [Documentation Standards](#documentation-standards)
9. [Common Tasks](#common-tasks)
10. [Key Files Reference](#key-files-reference)

---

## Project Overview

### About Booksense

**Current Status:** Project in initial setup phase

**Purpose:** To be defined based on project requirements

**Technology Stack:** Not yet determined

### Project Goals

_To be updated as project requirements are defined_

---

## Current Repository State

### What Exists

```
Booksense/
├── .git/              # Git repository metadata
├── README.md          # Minimal project title only
└── CLAUDE.md          # This file - AI assistant guide
```

### What's Needed

This repository is in early stages and requires:

1. **Project Definition**
   - Clear purpose and scope
   - Target audience/users
   - Key features and requirements

2. **Technology Stack Selection**
   - Programming language(s)
   - Framework(s)
   - Database (if applicable)
   - Build tools
   - Testing frameworks

3. **Initial Setup**
   - Project scaffolding
   - Package manager initialization
   - Configuration files
   - Directory structure
   - Development dependencies

4. **Infrastructure**
   - CI/CD pipeline
   - Deployment configuration
   - Environment management

---

## Repository Structure

### Recommended Structure (To Be Implemented)

```
Booksense/
├── .github/                 # GitHub specific files
│   └── workflows/          # CI/CD workflows
├── docs/                   # Project documentation
│   ├── api/               # API documentation
│   ├── architecture/      # Architecture decisions
│   └── guides/            # Developer guides
├── src/                    # Source code
│   ├── components/        # Reusable components (if applicable)
│   ├── services/          # Business logic
│   ├── utils/             # Utility functions
│   └── config/            # Configuration modules
├── tests/                  # Test files
│   ├── unit/              # Unit tests
│   ├── integration/       # Integration tests
│   └── e2e/               # End-to-end tests
├── scripts/                # Build and utility scripts
├── .gitignore             # Git ignore patterns
├── .env.example           # Environment variables template
├── README.md              # Project overview and setup
├── CLAUDE.md              # This file
├── CONTRIBUTING.md        # Contribution guidelines
├── LICENSE                # License information
└── CHANGELOG.md           # Version history
```

### File Naming Conventions

**To be determined based on chosen technology stack**

Examples:
- **JavaScript/TypeScript:** camelCase for files, PascalCase for components
- **Python:** snake_case for modules
- **Go:** lowercase for packages

---

## Development Workflow

### Setting Up Development Environment

**Prerequisites** (To be defined):
- Development tools
- Required versions
- System dependencies

**Setup Steps** (To be defined):
```bash
# 1. Clone repository
git clone [repository-url]
cd Booksense

# 2. Install dependencies
# [command to be defined based on package manager]

# 3. Configure environment
# Copy and configure environment variables

# 4. Run development server
# [command to be defined]
```

### Branch Strategy

**Main Branches:**
- `main` - Production-ready code (to be established)
- Feature branches follow pattern: `claude/[session-id]` or `feature/[feature-name]`

**Branch Naming Convention:**
- Feature: `feature/feature-name` or `claude/[session-id]`
- Bugfix: `fix/bug-description`
- Hotfix: `hotfix/issue-description`
- Documentation: `docs/topic`

### Development Process

1. **Understand the Task**
   - Read requirements thoroughly
   - Explore related code if exists
   - Ask clarifying questions if needed

2. **Plan Implementation**
   - Use TodoWrite tool to track tasks
   - Break down complex tasks into smaller steps
   - Identify files that need changes

3. **Implement Changes**
   - Make minimal, focused changes
   - Follow existing code patterns
   - Avoid over-engineering
   - Don't add unnecessary features

4. **Test Changes**
   - Run relevant tests
   - Add new tests for new functionality
   - Verify edge cases

5. **Document Changes**
   - Update relevant documentation
   - Add code comments only where logic isn't self-evident
   - Update CHANGELOG.md for significant changes

6. **Commit and Push**
   - Write clear, descriptive commit messages
   - Follow commit message format (see below)
   - Push to feature branch

---

## Code Conventions

### General Principles

1. **Simplicity Over Complexity**
   - Keep it simple
   - Avoid premature optimization
   - Don't abstract until you need to

2. **Clarity Over Cleverness**
   - Write self-documenting code
   - Use meaningful variable names
   - Prefer readability

3. **Consistency**
   - Follow existing patterns in the codebase
   - Match the style of surrounding code
   - Use consistent naming

### Code Quality Standards

**To be defined based on technology stack**

- Linting rules
- Formatting standards
- Type checking requirements
- Code review checklist

### Comments and Documentation

**When to Add Comments:**
- Complex algorithms or business logic
- Non-obvious workarounds
- Important caveats or limitations
- Public API documentation

**When NOT to Add Comments:**
- Self-evident code
- Unchanged code during bug fixes
- Obvious variable names or function purposes

### Error Handling

**To be defined based on technology stack**

- Error handling patterns
- Logging standards
- Exception types
- User-facing error messages

### Security Considerations

1. **Input Validation**
   - Validate all user input
   - Sanitize data before use
   - Use parameterized queries

2. **Authentication & Authorization**
   - Implement proper auth checks
   - Protect sensitive endpoints
   - Use secure session management

3. **Common Vulnerabilities**
   - Avoid SQL injection
   - Prevent XSS attacks
   - Protect against CSRF
   - Secure sensitive data
   - Follow OWASP Top 10 guidelines

4. **Dependencies**
   - Keep dependencies updated
   - Review security advisories
   - Audit third-party packages

---

## Git Workflow

### Commit Message Format

```
<type>: <subject>

<body>

<footer>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting)
- `refactor`: Code refactoring
- `test`: Test additions or changes
- `chore`: Build process or tooling changes

**Example:**
```
feat: add user authentication system

Implement JWT-based authentication with login and registration endpoints.
Includes password hashing, token generation, and middleware for protected routes.

Closes #123
```

### Commit Guidelines

1. **Atomic Commits**
   - One logical change per commit
   - All tests should pass after each commit
   - Commit related changes together

2. **Commit Message Quality**
   - Clear and descriptive
   - Explain WHY, not just WHAT
   - Reference issues when applicable

3. **Before Committing**
   - Review your changes
   - Run tests
   - Check for debugging code
   - Verify no secrets are included

### Git Operations

**Fetching and Pulling:**
```bash
# Fetch specific branch
git fetch origin <branch-name>

# Pull with retry on network errors
git pull origin <branch-name>
```

**Pushing Changes:**
```bash
# Always use -u flag for first push
git push -u origin <branch-name>

# CRITICAL: Branch must start with 'claude/' and end with session id
# Otherwise push will fail with 403 error
```

**Retry Logic:**
- For network failures, retry up to 4 times
- Use exponential backoff: 2s, 4s, 8s, 16s

---

## Testing Strategy

### Testing Pyramid (To Be Implemented)

```
        /\
       /  \     E2E Tests (Few)
      /----\
     /      \   Integration Tests (Some)
    /--------\
   /          \ Unit Tests (Many)
  /____________\
```

### Test Organization

**To be defined based on technology stack**

- Unit tests location
- Integration tests location
- E2E tests location
- Test naming conventions
- Mock/stub strategies

### Testing Guidelines

1. **Write Tests For:**
   - New features
   - Bug fixes
   - Public APIs
   - Complex logic
   - Edge cases

2. **Test Characteristics:**
   - Fast execution
   - Isolated and independent
   - Repeatable results
   - Clear assertions
   - Descriptive names

3. **Coverage Goals:**
   - To be defined based on project needs
   - Focus on critical paths
   - Don't obsess over 100% coverage

### Running Tests

```bash
# To be defined based on test framework
# npm test
# pytest
# go test
# cargo test
```

---

## Documentation Standards

### Code Documentation

1. **README.md**
   - Project overview
   - Setup instructions
   - Usage examples
   - Contribution guidelines
   - License information

2. **API Documentation**
   - Endpoint descriptions
   - Request/response formats
   - Authentication requirements
   - Example calls
   - Error codes

3. **Architecture Documentation**
   - System design
   - Component interactions
   - Data flow
   - Technology decisions
   - Trade-offs and rationale

### Keeping Documentation Updated

- Update docs when changing functionality
- Document breaking changes
- Keep examples current
- Review docs during code review
- Archive outdated information

### This File (CLAUDE.md)

**When to Update:**
- Major architectural changes
- New coding conventions
- Workflow changes
- Technology stack updates
- Project structure modifications

**Who Updates:**
- AI assistants working on the project
- Human developers for project-wide changes
- Keep it current and accurate

---

## Common Tasks

### For AI Assistants Working on This Repository

#### Task: Adding a New Feature

1. **Read existing code** - Never propose changes without reading relevant files
2. **Use TodoWrite** - Track implementation steps
3. **Make minimal changes** - Only what's requested
4. **Test thoroughly** - Run existing tests, add new ones
5. **Document** - Update relevant docs
6. **Commit clearly** - Follow commit message format

#### Task: Fixing a Bug

1. **Reproduce the bug** - Understand the issue
2. **Locate root cause** - Find the problematic code
3. **Fix minimally** - Don't refactor surrounding code
4. **Add regression test** - Prevent bug from recurring
5. **Verify fix** - Test the specific scenario
6. **Document** - Update changelog if significant

#### Task: Refactoring Code

1. **Have clear objective** - Know what you're improving
2. **Ensure test coverage** - Tests should pass before and after
3. **Small increments** - Make small, safe changes
4. **Preserve behavior** - Don't change functionality
5. **Document decisions** - Explain why refactoring was needed

#### Task: Updating Dependencies

1. **Check changelog** - Review breaking changes
2. **Update incrementally** - One dependency at a time
3. **Run all tests** - Verify compatibility
4. **Update code if needed** - Fix breaking changes
5. **Document** - Note version updates in changelog

#### Task: Writing Documentation

1. **Be clear and concise** - Avoid unnecessary complexity
2. **Include examples** - Show, don't just tell
3. **Keep it current** - Sync with actual code
4. **Consider audience** - Write for the reader
5. **Use proper formatting** - Follow markdown conventions

### Tool Usage Preferences

1. **File Operations**
   - Use `Read` for reading files (not `cat`)
   - Use `Edit` for modifying files (not `sed`)
   - Use `Write` for new files (not `echo >`)

2. **Searching**
   - Use `Grep` for content search (not `grep` command)
   - Use `Glob` for file patterns (not `find`)
   - Use `Task` with `Explore` for codebase exploration

3. **Planning**
   - Always use `TodoWrite` for multi-step tasks
   - Track progress in real-time
   - Mark tasks complete immediately

---

## Key Files Reference

### Configuration Files (To Be Added)

| File | Purpose | When to Modify |
|------|---------|----------------|
| `.gitignore` | Files to exclude from Git | Adding new build artifacts, dependencies |
| `.env.example` | Environment variable template | Adding new config options |
| Package file | Dependencies and scripts | Adding/updating dependencies |
| Build config | Build and bundling settings | Changing build process |
| Test config | Testing framework setup | Changing test settings |

### Core Source Files (To Be Added)

_To be populated as codebase develops_

### Important Directories (To Be Created)

_To be populated as project structure is established_

---

## Project-Specific Notes

### Known Issues

_To be documented as discovered_

### Technical Debt

_To be tracked as identified_

### Future Considerations

_To be added as project evolves_

---

## Getting Help

### For AI Assistants

1. **Uncertain about approach?**
   - Ask the user for clarification
   - Use the `Task` tool with appropriate agents
   - Read existing code patterns

2. **Need more context?**
   - Use `Task` with `Explore` agent
   - Read related files
   - Check documentation

3. **Blocked by configuration?**
   - Ask user to check their settings
   - Provide clear error messages
   - Suggest possible solutions

### For Human Developers

_To be added: Links to internal resources, documentation, team contacts_

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0.0 | 2025-12-04 | Initial CLAUDE.md creation | Claude AI Assistant |

---

## Appendix

### Useful Commands (To Be Populated)

```bash
# Development
# [to be defined]

# Testing
# [to be defined]

# Building
# [to be defined]

# Deployment
# [to be defined]
```

### External Resources

- [GitHub Repository](https://github.com/hafsaahmed614/Booksense)
- Project Documentation: _To be added_
- API Documentation: _To be added_

### Glossary

_To be added as project-specific terms emerge_

---

**Note to AI Assistants:** This document should be treated as a living guide. Update it as the project evolves, new conventions are established, or architectural decisions are made. Always keep it accurate and current.

**Note to Developers:** This file helps AI assistants work more effectively on your codebase. Keep it updated alongside your regular documentation.

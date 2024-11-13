# Contributing to Stylus AssemblyScript SDK

👋 First off, thanks for taking the time to contribute! Your help makes this SDK better for everyone in the Arbitrum ecosystem.

## 🗺️ Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Development Process](#development-process)
- [Pull Request Process](#pull-request-process)
- [Coding Standards](#coding-standards)
- [Testing Guidelines](#testing-guidelines)
- [Documentation](#documentation)
- [Community](#community)

## 📜 Code of Conduct

This project and everyone participating in it are governed by our Code of Conduct. By participating, you agree to uphold this code. Please report unacceptable behavior to [project email].

## 🚀 Getting Started

1. Fork the repository
2. Clone your fork:
```bash
git clone https://github.com/your-username/stylus-assemblyscript-sdk.git
cd stylus-assemblyscript-sdk
```

3. Install dependencies:
```bash
npm install
```

4. Create a new branch:
```bash
git checkout -b feature/your-feature-name
```

## 💻 Development Setup

### Prerequisites

- Node.js (v16 or later)
- npm or yarn
- AssemblyScript toolchain
- Rust toolchain (for testing against Stylus examples)

### Local Development

1. Install development dependencies:
```bash
npm install --save-dev
```

2. Run tests:
```bash
npm test
```

3. Build the project:
```bash
npm run build
```

## 🔄 Development Process

1. Check existing issues and discussions
2. Create an issue for new features/bugs
3. Get feedback on implementation approach
4. Implement your changes
5. Write/update tests
6. Update documentation
7. Submit PR

### Branch Naming

- Features: `feature/description`
- Fixes: `fix/description`
- Documentation: `docs/description`
- Tests: `test/description`

## 🔍 Pull Request Process

1. Update the README.md with details of changes if needed
2. Update the documentation
3. Add tests for new functionality
4. Ensure all tests pass
5. Update the CHANGELOG.md
6. Get at least one code review
7. Squash commits before merging

### PR Title Format

```
type(scope): description

Examples:
feat(storage): add persistent storage implementation
fix(compiler): resolve WASM memory allocation issue
docs(api): update method documentation
```

## 📐 Coding Standards

### General Guidelines

- Follow AssemblyScript best practices
- Use TypeScript-style type annotations
- Keep functions focused and small
- Write descriptive variable names

### Code Style

```typescript
// Good
export class Storage<T> {
  private key: Uint8Array;

  constructor(key: Uint8Array) {
    this.key = key;
  }

  get(): T {
    // Implementation
  }
}

// Bad
export class storage<t> {
  constructor(k: Uint8Array) { this.key=k; }
  get() { /* ... */ }
}
```

## 🧪 Testing Guidelines

### Test Structure

```typescript
describe("Storage", () => {
  it("should store and retrieve values", () => {
    // Setup
    const storage = new Storage<u32>(new Uint8Array([1]));
    
    // Action
    storage.set(42);
    
    // Assert
    expect(storage.get()).toBe(42);
  });
});
```

### Test Coverage Requirements

- Minimum 90% code coverage
- All public APIs must be tested
- Include edge cases
- Test error conditions

## 📚 Documentation

### Documentation Requirements

- JSDoc comments for all public APIs
- README updates for new features
- Example code for new functionality
- Architecture documentation updates
- Clear commit messages

### Documentation Style

```typescript
/**
 * Stores a value in contract storage.
 * @param key - The storage key
 * @param value - The value to store
 * @throws If key is invalid
 * @example
 * ```ts
 * const storage = new Storage<u32>(key);
 * storage.set(42);
 * ```
 */
public set(value: T): void {
  // Implementation
}
```

## 👥 Community

- Join our [Discord](https://discord.gg/example)
- Follow us on [Twitter](https://twitter.com/example)
- Read our [Blog](https://blog.example.com)

### Getting Help

1. Check the documentation
2. Search existing issues
3. Ask in Discord #dev channel
4. Create a new issue

## 🎖️ Recognition

Contributors will be:
- Added to CONTRIBUTORS.md
- Recognized in release notes
- Given credit in documentation

## 📝 License

By contributing, you agree that your contributions will be licensed under the same license as the project.

Thank you for contributing to make Arbitrum development more accessible! 🙏

# Stylus AssemblyScript SDK

A software development kit for writing Arbitrum Stylus smart contracts in AssemblyScript. This SDK allows developers to write, test, and deploy smart contracts to Arbitrum using familiar TypeScript-like syntax while leveraging the performance benefits of WebAssembly.

## 🌟 Features

- Write smart contracts using AssemblyScript syntax
- Type-safe contract development environment
- Compatible with existing Arbitrum Stylus infrastructure
- Efficient WASM compilation
- Built-in testing utilities
- Storage abstractions for easy state management

## 📋 Prerequisites

- Node.js (v16 or later)
- npm or yarn
- Basic understanding of AssemblyScript and blockchain development

## 🚀 Quick Start

1. Install the SDK:
```bash
npm install stylus-assemblyscript-sdk
```

2. Create a new contract:
```typescript
import { contract, external, view, StyledContract, Storage, U256 } from "stylus-assemblyscript-sdk";

@contract()
class SimpleStorage extends StyledContract {
  private value: Storage<U256>;

  constructor() {
    super();
    this.value = new Storage<U256>(new Uint8Array([1]));
  }

  @view()
  getValue(): U256 {
    return this.value.get();
  }

  @external()
  setValue(newValue: U256): void {
    this.value.set(newValue);
  }
}
```

3. Compile your contract:
```bash
npm run asbuild:release
```

## 🏗️ Project Structure

```
stylus-assemblyscript-sdk/
├── src/
│   ├── types.ts          # Core type definitions
│   ├── storage.ts        # Storage abstractions
│   ├── contract.ts       # Base contract class
│   └── decorators.ts     # Contract decorators
├── tests/
│   └── contract.spec.ts  # Test specifications
├── examples/
│   └── simple-storage.ts # Example contracts
└── assembly/
    └── index.ts         # Main entry point
```

## 📚 Core Concepts

### Contracts
Contracts are classes decorated with `@contract()` that extend `StyledContract`. They form the basic unit of deployment on Arbitrum Stylus.

### Storage
The SDK provides type-safe storage abstractions for managing contract state:
```typescript
private balance: Storage<U256>;
```

### Methods
- `@external()`: Methods that can modify contract state
- `@view()`: Read-only methods that don't modify state
- `@payable()`: Methods that can receive ETH

## 🧪 Testing

Run the test suite:
```bash
npm test
```

Write a test:
```typescript
import { SimpleStorage } from "../examples/simple-storage";

describe("SimpleStorage", () => {
  it("should store and retrieve value", () => {
    const contract = new SimpleStorage();
    contract.setValue(42);
    expect(contract.getValue()).toBe(42);
  });
});
```

## 🛠️ Development Workflow

1. Write your contract in AssemblyScript
2. Test using the provided testing framework
3. Compile to WASM using `asbuild`
4. Deploy using Stylus deployment tools

## 🔍 Gas Optimization

The SDK automatically handles:
- Efficient WASM compilation
- Optimal storage layouts
- Gas metering integration

Tips for optimization:
- Use appropriate data types
- Minimize storage operations
- Leverage view functions when possible

## 🤝 Contributing

We welcome contributions! Please see our contributing guidelines for more details.

1. Fork the repository
2. Create a feature branch
3. Submit a pull request

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

## ⚠️ Security

This is alpha software. Use at your own risk. Always audit your contracts before deployment.

## 🙋‍♂️ Support

- Join our [Discord](https://discord.gg/example)
- Read the [Documentation](https://docs.example.com)
- Report [Issues](https://github.com/example/issues)

## 🗺️ Roadmap

- [ ] Complete U256/I256 implementation
- [ ] Add event emission support
- [ ] Implement full ABI encoding/decoding
- [ ] Create deployment tools
- [ ] Add contract upgradeability support

## ✨ Acknowledgements

This SDK is built on top of the Arbitrum Stylus platform and AssemblyScript compiler. Special thanks to the teams behind these projects.

# JavaScript/TypeScript Strict Configuration

## JavaScript-Specific Installation

```bash
npm install --save-dev typescript
```

Or for projects using Yarn:

```bash
yarn add --dev typescript
```

## React/JSX Configuration

For React projects, extend the base configuration with JSX settings:

```json
{
  "compilerOptions": {
    "jsx": "react-jsx",
    "allowSyntheticDefaultImports": true,
    "esModuleInterop": true
  }
}
```

## Node.js Configuration

For Node.js projects, add module resolution settings:

```json
{
  "compilerOptions": {
    "module": "commonjs",
    "target": "es2020",
    "moduleResolution": "node",
    "resolveJsonModule": true
  }
}
```

## Build Integration

Integrate with common JavaScript build tools:

- **npm scripts**: Add `"typecheck": "tsc --noEmit"` to package.json scripts
- **Webpack**: Ensure ts-loader or babel-loader with TypeScript preset is configured
- **Vite**: TypeScript support is built-in, no additional configuration needed
- **Next.js**: Built-in TypeScript support, just ensure tsconfig.json exists

## JavaScript-Specific Error Patterns

Common fixes for JavaScript/TypeScript projects:

1. **Import/Export**: Use proper ES module syntax with type imports when needed
2. **DOM Types**: Install @types/node or configure lib array for proper DOM/Node types
3. **Third-party Libraries**: Install corresponding @types packages for untyped libraries
4. **Dynamic Imports**: Use proper typing for dynamic imports and lazy loading

## Verification

```bash
npx tsc --noEmit
npm run typecheck
```
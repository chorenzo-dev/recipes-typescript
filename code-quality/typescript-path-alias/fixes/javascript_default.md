# Setting up TypeScript Path Alias

## TypeScript Configuration

Add or update the `tsconfig.json` file with path mapping configuration:

```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "~/*": ["src/*"]
    }
  }
}
```

If using a different source directory than `src/`, adjust the path mapping accordingly.

## Build Tool Configuration

### For Vite projects
Add alias configuration to `vite.config.js` or `vite.config.ts`:

```javascript
import { defineConfig } from 'vite'
import path from 'path'

export default defineConfig({
  resolve: {
    alias: {
      '~': path.resolve(__dirname, 'src')
    }
  }
})
```

### For Webpack projects
Add alias configuration to `webpack.config.js`:

```javascript
const path = require('path')

module.exports = {
  resolve: {
    alias: {
      '~': path.resolve(__dirname, 'src')
    }
  }
}
```

## Update Existing Imports

Find and replace all relative imports that navigate up from the source directory with the new alias:

```bash
# Find TypeScript files with relative imports going up from src
find . -name "*.ts" -o -name "*.tsx" | xargs grep -l "\.\./.*" | grep -E "src/"
```

For each file found, replace imports that reference files outside the current directory structure with the alias:

```typescript
// Replace patterns like:
import { Component } from '../../../components/Component'
import { utils } from '../../utils/helpers'
import config from '../../../config/app.config'

// With:
import { Component } from '~/components/Component'
import { utils } from '~/utils/helpers' 
import config from '~/config/app.config'
```

Focus on replacing imports that use `../` to navigate up to the source root level.

## Verification

Test the alias by verifying that imports resolve correctly:

```typescript
// Example of converted import
import { Component } from '~/components/Component'
```

Ensure the TypeScript compiler and your build tool both resolve the alias correctly without errors. Run the TypeScript type checker to verify all imports resolve properly:

```bash
# First try the typecheck script if available
npm run typecheck
```

If the project doesn't have a typecheck script in package.json, use TypeScript directly:

```bash
# Fallback to direct TypeScript type checking
npx tsc --noEmit
```
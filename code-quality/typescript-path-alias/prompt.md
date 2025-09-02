## Goal

Configure a top-level path alias (~) to enable clean imports from the project's source root directory.

## Investigation

1. **Check for existing TypeScript configuration**
   - Look for tsconfig.json or tsconfig.*.json files in the project root
   - Examine any existing "paths" configuration in compilerOptions
   - Note the "baseUrl" setting if present

2. **Identify source directory structure**
   - Determine the main source directory (commonly src/, lib/, or project root)
   - Check for existing import patterns in TypeScript files
   - Identify the intended root for the alias mapping

3. **Check bundler/build tool configuration**
   - Look for webpack.config.js, vite.config.js, rollup.config.js, or similar build configuration
   - Check if path aliases are already configured in the bundler
   - Identify if additional bundler configuration is needed for the alias

4. **Examine existing import statements**
   - Review current relative import patterns (e.g., ../../../components)
   - Check if any path aliases are already in use
   - Identify files that would benefit from the alias

## Expected Output

This recipe relies on the automatic `typescript-path-alias.applied` field to indicate successful configuration.
# Setting up TypeScript Path Alias

## TypeScript Configuration

Update the `tsconfig.json` file with path mapping configuration. Add or update the compilerOptions section to include baseUrl as "." and paths mapping with "~/*": ["src/*"]. If using a different source directory than src/, adjust the path mapping accordingly.

## Build Tool Configuration

### For Vite projects
Add alias configuration to `vite.config.js` or `vite.config.ts`. In the resolve section, add an alias mapping '~' to the src directory path using `path.resolve(__dirname, 'src')`.

### For Webpack projects
Add alias configuration to `webpack.config.js`. In the resolve section, add an alias mapping '~' to the src directory path.

## Update Existing Imports

Find and replace all relative imports that navigate up from the source directory with the new alias. Use this command to find TypeScript files: `find . -name "*.ts" -o -name "*.tsx" | xargs grep -l "\.\./.*" | grep -E "src/"`

For each file found, replace imports that reference files outside the current directory structure with the alias. Convert patterns like `../../../components/Component` to `~/components/Component`. Focus on replacing imports that use `../` to navigate up to the source root level.

## Verification

Test the alias by creating example imports using the ~ alias pattern. Ensure the TypeScript compiler and your build tool both resolve the alias correctly without errors. 

Run the TypeScript type checker to verify all imports resolve properly. First try: `npm run typecheck`

If the project doesn't have a typecheck script in package.json, use: `npx tsc --noEmit`
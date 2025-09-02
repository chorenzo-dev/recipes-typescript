## Goal

Configure TypeScript with the strictest compiler options to catch errors early and enforce best practices.

## Investigation

1. **Locate TypeScript configuration**
   - Check for tsconfig.json in the project root
   - Look for TypeScript configuration in package.json
   - Identify any existing compiler options that may conflict

2. **Check current TypeScript setup**
   - Verify TypeScript is installed as a dependency
   - Check if any build tools or frameworks override TypeScript settings
   - Identify source directories and file patterns covered by TypeScript

3. **Assess project requirements**
   - Identify the project's framework and structure
   - Note any existing type-related code patterns
   - Check for potential compatibility considerations

## Expected Output

This recipe relies on the automatic `strict-typescript-config.applied` field to indicate successful configuration.
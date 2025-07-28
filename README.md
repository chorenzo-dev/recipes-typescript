# @chorenzo/recipes-typescript

TypeScript-focused recipes for the Chorenzo engine - specialized automation recipes for TypeScript development workflows.

## Recipe Documentation

For complete documentation on recipe structure, file formats, design principles, and contributing guidelines, see:

**[Recipe Documentation](https://github.com/chorenzo-dev/engine/blob/main/docs/recipes.md)**

## TypeScript-Specific Considerations

- **Compiler Options**: Recipes should detect and respect existing `tsconfig.json` configurations
- **Module Systems**: Support for both CommonJS and ESM module resolution
- **Type Definitions**: Proper handling of `@types/*` packages and declaration files
- **Build Targets**: Awareness of different compilation targets and output formats
- **Monorepo Support**: Compatible with TypeScript project references and workspace configurations

## Contributing

1. Create a folder matching your recipe ID (kebab-case)
2. Add `metadata.yaml` with at least: id, summary, ecosystems, provides
3. Write `prompt.md` with Goal, Investigation, and Expected Output sections
4. Add variant-specific fix prompts under `fixes/`
5. Ensure all paths in metadata.yaml match actual file locations
6. Test recipes against common TypeScript project structures

## Open Issues

- Recipe validation CLI (`chorenzo recipes lint`) to be implemented in the main CLI repository
- TypeScript-specific recipe categories and organization patterns
# Contributing to remove-homebrew-action

Thank you for your interest in contributing to this project!

## Development

This action is implemented as a composite action that uses shell scripts to remove Homebrew from macOS runners.

### Structure

- `action.yml` - Main action definition with metadata and the removal script
- `README.md` - User-facing documentation
- `.github/workflows/test.yml` - Integration test workflow

### Testing

The action can be tested by running the workflow in `.github/workflows/test.yml` on a macOS runner. The test:

1. Checks out the repository
2. Runs the action to remove Homebrew
3. Verifies that Homebrew has been successfully removed

### Making Changes

When making changes to the action:

1. Update `action.yml` if changing the removal logic
2. Update `README.md` if changing how users interact with the action
3. Ensure YAML files are properly formatted (no trailing spaces)
4. Test on actual macOS runners when possible

### Code Style

- Use proper shell script best practices
- Include comments for complex operations
- Handle errors gracefully with `|| true` where appropriate
- Use `sudo` only when necessary

## Reporting Issues

Please report issues on the GitHub issue tracker, including:

- The macOS runner version (macos-latest, macos-13, etc.)
- Any error messages
- Your workflow configuration

## Pull Requests

Pull requests are welcome! Please ensure:

- Your changes work on macOS runners
- Documentation is updated if needed
- YAML files pass linting (`yamllint -d relaxed`)

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

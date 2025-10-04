# remove-homebrew-action

A GitHub Action to remove Homebrew from macOS runners to avoid conflicts.

## Overview

This action removes Homebrew from GitHub-hosted macOS runners. This is useful when you need to avoid conflicts between Homebrew packages and other package managers or build systems.

## Usage

Add this action to your workflow before steps that might conflict with Homebrew:

```yaml
name: Build

on: [push, pull_request]

jobs:
  build:
    runs-on: macos-latest
    steps:
      - name: Remove Homebrew
        uses: xpack/remove-homebrew-action@v1
      
      - name: Checkout code
        uses: actions/checkout@v4
      
      - name: Build project
        run: ./build.sh
```

## When to Use This Action

Use this action when:

- You're using alternative package managers (like MacPorts)
- You need a clean environment without Homebrew
- You want to avoid conflicts between Homebrew and your build system
- You need to reduce disk space usage on the runner

## What It Does

This action:

1. Checks if the runner is macOS (skips on other platforms)
2. Verifies Homebrew is installed
3. Uninstalls all Homebrew packages and casks
4. Removes Homebrew installation directories
5. Cleans up Homebrew caches and logs

## Platform Support

- ✅ macOS runners (macos-latest, macos-13, macos-12, etc.)
- ⚠️ Skips automatically on Linux and Windows runners

## Notes

- This action requires `sudo` permissions (available by default on GitHub-hosted runners)
- The action is idempotent - it's safe to run multiple times
- This action only removes Homebrew, not packages installed via other means

## License

MIT - See [LICENSE](LICENSE) for details.

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

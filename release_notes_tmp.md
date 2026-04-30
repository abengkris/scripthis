### Fixed
- **Help Command Crash:** Added a fallback mechanism to `/scripthis:help` so it defaults to English if the user runs the command before initializing a project (`project.json` is missing).
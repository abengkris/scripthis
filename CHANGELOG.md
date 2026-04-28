# Changelog

All notable changes to this project will be documented in this file.

## [3.0.0] - Current Release
### Added
- **6 Advanced Story Frameworks (Skills):** Added expert-level analysis for Save the Cat, Hero's Journey, Story Circle, 8-Sequence Approach, Enneagram, and Pixar's 22 Rules.
- **Interactive Wizards:** Commands like `/setup`, `/character`, and `/review` now use the `ask_user` tool for interactive multiple-choice forms.
- **Draft Vault:** Added `/save_draft` command for Git-based version control of scripts.
- **Research Assistant:** Added `/research` command with live Google Web Search integration.
- **PDF Export:** Added `/export` command leveraging `afterwriting` to generate industry-standard PDFs.

### Changed
- **Architecture Overhaul:** Removed the Node.js MCP server entirely for a lightweight, dependency-free installation. The extension now relies 100% on Gemini CLI's native, powerful toolset (`read_file`, `write_file`, `run_shell_command`, etc.).
- **6-P Workflow:** Refined the core protocol to track Pitch, World, People, Plan, Pages, and Polish.

## [2.0.0] - Previous Iteration
### Added
- Created the initial 6-P Workflow checklist and `/workflow` command.
- Added `project.json` for metadata tracking.

## [1.0.0] - Initial Concept
### Added
- Initial creation of the Showrunner persona in `GEMINI.md`.
- Basic `/setup`, `/write`, `/character`, and `/review` commands using a custom MCP server.
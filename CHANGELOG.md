# Changelog

All notable changes to this project will be documented in this file.

## [3.2.0] - Genre-Specific Templates Update
### Added
- **Genre Templates:** The `/scripthis:setup` command now automatically populates `outline.md` and `world_rules.md` with professional templates based on the chosen genre (Horror, Sitcom, Sci-Fi, Drama, or Action).
- **Template Library:** Created a new `templates/` directory to store specialized story structures and worldbuilding rules.

## [3.1.0] - Dialogue Doctor & Subtext Update
### Added
- **Dialogue Doctor:** Introduced the `/scripthis:dialogue_doctor` command and corresponding skill. The AI can now perform a "Subtext Audit" to fix boring, literal dialogue using professional techniques like Deflection, Sarcasm, and Metaphor.
- **Voice Specialization:** Improved the AI's ability to differentiate character voices based on their unique vocabulary and syntax.

## [3.0.5] - Time Machine Update
### Added
- **Time Machine:** Introduced the `/scripthis:restore` command, allowing writers to view draft history and roll back the entire project to a previous snapshot.
- **Improved Version Control:** Refined the integration between drafting and the Git-based Studio Vault.

## [3.0.4] - Scene Navigator Update
### Added
- **Scene Navigator:** Introduced the `/scripthis:scenes` command, allowing writers to instantly list and analyze all sluglines/scene headings in their script.
- **Pacing Awareness:** The AI now analyzes the balance between INT/EXT scenes and identifies pacing gaps between scenes.

## [3.0.3] - Context & Research Update
### Added
- **Multi-Language Support:** Added language preference selection during `/setup` and enforced consistency in `project.json`.
- **Mandatory Research Protocol:** AI now proactively uses web tools to verify facts and jargon, saving findings to the `reference/` folder.

## [3.0.2] - The Ultimate Fountain Syntax Update
### Added
- **Complete Fountain Specification:** Integrated 100% of the Fountain syntax rules into the AI's core instructions, including:
    - Advanced Scene Headings (`EST.`, `I/E.`, `INT./EXT.`).
    - Specialized Dialogue (Dual Dialogue with `^`, Lyrics with `~`).
    - Professional Formatting (Centered text `> <`, Page Breaks `===`, Notes `[[ ]]`, Boneyard `/* */`).
    - Structural Metadata (Sections `#`, Synopses `=`).
- **Standardized Title Page:** Refined the `/setup` command to generate industry-standard Fountain Title Pages.

## [3.0.1] - Patch Update
### Fixed
- **Anti-Hallucination Protocol:** Added a critical safety check to the `/write` command. The AI will now stop and require the user to define a character if they appear in a scene but lack a Character Bible, preventing spontaneous AI "voice drift".
- **Version Bump:** Updated `gemini-extension.json` version to properly reflect the latest state.

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
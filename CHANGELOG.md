# Changelog

All notable changes to this project will be documented in this file.

## [3.7.0] - Precision Rewriting & Stability Update
### Added
- **Precision Rewriting:** Introduced the `/scripthis:rewrite` command. This enables surgical editing of specific scenes using `grep_search` and `replace` to avoid full-file overwrites and context window truncation.
- **Outline Adaptation Protocol:** The AI now proactively asks to update `outline.md` whenever a newly written or rewritten scene deviates from the original plan.
- **Export Fallback:** Added a fallback mechanism to `/scripthis:export` to convert the script to a clean `.txt` file if Node.js (`npx`) is not installed on the system.

### Changed
- **Safe Appending:** Refactored the `/scripthis:write` command to use native file tools (`read_file` -> `write_file`) for appending new scenes, removing the dependency on unsafe shell commands (`echo >>`).
- **Explicit Workflow Tracking:** Improved `/scripthis:setup` and `/scripthis:character` to explicitly update and check off stages (PITCH and PEOPLE) in `workflow.md`.
- **Documentation Update:** Updated `README.md` to include the new `/rewrite` command in the commands table.

## [3.6.9] - Skill and Constraint Fixes
### Fixed
- **World Rules Validation:** Added missing `read_file` step to `character.toml` to ensure the AI actually reads `world_rules.md` before applying negative constraints regarding backstory consistency.
- **Skill Activation Header:** Added missing activation header and `## Instructions for AI` to `fountain-syntax/SKILL.md` so the AI correctly adopts the persona and knows how to apply the formatting rules.

## [3.6.8] - Hotfix Update
### Fixed
- **TOML Parsing:** Fixed a syntax error with trailing characters in the `review.toml` command file that prevented the extension from loading correctly.

## [3.6.7] - Cleanup Update
### Fixed
- **Artifact Removal:** Removed accidentally tracked `release_notes_tmp.md` file from the repository.

## [3.6.6] - Review Formatting Update
### Added
- **Strict Output Format:** Enforced a standardized structure for the `/scripthis:review` command's coverage report (Logline Analysis, Structural Assessment, Character Arcs, Dialogue Notes, and Rating). This guarantees consistency across drafts and AI sessions.

## [3.6.5] - Skill Resilience Update
### Added
- **Skill Fallback Behavior:** Added explicit instructions to `/write`, `/review`, and `/dialogue_doctor` commands. If the `activate_skill` tool is unavailable or fails, the AI is now instructed to gracefully fall back on its inherent knowledge of the required frameworks (e.g., Fountain syntax, subtext mechanics, story structures) rather than crashing or skipping the step.

## [3.6.4] - Review Command Guard Update
### Added
- **Review Guard Clause:** Added an initial validation step to `/scripthis:review` to check if a `.fountain` script file actually exists before attempting to provide coverage, preventing AI hallucinations or crashes on empty projects.

## [3.6.3] - Onboarding Stability Update
### Fixed
- **Help Command Crash:** Added a fallback mechanism to `/scripthis:help` so it defaults to English if the user runs the command before initializing a project (`project.json` is missing).

## [3.6.2] - Prompt Safety Update
### Added
- **Negative Constraints:** Added strict "Do NOT" rules to core commands (`/write`, `/review`, `/character`) to prevent AI hallucination, unapproved world-building, and "voice drift". For instance, the AI will now forcefully refuse to write more than 5 pages without user approval or invent dialogue for undefined characters.

## [3.6.1] - Prompt Clarity Update
### Fixed
- **Instruction Ambiguity:** Replaced ambiguous shell-like variable placeholders (e.g., `${USER_INPUT}`, `{{args}}`) in `save_draft.toml` and `write.toml` with explicit natural language instructions to ensure the AI interprets user inputs accurately across different sessions and models.

## [3.6.0] - Context Efficiency Update
### Added
- **Fountain Syntax Skill:** Extracted all Fountain formatting and syntax rules from `GEMINI.md` into a new, on-demand `fountain-syntax` skill to significantly reduce the persistent context window load.

### Changed
- **Optimized Prompts:** Updated `/scripthis:write` and `/scripthis:review` to dynamically load the `fountain-syntax` skill only when needed, preventing "lost in the middle" context truncation on longer scripts.

## [3.5.2] - Workflow Stability Update
### Fixed
- **Filename Quoting:** Updated `/scripthis:workflow` to safely quote the `.fountain` filename during line-counting to prevent shell errors with spaces.
- **Workflow Examples:** Corrected a misleading "Next Action" example in `/scripthis:workflow` to accurately reflect the studio workflow logic.

## [3.5.1] - Pacing and Progress Tracking Update
### Added
- **Pacing Guidelines:** Added explicit pacing rules for Stage Play, Sitcom (30 min), and general Genre notes to `GEMINI.md`.
- **Progress Tracking:** Updated `/scripthis:workflow` to actively estimate the script's page count and report progress against the genre target.

## [3.5.0] - Release Ready Cleanup
### Added
- **Sitcom Genre:** Added 'Sitcom' as a distinct genre option in the Setup Wizard, correctly mapping to its dedicated template folder.

### Fixed
- **Documentation Sync:** Updated `GEMINI.md` to include all current custom commands (`/logline`, `/dialogue_doctor`, `/moodboard`, `/help`).
- **Key Features:** Added 'Three-Act Structure' to the advanced story frameworks list in `README.md`.
- **Version Headers:** Synchronized the manual version in `help.toml` to v3.5.0.
- **Copyright:** Updated `LICENSE` year to 2024-2026.

## [3.4.1] - Maintenance & Cleanup Update
### Fixed
- **Artifact Removal:** Fixed trailing `file_path:` artifact in `logline.toml`.
- **Logic Sequence:** Fixed duplicate step numbering in `write.toml`.
- **Skill Registration:** Correctly registered `three-act-structure` in `GEMINI.md`.
- **Docs Update:** Added `/logline` documentation to `help.toml` and `README.md`.
- **Template Consistency:** Aligned Sci-Fi and Sitcom templates with specific world-building criteria and added missing Comedy template folder.

## [3.4.0] - Safety & Workflow Refinement Update
### Added
- **Three-Act Structure Skill:** Added a fundamental story framework skill (`three-act-structure`) for more accessible pacing and structure analysis.
- **Logline Workshop:** Introduced the `/scripthis:logline` command to refine and validate loglines based on Protagonist, Goal, Conflict, and Stakes.

### Fixed
- **.gitignore Conflict:** Cleaned up the extension's `.gitignore` to prevent conflicts with the user's project files. Setup now initializes a project-local `.gitignore`.
- **Shell Injection Security:** Added strict input sanitization and shell escaping/quoting for user input in `save_draft.toml` and other commands.
- **Restore Safety:** Added `git stash` and explicit confirmation step in `/scripthis:restore` to prevent data loss.
- **Export Error Handling:** Added system requirement verification (Node.js/npx) and graceful error reporting for `/scripthis:export`.
- **Review Persistence:** Added an optional save feature to `/scripthis:review` to store coverage reports in `drafts/`.
- **Multilingual Support:** Fixed `help.toml` to dynamically translate the studio manual based on `project.json` language.
- **Writing Validation:** Added pre-check for `outline.md` in `/scripthis:write` to ensure project environment is valid.
- **TV Series Support:** Added series naming conventions to `world_rules.md` templates for TV Pilot projects.
- **Documentation:** Fixed numbering in `GEMINI.md`, removed artifacting at the end of files, and updated `README.md` with requirements and skill fallback notes.

## [3.3.0] - Moodboard Generator Update
### Added
- **Moodboard Integration:** Introduced the `/scripthis:moodboard` command. The AI now acts as a Concept Artist, reading character bibles and world rules to generate hyper-detailed image prompts for tools like Midjourney or DALL-E.
- **Visual Synthesis:** The AI can now translate narrative atmosphere into technical photography and cinematography terms (lighting, lens type, style).

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
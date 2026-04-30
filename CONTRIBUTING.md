# Contributing to ScripThis

First off, thank you for considering contributing to ScripThis! It's people like you that make ScripThis a powerful tool for screenwriters everywhere.

## Where can I contribute?

1. **Adding New Skills:** Are you an expert in a specific storytelling framework (e.g., The Snowflake Method, Truby's 22 Building Blocks)? You can add a new skill!
   - Create a new folder in `skills/` (e.g., `skills/snowflake-method/`).
   - Add a `SKILL.md` file explaining the framework and instructions for the AI.
2. **Improving Commands:** Have an idea for a new command? Create a new `.toml` file in `commands/scripthis/` using the existing syntax.
3. **Bug Fixes:** Notice the AI drifting or hallucinating? Help us refine the prompt in `GEMINI.md` or the specific command `.toml` files.

## How to submit your changes

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/amazing-new-skill`).
3. Make your changes and test them locally using `gemini extension install .`
4. Commit your changes (`git commit -m 'Add The Snowflake Method skill'`).
5. Push to the branch (`git push origin feature/amazing-new-skill`).
6. Open a Pull Request on GitHub.

## Code of Conduct
Please be respectful and constructive in your feedback and contributions. We are building a collaborative Writer's Room!
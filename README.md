# 🎬 ScripThis: AI-Powered Professional Screenwriting Suite

**ScripThis** is a high-performance Gemini CLI extension designed for professional screenwriters and showrunners. It transforms an LLM into a "Digital Showrunner" that manages project metadata, character bibles, world rules, and industry-standard formatting.

Unlike standard AI writing tools, ScripThis uses **Grounding and State-Awareness** to ensure your script stays consistent in voice, theme, and pacing from the first logline to the final polish.

---

## 🚀 Key Features

*   **The 6-P Workflow:** A milestone-driven system (Pitch, World, People, Plan, Pages, Polish) that keeps your project moving through the professional development lifecycle.
*   **Genre-Specific Templates:** Automatically populates your outline and world rules with professional structures tailored for Horror, Sci-Fi, Sitcom, Drama, and Action.
*   **Fountain Native:** Generates and reads strictly formatted `.fountain` files, compatible with industry software like Final Draft, Fade In, and Highland 2.
*   **Character Grounding:** Maintains deep character bibles that the AI references before every line of dialogue to prevent "voice drift."
*   **Studio-Grade Coverage:** A `/review` command that interactively analyzes your script. Choose from General Coverage, or advanced frameworks like the "Hero's Journey", "Save the Cat", "Story Circle", and "8-Sequence Approach".
*   **Interactive Wizards:** Uses the `ask_user` tool for a sleek setup, character creation, review selection, and moodboard generation.
*   **Moodboard Integration:** Automatically reads your bibles and world rules to generate highly detailed prompts for image generators like Midjourney.
*   **Advanced Story Frameworks (Skills):** Access a virtual Writer's Room with skills built-in for: Three-Act Structure, Save the Cat, Hero's Journey, Dan Harmon's Story Circle, 8-Sequence Approach, Enneagram, Pixar's 22 Rules, and Dialogue Doctor.

---

## 🛠 Commands

| Command | Action |
| :--- | :--- |
| `/scripthis:setup` | Launches the Project Wizard to define Title, Genre, and Format. |
| `/scripthis:workflow` | Summarizes project status and identifies the next professional milestone. |
| `/scripthis:character` | Launches the Character Wizard to build a grounded cast bible. |
| `/scripthis:write` | Drafts the next scene or sequence based on your approved outline. |
| `/scripthis:review` | Provides a "Studio Coverage" report with structural and dialogue analysis. |
| `/scripthis:scenes` | Displays an instant summary of all scene headings (Sluglines) in your script. |
| `/scripthis:export` | Exports the current `.fountain` script to a professional PDF file. |
| `/scripthis:research`| Performs live web research and fact-checking for your script. |
| `/scripthis:save_draft`| Secures your script's current state into a Git-based "Draft Vault" for safe rewriting. |
| `/scripthis:restore`   | Restores your script to a previous version from the Studio Vault (Time Machine). |
| `/scripthis:logline`   | Refines and validates your story's logline against professional pillars. |
| `/scripthis:dialogue_doctor` | Polishes scene dialogue to add subtext and remove "on-the-nose" lines. |
| `/scripthis:moodboard` | Generates detailed image prompts to visualize characters and locations. |
| `/scripthis:help` | Displays the Studio Manual and Pro-Tips for best results. |

---

## 📂 Project Structure

ScripThis organizes your project into a professional studio hierarchy:

```text
project_root/
├── characters/        # Markdown files for every character's voice and history.
├── reference/         # Research and world-building notes.
├── drafts/            # Older versions of your script.
├── project.json       # Metadata (Genre, Format, Logline).
├── workflow.md        # The 6-P milestone tracker.
├── outline.md         # Your scene-by-scene beat sheet.
├── world_rules.md     # The "Project Bible" for setting consistency.
└── [title].fountain   # Your main industry-standard script file.
```

---

## 💻 Installation & Setup

### 1. Requirements
*   **Gemini CLI v0.5.0 or higher** (Required for `activate_skill` functionality).
*   *(Optional)* **Node.js/npm** if you want to use the `/scripthis:export` command (it uses `npx afterwriting` to generate PDFs).

*Note: ScripThis utilizes advanced AI skills. If a skill is not found, the system will proceed with standard prompt-based intelligence. Please ensure your environment is updated to support extension-level skills.*

### 2. Local Installation
Clone this repository to your local machine and run the following in the project root to link the extension to your Gemini CLI:

```bash
gemini extension install .
```

---

## 🖋 Philosophy: "The Showrunner Method"
ScripThis does not try to write your script in one go. It uses the **Incremental Drafting** method. By writing 3-5 pages at a time and constantly cross-referencing your `outline.md` and `character` files, it ensures that the AI's output is as sharp on page 90 as it was on page 1.

---
*Created for writers who want the power of AI with the control of a professional studio.*



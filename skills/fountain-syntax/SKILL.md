# Fountain & Industry Standards
- **Scene Headings (Slugging):** Must be ALL CAPS and start with one of the following exact prefixes to be recognized as a new scene:
  - `INT.` (Indoor scene, e.g., `INT. BRICK'S ROOM - DAY`)
  - `EXT.` (Outdoor scene, e.g., `EXT. BRICK'S POOL - DAY`)
  - `EST.` (Establishing scene, e.g., `EST. CITY - NIGHT`)
  - `INT./EXT.` or `INT/EXT.` (Indoor/Outdoor scene, e.g., `INT./EXT. RONNA'S CAR - NIGHT [DRIVING]`)
  - `I/E.` (Abbreviated Indoor/Outdoor, e.g., `I/E. RONNA'S CAR - NIGHT [DRIVING]`)
- **Transitions:** Must be ALL CAPS, flush right (in standard rendering), and end with `TO:` (e.g., `CUT TO:`, `SMASH CUT TO:`).
- **Action Lines:** Any paragraph that isn't a Scene Heading, Character, Dialogue, or Transition. Write in the "present tense" and keep paragraphs under 4 lines for readability.

# Analysis Framework (Formatting Elements)
- **Dialogue:** Any text following a Character or Parenthetical element. Avoid "walls of text."
- **Parenthetical:** Wrapped in `( )` and placed immediately below a Character or Dialogue element (e.g., `(starting the engine)`).
- **Dual Dialogue:** Dual, or simultaneous, dialogue is expressed by adding a caret `^` immediately after the second Character element (e.g., `STEEL^`).
- **Lyrics:** Lyric lines must start with a tilde `~` (e.g., `~Willy Wonka! Willy Wonka!`).
- **Formatting:** Strictly use Fountain syntax. 
- **Title Page:** Must be the first thing in the `.fountain` document. Uses key: value pairs (e.g., `Title:`, `Author:`, `Draft date:`, `Contact:`).
- **Centered Text:** Bracketed with greater/less-than signs (e.g., `>THE END<`).
- **Emphasis:**
  - Italics: `*italics*`
  - Bold: `**bold**`
  - Bold Italics: `***bold italics***`
  - Underline: `_underline_`
- **Page Breaks:** Indicated by a line containing three or more consecutive equal signs `===`.
- **Notes:** Inline or block notes are enclosed in double brackets (e.g., `[[Or did we think of actual names?]]`).
- **Boneyard (Ignore Text):** To hide text from the final render, wrap it in `/*` and `*/` (e.g., `/* INT. GARAGE - DAY */`).
- **Sections:** Created by preceding a line with one or more `#` signs (e.g., `# Act`, `## Sequence`).
- **Synopses:** Single-line descriptions of sections or scenes, prefixed by an equal sign `=` (e.g., `= Set up the characters.`).
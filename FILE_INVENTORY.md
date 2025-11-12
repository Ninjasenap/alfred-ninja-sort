# File Inventory - Alfred Ninja Sort

This document provides a comprehensive inventory of all files in the Alfred Ninja Sort project.

## Project Overview
**Ninja Sort** is an Alfred workflow that sorts text alphabetically. Users can select text and use a hotkey to sort paragraphs alphabetically, with special support for Scandinavian characters.

---

## Core Files

### `info.plist`
**Type:** XML Property List
**Purpose:** Alfred workflow configuration file
**Description:** Contains the complete workflow definition including:
- Bundle ID: `se.ninjasmurf.alfred.ninjasort`
- Workflow metadata (name, description, version 1.0.1)
- Node connections defining the workflow logic
- Embedded scripts:
  - **Python script** for standard alphabetical sorting (strips whitespace and sorts lines)
  - **AppleScript** for Scandinavian character sorting (custom sort algorithm)
- Hotkey trigger configuration (default: Cmd+Ctrl+Shift+J)
- Conditional logic to choose between sorting methods based on language settings
- User configuration options for Scandinavian letter support
- Clipboard output with autopaste functionality

**Key Components:**
- Hotkey trigger node
- Conditional node (checks for Scandinavian locale)
- Python sorting script (UTF-8 compatible)
- AppleScript sorting script (handles special characters)
- Clipboard output node

---

### `README.md`
**Type:** Markdown Documentation
**Purpose:** Project documentation and user guide
**Description:** Provides:
- Project overview and description
- Installation instructions
- Download link to the workflow release (v1.0.1)
- Usage instructions with visual examples
- Screenshots showing before/after sorting

---

### `LICENSE`
**Type:** Text
**Purpose:** Software license
**Description:** Contains the complete GNU General Public License v3.0 (GPL-3.0). This is a copyleft license that ensures the software remains free and open source. Users are free to use, modify, and distribute the software under the same license terms.

---

### `icon.png`
**Type:** PNG Image
**Purpose:** Workflow icon
**Description:** Visual icon displayed in Alfred for the Ninja Sort workflow. This helps users identify the workflow in Alfred's interface. File size: 67,891 bytes.

---

### `.gitignore`
**Type:** Git Configuration
**Purpose:** Specifies intentionally untracked files
**Description:** Excludes the following from version control:
- `.DS_Store` - macOS Finder metadata files
- `prefs.plist` - User-specific workflow preferences (local settings only)

---

## Project Structure

```
alfred-ninja-sort/
├── .git/                 # Git repository metadata
├── .gitignore           # Git ignore rules
├── LICENSE              # GNU GPL v3.0 license
├── README.md            # Documentation
├── icon.png             # Workflow icon
└── info.plist           # Alfred workflow configuration
```

---

## Technical Details

### Workflow Logic
1. User selects text and triggers hotkey
2. Selected text is passed to a conditional node
3. Based on the `scandinavian` variable setting:
   - **If enabled (sv_SE)**: Uses AppleScript for proper Scandinavian character sorting
   - **If disabled**: Uses Python for standard UTF-8 sorting
4. Text is trimmed and sorted
5. Result is copied to clipboard and auto-pasted

### Language Support
- **Standard mode**: Python-based sorting using `sorted()` with case-insensitive comparison
- **Scandinavian mode**: AppleScript-based custom sorting algorithm that properly handles characters like å, ä, ö

### Dependencies
- macOS with Alfred (Powerpack required)
- Python runtime (built into macOS)
- AppleScript runtime (built into macOS)

---

## File Count Summary
- **Total files**: 5 tracked files
- **Configuration files**: 2 (info.plist, .gitignore)
- **Documentation files**: 2 (README.md, LICENSE)
- **Asset files**: 1 (icon.png)

---

**Last Updated:** 2025-11-12
**Project Version:** 1.0.1
**Author:** henrik@ninjasmurf.se

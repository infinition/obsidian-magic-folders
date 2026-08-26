<p align="center">
  <img src=".github/obsidian-magic-folders.png" alt="Magic Folders for Obsidian icon" width="128">
</p>

# Magic Folders for Obsidian

[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) ![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=flat&logo=typescript&logoColor=white) [![Release](https://img.shields.io/github/v/release/infinition/obsidian-magic-folders?style=flat)](https://github.com/infinition/obsidian-magic-folders/releases) [![Obsidian Plugin](https://img.shields.io/badge/Obsidian-Plugin-7C3AED?style=flat&logo=obsidian&logoColor=white)](https://obsidian.md/plugins?id=magic-folders) [![Buy Me a Coffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-ffdd00?style=flat&logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/infinition)

Virtual smart folders that automatically group files by tag, link, folder path, file extension, or frontmatter property. Files are never moved or copied. Magic Folders are views, not real directories.

---

## Features

- Virtual folders in the file explorer that update automatically when files change.
- Filter types: tags, internal links (`[[Note]]`), folder paths, file extensions, frontmatter key:value.
- Customizable name, icon (30+ options), color (15 presets), sort order, and direction per folder.
- Sort by name, modified date, created date, type, or size.

---

## Filter syntax

| Type | Example |
|------|---------|
| Tag | `#Todo` |
| Link | `[[Projects]]` |
| Folder | `folder:Daily Notes` |
| Extension | `.pdf` |
| Frontmatter | `status:done` |

Multiple filters can be combined.

---

## Examples

**Todo folder**: all files tagged `#Todo` or `#WIP`, sorted by modified date descending.

**Project hub**: all files linking to a `[[Projects]]` note.

**Recent daily notes**: files in `folder:Daily Notes`, sorted by modified date descending.

---

## Commands

| Command | Description |
|---------|-------------|
| Create Magic Folder | Open the creation modal |
| Refresh all Magic Folders | Force a manual refresh |

---

## Installation

Search for **Magic Folders** in Obsidian's Community Plugins browser.

---

## Star History

<a href="https://www.star-history.com/?repos=infinition%2Fobsidian-magic-folders&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=infinition/obsidian-magic-folders&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=infinition/obsidian-magic-folders&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=infinition/obsidian-magic-folders&type=date&legend=top-left" />
 </picture>
</a>

---

## License

MIT. See [LICENSE](LICENSE).

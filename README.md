# Magic Folders for Obsidian ✨

Create virtual smart folders that dynamically display files based on tags, links, or custom filters.

![Magic Folders](https://img.shields.io/badge/Obsidian-Plugin-purple)

## Features

- 🪄 **Virtual Folders**: Create folders that don't exist on disk but display filtered content
- 🏷️ **Tag Filtering**: Show all files with specific tags (#Todo, #WIP, etc.)
- 🔗 **Link Filtering**: Show all files linking to a specific note
- 📁 **Folder Filtering**: Filter by folder path
- 📄 **Extension Filtering**: Filter by file extension
- 📋 **Frontmatter Filtering**: Filter by frontmatter properties
- 🎨 **Customizable**: Choose colors, icons, and names for each magic folder
- 📊 **Sorting**: Sort files by name, date, type, or size
- 🔄 **Dynamic Updates**: Folders update automatically when files change
# ✨ Magic Folders — Obsidian Plugin

**Smart virtual folders powered by tags, links, extensions, and frontmatter.**

Magic Folders lets you create dynamic, filter-based virtual folders that appear directly in Obsidian's file explorer. Instead of duplicating or moving files, Magic Folders automatically groups files matching your criteria — tags, internal links, file extensions, folder paths, or frontmatter metadata — into beautifully styled virtual collections.

> 📌 Files are never moved or copied. Magic Folders are **virtual views** — they reference files wherever they live in your vault.

---

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [Creating a Magic Folder](#creating-a-magic-folder)
- [Do Magic — Filter System](#do-magic--filter-system)
  - [Filter Types](#filter-types)
  - [Logic Operators](#logic-operators)
  - [Examples](#filter-examples)
- [Sorting](#sorting)
- [Icons and Customization](#icons-and-customization)
  - [Built-in Icons](#built-in-icons)
  - [Emojis](#emojis)
  - [Custom Icons](#custom-icons)
  - [Icon Adjustments](#icon-adjustments)
  - [Color and Opacity](#color-and-opacity)
  - [Icon-Only Mode](#icon-only-mode)
- [Unread Files and Badges](#unread-files-and-badges)
- [Context Menus](#context-menus)
- [Drag and Drop Reordering](#drag-and-drop-reordering)
- [Settings](#settings)
- [Internationalization](#internationalization)
- [Commands](#commands)
- [Technical Details](#technical-details)
  - [File Opening Behavior](#file-opening-behavior)
  - [Caching](#caching)
  - [Performance](#performance)
- [Troubleshooting](#troubleshooting)
- [API and Data Model](#api-and-data-model)
- [Changelog](#changelog)
- [License](#license)

---

## Features

| Feature | Description |
|---|---|
| **Virtual Folders** | Dynamic collections based on filters — files are never moved |
| **Multi-Filter System** | Combine tags, links, extensions, folder paths, and frontmatter with OR / AND / NOT logic |
| **Live Preview** | See matching files in real-time while building filters |
| **Custom Styling** | 15 preset colors with opacity control, 30+ Lucide icons, full emoji picker, and custom image icons |
| **Icon Adjustments** | Size, X/Y offset sliders for pixel-perfect positioning |
| **Unread Tracking** | Bold new files, badge counts on collapsed folders, mark all read/unread |
| **Sorting** | Sort by name, modified date, created date, file type, size, or tag count |
| **Drag & Drop** | Reorder magic folders by dragging their titles |
| **Context Menus** | Full right-click menus on both folders and files |
| **Tooltips** | Hover to see matched filter tags on each file |
| **File Count** | Optional badge showing the number of files in each folder |
| **Multi-Language** | English, French, Spanish, German, Italian |
| **Smart Caching** | Instant load from cache, background refresh for latest data |
| **Responsive Modals** | All dialogs adapt to screen size with consistent slider/control layout |
| **No Explorer Flash** | Clicking files in Magic Folders does not scroll or flash the native explorer tree |

---

## Installation

### From Obsidian Community Plugins (Recommended)

1. Open **Settings → Community Plugins → Browse**
2. Search for **"Magic Folders"**
3. Click **Install**, then **Enable**

### Manual Installation

1. Download the latest release (`main.js`, `manifest.json`, `styles.css`) from the Releases page
2. Create a folder: `<your-vault>/.obsidian/plugins/obsidian-magic-folders/`
3. Place the downloaded files inside that folder
4. Restart Obsidian and enable the plugin in **Settings → Community Plugins**

---

## Quick Start

1. **Click the wand icon** (🪄) in the left ribbon or in the file explorer header bar
2. **Name** your Magic Folder and pick a **color** and **icon**
3. Click **Create Magic Folder** — it appears at the top of your file explorer
4. **Right-click** the new folder → **Do Magic (Edit Filters)**
5. Add filters like `#project`, `[[Meeting Notes]]`, `.pdf`, or `folder:Research`
6. Click **Apply Magic ✨** — matching files appear instantly

---

## Creating a Magic Folder

Open the creation modal in any of these ways:

- Click the **🪄 wand icon** in the file explorer header
- Click the **🪄 ribbon icon** in the left sidebar
- Run the command **"Create Magic Folder"** from the command palette (`Ctrl/Cmd + P`)
- Right-click any folder → **"Create Magic Folder here"**

### Modal Options

| Option | Description |
|---|---|
| **Name** | Display name shown in the explorer sidebar |
| **Hide Name** | Toggle to show only the icon (no text label) |
| **Color** | Choose from 15 presets or use the color picker. Adjustable opacity. |
| **Icon** | Pick from 30+ Lucide icons |
| **Emoji** | Optional emoji to use instead of an icon |
| **Custom Icon** | Upload or select an image icon (SVG, PNG, JPG, GIF, WebP) |
| **Icon Adjustments** | Size slider (10–64px), X offset (−20 to +20), Y offset (−20 to +20) |
| **Sort By** | Name, Last Modified, Created Date, File Type, Size, or Tag |
| **Sort Order** | Ascending or Descending |

All changes to name, color, and icon are reflected **live** in the file explorer while the modal is open — no need to save first to preview.

---

## Do Magic — Filter System

The **Do Magic** modal is the heart of the plugin. It lets you build complex filter rules that determine which files appear in a Magic Folder.

### Opening Do Magic

- Right-click a Magic Folder → **"✨ Do Magic (Edit Filters)"**

### Filter Types

| Syntax | Filter Type | Description | Example |
|---|---|---|---|
| `#tag` | Tag | Matches files containing this tag (including nested tags) | `#project`, `#work/meeting` |
| `[[link]]` | Internal Link | Matches files linking to a specific note | `[[Dashboard]]` |
| `folder:path` | Folder Path | Matches files inside a folder (partial match) | `folder:Research/2024` |
| `.ext` or `ext:ext` | File Extension | Matches files with a specific extension | `.pdf`, `ext:png` |
| `key:value` | Frontmatter | Matches files where frontmatter key contains value | `status:active`, `type:journal` |

### Quick Insert Buttons

The modal provides quick-insert buttons for common filter types:

`#tag` · `[[link]]` · `folder:` · `.ext` · `ext:` · `key:value`

Clicking a button inserts a template into the input field for you to customize.

### Autocomplete

As you type, the plugin suggests matching tags, links, and extensions from your vault. Use arrow keys to navigate and `Enter` to select.

### Logic Operators

Filters can be combined using three logic modes:

| Operator | Behavior | Color |
|---|---|---|
| **OR** | File matches if it has **any** of the OR filters | 🟢 Green |
| **AND** | File must match **all** AND filters | 🔵 Blue |
| **NOT** | File is **excluded** if it matches any NOT filter | 🔴 Red |

Select the logic mode before adding each filter. Filters are grouped visually by their logic type.

### Filter Examples

**All markdown files tagged `#project`:**
- Add `#project` (OR)

**PDFs in the Research folder:**
- Add `.pdf` (OR)
- Add `folder:Research` (AND)

**Files tagged `#todo` but NOT tagged `#done`:**
- Add `#todo` (OR)
- Add `#done` (NOT)

**Files linking to Dashboard OR tagged `#important`:**
- Add `[[Dashboard]]` (OR)
- Add `#important` (OR)

**Journal entries from 2024 with status "published":**
- Add `folder:Journal/2024` (AND)
- Add `status:published` (AND)

### Live Preview

The bottom of the Do Magic modal shows a live preview of all matching files, updating in real-time as you add or remove filters.

---

## Sorting

Each Magic Folder has its own independent sorting configuration.

| Sort Type | Description |
|---|---|
| **Name** | Alphabetical (A → Z or Z → A) |
| **Last Modified** | Most/least recently edited |
| **Created Date** | Newest/oldest first |
| **File Type** | Grouped by extension |
| **File Size** | Largest/smallest first |
| **Tag** | Files matching more filters appear first |

Change sorting via the right-click context menu or in the Edit modal. Both sort field and direction (ascending/descending) are configurable.

---

## Icons and Customization

### Built-in Icons

30+ icons from the [Lucide](https://lucide.dev/) icon set are available, including:

`folder-search` · `wand-2` · `sparkles` · `star` · `heart` · `bookmark` · `tag` · `hash` · `filter` · `layers` · `box` · `archive` · `briefcase` · `zap` · `flame` · `target` · `trophy` · `crown` · `gem` · `rocket` · `lightbulb` · `brain` · `puzzle` · `compass` · `map` · `globe`

### Emojis

A searchable emoji picker with 300+ emojis is built in. The selected emoji replaces the icon in the folder title.

### Custom Icons

To use your own icon images:

1. Go to **Settings → Magic Folders → Use custom icons** and enable it
2. Set the **Custom icon folder** path (vault-relative like `Assets/Icons` or an absolute system path)
3. Place SVG, PNG, JPG, GIF, or WebP files in that folder
4. When creating/editing a Magic Folder, a custom icon grid will appear in the modal
5. Click any icon to select it — it is automatically resized and cached

Custom icons are stored as optimized PNGs in `.obsidian/plugins/obsidian-magic-folders/custom-icons/` for fast loading. GIF icons retain their animation.

### Icon Adjustments

All icon types (built-in, emoji, and custom) support:

| Control | Range | Description |
|---|---|---|
| **Size** | 10 – 64 px | Scale the icon up or down |
| **X Offset** | −20 to +20 px | Shift the icon left or right |
| **Y Offset** | −20 to +20 px | Shift the icon up or down |
| **Keep Image Ratio** | Toggle | Preserve aspect ratio for custom icons |

Changes are reflected live in the file explorer as you drag the sliders.

### Color and Opacity

- **15 preset colors** with one-click selection
- **Custom color picker** for any hex color
- **Opacity slider** (0% – 100%) for subtle or vibrant folder accents

The color is applied as a left border, gradient background, icon tint, and title text color in the explorer.

### Icon-Only Mode

Enable **"Hide Name (Icon Only)"** to display just the icon with no text label. This is useful for icon-heavy workflows or minimal sidebar layouts.

---

## Unread Files and Badges

Magic Folders tracks which files are new (appeared since your last view) and which you have opened.

### How It Works

1. When a Magic Folder is refreshed and new files appear that weren't in the previous list, they are marked as **unread**
2. Unread files appear in **bold** inside the folder
3. When the folder is collapsed, a **badge** shows the count of unread files
4. Opening a file in any Magic Folder marks it as **read** across all folders
5. Right-click a folder to **Mark all as Read** or **Mark all as Unread**

### Related Settings

| Setting | Default | Description |
|---|---|---|
| Show new items badge | ✅ On | Badge on collapsed folders with unread count |
| Highlight unread files | ✅ On | Bold styling for unread files |
| Show file count | ✅ On | Total file count badge next to folder name |

---

## Context Menus

### Magic Folder Context Menu (Right-click folder title)

| Action | Description |
|---|---|
| ✨ Do Magic (Edit Filters) | Open the filter editor |
| Edit Magic Folder | Open the creation/edit modal |
| Move Up / Move Down | Reorder the folder |
| Sort by: Name / Modified / Created / Type / Size / Tag | Change sorting |
| Order: Ascending / Descending | Change sort direction |
| Refresh | Force refresh matching files |
| Mark all as Read | Clear all unread markers |
| Mark all as Unread | Mark all files as unread |
| Delete Magic Folder | Remove the virtual folder |

### File Context Menu (Right-click a file inside a Magic Folder)

| Action | Description |
|---|---|
| Open | Open in the current tab |
| Open in new tab | Open in a new tab |
| In Magic Folder: {name} | Shows which folder contains this file |
| Matched: {filters} | Shows which filters this file matched |

### Native File Context Menu Integration

When right-clicking any file in the native explorer, if that file belongs to a Magic Folder, the context menu shows which Magic Folder(s) it belongs to and which filters matched.

---

## Drag and Drop Reordering

Magic Folders can be reordered by dragging:

1. Click and hold a Magic Folder's title bar
2. Drag it over another Magic Folder
3. Release to swap positions

A dashed outline appears around the drop target to indicate valid placement. The new order is saved automatically.

---

## Settings

Access via **Settings → Community Plugins → Magic Folders**

| Setting | Default | Description |
|---|---|---|
| **Show tooltips** | ✅ On | Show matched filter tags when hovering over files |
| **Auto refresh** | ✅ On | Automatically refresh folders when vault files change |
| **Show new items badge** | ✅ On | Unread count badge on collapsed folders |
| **Highlight unread files** | ✅ On | Bold styling for new/unread files |
| **Show file count** | ✅ On | File count badge next to folder name |
| **Language** | Français | UI language (EN, FR, ES, DE, IT) |
| **Use custom icons** | ❌ Off | Enable custom icon images from a folder |
| **Custom icon folder** | (empty) | Path to folder containing icon files |

---

## Internationalization

The entire plugin UI is available in five languages:

| Code | Language | Native Name |
|---|---|---|
| `en` | English | English |
| `fr` | French | Français |
| `es` | Spanish | Español |
| `de` | German | Deutsch |
| `it` | Italian | Italiano |

All labels, menus, notices, modal text, settings descriptions, and help text are fully translated. Change the language at any time in settings — the UI updates immediately.

---

## Commands

Available from the Command Palette (`Ctrl/Cmd + P`):

| Command | Description |
|---|---|
| **Create Magic Folder** | Open the creation modal |
| **Create Magic Folder in current folder** | Open the creation modal with context |
| **Refresh all Magic Folders** | Force refresh all virtual folders |

---

## Technical Details

### File Opening Behavior

When clicking a file inside a Magic Folder:

- The file opens directly in the current or a new tab using `leaf.openFile()`
- **The native file explorer tree does NOT scroll or reveal** the file's actual folder location
- This prevents the jarring "flash" that occurred with previous versions when opening non-Markdown files (PDFs, images, etc.)
- The plugin temporarily suppresses the file explorer's `revealInFolder` behavior during magic folder opens
- `Ctrl/Cmd + Click` opens in a new tab

### Caching

Magic Folders uses a two-tier caching strategy:

1. **Settings cache**: On load, the plugin immediately renders folders from the last-saved file list (instant UI)
2. **Background refresh**: After initial render, the plugin recalculates all filters in the background and updates if anything changed
3. **Custom icon cache**: Icon images are cached in memory and localStorage for instant display

This means the explorer always shows your Magic Folders immediately, even in large vaults.

### Performance

- **Debounced refresh**: File system changes trigger a 500ms debounced refresh to batch rapid changes
- **MutationObserver**: If Obsidian's virtual scrolling removes a Magic Folder DOM node, it is automatically re-injected within 50ms
- **Lazy icon loading**: Custom icons use `requestIdleCallback` for non-blocking image loading
- **Filter evaluation**: OR/AND/NOT logic is evaluated with early termination (NOT filters short-circuit first)

### Data Storage

All settings and folder configurations are stored in the plugin's `data.json` file inside:

```
<vault>/.obsidian/plugins/obsidian-magic-folders/data.json
```

Custom icon files (resized copies) are stored in:

```
<vault>/.obsidian/plugins/obsidian-magic-folders/custom-icons/
```

---

## Troubleshooting

### Magic Folders disappear after scrolling

Obsidian uses virtual scrolling in the file explorer, which can remove DOM nodes that are scrolled out of view. The plugin includes a `MutationObserver` that automatically re-inserts missing Magic Folders. If this issue persists, use the **Refresh all Magic Folders** command.

### Files don't update after adding tags

Ensure **Auto refresh** is enabled in settings. If you just added a tag, Obsidian's metadata cache may take a moment to update. You can also right-click the folder → **Refresh**.

### Custom icons not showing

1. Verify the icon folder path in settings (vault-relative: `Assets/Icons` or absolute: `/Users/me/icons`)
2. Ensure the files are `.svg`, `.png`, `.jpg`, `.gif`, or `.webp`
3. Check that **Use custom icons** is toggled on
4. Try toggling the setting off and on again

### Non-Markdown files not appearing

File extension filters (`.pdf`, `.png`, etc.) automatically search **all vault files**, not just Markdown. If a filter is tag-based only, the plugin searches only Markdown files. Add an `ext:` filter to include other file types.

### Explorer flashes when opening files

This was a known issue in earlier versions. The current version uses direct `leaf.openFile()` instead of `openLinkText()` and patches the file explorer's reveal behavior. Ensure you are running the latest version.

---

## API and Data Model

### MagicFolder Object

```typescript
interface MagicFolder {
  id: string;                    // Unique identifier (e.g., "magic-1706000000000-abc123")
  name: string;                  // Display name
  icon: string;                  // Lucide icon name
  color: string;                 // Hex color or rgba() string
  filters: MagicFilter[];        // Array of filter rules
  sortBy: SortType;              // 'name' | 'modified' | 'created' | 'type' | 'size' | 'tag'
  sortOrder: 'asc' | 'desc';
  collapsed: boolean;
  emoji?: string;                // Optional emoji override
  customIconPath?: string;       // Path to cached custom icon
  customIconSourcePath?: string; // Original icon source path
  customIconSize?: number;       // Icon size in pixels (default: 28)
  customIconKeepRatio?: boolean; // Preserve aspect ratio
  customIconOffsetX?: number;    // Horizontal offset in pixels
  customIconOffsetY?: number;    // Vertical offset in pixels
  hideName?: boolean;            // Icon-only mode
  unreadFilePaths?: string[];    // Paths of unread files
}
```

### MagicFilter Object

```typescript
interface MagicFilter {
  type: 'tag' | 'link' | 'folder' | 'extension' | 'frontmatter';
  value: string;
  operator: 'contains' | 'equals' | 'startsWith' | 'endsWith';
  logic: 'OR' | 'AND' | 'NOT';
}
```

### Settings Object

```typescript
interface MagicFoldersSettings {
  magicFolders: MagicFolder[];
  showInExplorer: boolean;
  refreshOnChange: boolean;
  showTooltips: boolean;
  cache: MagicFolderCache[];
  language: 'en' | 'fr' | 'es' | 'de' | 'it';
  customIconsEnabled: boolean;
  customIconFolder: string;
  showNewItemsBadge: boolean;
  highlightUnreadFiles: boolean;
  showFileCount: boolean;
}
```

---

## Changelog

### v1.0.0

- Initial release
- Virtual folder creation with tag, link, extension, folder, and frontmatter filters
- OR / AND / NOT logic operators
- 6 sorting modes with ascending/descending order
- 30+ Lucide icons, full emoji picker, custom image icons
- Icon size, offset, and aspect ratio controls
- Color picker with opacity support
- Unread file tracking with badges
- Drag and drop folder reordering
- 5-language support (EN, FR, ES, DE, IT)
- Context menus for folders and files
- Settings cache with background refresh
- MutationObserver-based resilience against virtual scrolling
- Direct file opening without explorer tree reveal or flash

---

## License

This plugin is released under the [MIT License](LICENSE).

---

<p align="center">
  Made with ✨ magic for the Obsidian community
</p>
## Installation

### From Obsidian Community Plugins
1. Open Settings → Community Plugins
2. Disable Safe Mode
3. Click Browse and search for "Magic Folders"
4. Install and enable the plugin

### Manual Installation
1. Download the latest release
2. Extract to your vault's `.obsidian/plugins/obsidian-magic-folders/` folder
3. Reload Obsidian
4. Enable the plugin in Settings → Community Plugins

## Usage

### Creating a Magic Folder
1. Click the **wand icon** (✨) in the file explorer toolbar, or
2. Use the command palette: "Create Magic Folder"

### Adding Filters (Do Magic)
1. Right-click on a magic folder
2. Select "✨ Do Magic (Edit Filters)"
3. Add filters:
   - **Tags**: `#Todo`, `#WIP`, `#Important`
   - **Links**: `[[MyNote]]`, `[[Folder/File]]`
   - **Folders**: `folder:Projects`
   - **Extensions**: `ext:md`, `ext:pdf`
   - **Frontmatter**: `status:active`, `type:project`

### Filter Syntax

| Type | Syntax | Example |
|------|--------|---------|
| Tag | `#tagname` | `#Todo` |
| Link | `[[note]]` | `[[Daily Notes]]` |
| Folder | `folder:path` | `folder:Projects` |
| Extension | `ext:type` | `ext:md` |
| Frontmatter | `key:value` | `status:done` |

### Customization

Each magic folder can be customized with:
- **Name**: Any name you want
- **Icon**: Choose from 30+ icons
- **Color**: 15 preset colors
- **Sort**: By name, modified date, created date, type, or size
- **Order**: Ascending or descending

## Examples

### Todo Folder
Show all files tagged with #Todo or #WIP:
```
Filters: #Todo #WIP
Sort: Modified (Descending)
```

### Project Hub
Show all files linking to your Projects note:
```
Filters: [[Projects]]
Sort: Name (Ascending)
```

### Recent Notes
Show recently modified notes in a specific folder:
```
Filters: folder:Daily Notes
Sort: Modified (Descending)
```

## Commands

| Command | Description |
|---------|-------------|
| Create Magic Folder | Opens the creation modal |
| Refresh all Magic Folders | Manually refreshes all folders |

## Settings

- **Show in Explorer**: Toggle visibility of magic folders in the file explorer
- **Refresh on Change**: Automatically refresh when files change

## Support

If you find this plugin useful, consider:
- ⭐ Starring the repository on GitHub
- 🐛 Reporting bugs or suggesting features
- 💬 Sharing your creative uses

## License

MIT License - feel free to use and modify!

---

Made with ✨ magic by [Infinition](https://github.com/infinition)

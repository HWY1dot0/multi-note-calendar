# Calendar Hub

Calendar Hub turns the calendar sidebar into a hub for your daily notes. Instead of
mapping each day to a single note, it surfaces **every note created on a given day**
wherever it lives in your vault, so you can find, open, and manage them all in one place.

## Why Calendar Hub?

If you generate a lot of notes, for example with AI tools, files quickly scatter
across folders and become hard to track down. Calendar Hub groups them by the day
they were created, giving you a single place to see everything from a given day
without hunting through your folder tree.

Example matches for one date:

- `Daily/2026-05-29.md`
- `Work log/work log 20260529.md`
- `Meeting notes/team sync 20260529.md`

![Calendar Hub preview](./images/calendar-hub-preview.png)

## Features

- See all notes created on any selected day, regardless of folder.
- Open and manage the day's notes from one panel.
- Scan the whole vault or limit matching to specific folders.
- Adjust folder filters directly from the calendar sidebar.
- Match exact Daily Notes filenames and dates embedded inside longer filenames.
- Add extra filename date formats such as `YYYYMMDD`.
- Use frontmatter date fields as a fallback when the filename has no date.
- Use note-count dots to see how many matching notes exist on each day.
- Keep optional weekly-note support for existing Calendar workflows.

## Date Matching

Calendar Hub maps Markdown files to calendar dates in this order:

1. Exact Daily Notes filename match using your configured Daily Notes format.
2. Date embedded in the filename using the Daily Notes format.
3. Date embedded in the filename using any extra formats you configure.
4. Frontmatter date fallback, only when the filename does not contain a matching date.

Filename dates take priority over frontmatter dates. Folder filters apply to both filename and frontmatter matching.

## Settings

- **Detect daily notes in all folders**: Scan Markdown files outside the configured Daily Notes folder.
- **Folders to scan for daily notes**: Limit matching to comma-separated folder paths. Leave blank to scan the whole vault.
- **Date format inside daily note filenames**: Add extra comma-separated formats, such as `YYYYMMDD`.
- **Use frontmatter date fallback**: Read configured frontmatter fields when the filename has no matching date.
- **Frontmatter date fields**: Choose fields such as `date`, `daily_date`, or `calendar.date`.
- **Note count dots**: Solid dots show how many matching notes exist for the day, up to 5 dots.
- **Confirm before creating new note**: Ask before creating a new Daily Note.
- **Show week number**: Show week numbers and keep legacy weekly-note behavior.

The folder filter can also be adjusted directly from the calendar sidebar.

## Installation

Install through Obsidian's Community Plugins directory after publication.

Before publication, install with BRAT using this repository:

```text
HWY1dot0/calendar-hub
```

Manual installation uses the files attached to each GitHub release:

- `main.js`
- `manifest.json`
- `styles.css`

Copy those files into `.obsidian/plugins/calendar-hub/` inside your vault, then reload Obsidian and enable the plugin.

## Commands

- **Open calendar view**: Opens the Calendar Hub sidebar view.
- **Reveal active note in calendar**: Moves the calendar to the month for the active date-based note.
- **Open weekly note**: Opens or creates the current weekly note when legacy weekly-note support is enabled.

## Compatibility

Calendar Hub requires Obsidian `0.9.11` or newer.

The plugin uses Obsidian theme variables and should follow light and dark themes without custom CSS.

## Relationship To Calendar

This plugin is based on Liam Cain's original Calendar plugin for Obsidian:

https://github.com/liamcain/obsidian-calendar-plugin

The original project is MIT licensed. The original copyright notice remains in `LICENSE`, alongside copyright for this fork's modifications.

Calendar Hub uses its own plugin id, `calendar-hub`, so it can be installed separately from the original Calendar plugin.

## Development

```bash
npm test
npm run build
```

## Say Thanks

If Calendar Hub helps your workflow, you can buy me a coffee:

https://www.buymeacoffee.com/hwy1dot0

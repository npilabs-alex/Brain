# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Brain** - A simple task/notes system with tagging and status tracking. Claude manages tasks via `tasks.json`.

## Task Management

Tasks are stored in `tasks.json`. Each task has:
- `id`: Auto-incrementing integer
- `task`: Description of the task
- `tags`: Array of strings (e.g., ["BandLab", "Beacon"])
- `status`: One of "pending", "in_progress", "completed"
- `created`: ISO timestamp
- `updated`: ISO timestamp

## Common Operations

### Adding a task
User says: "Create a fix list for Beacon and pass to developer, Tag BandLab and Beacon"
→ Add task with tags ["BandLab", "Beacon"], status "pending"

### Listing tasks by tag
User says: "List all BandLab tasks"
→ Filter tasks.json where tags includes "BandLab", display with status

### Updating status
User says: "Mark task 3 as completed" or responds "done" when asked
→ Update task status and updated timestamp

### Viewing all tags
User says: "What tags do I have?"
→ List unique tags across all tasks

## Display Format

When listing tasks, show:
```
[ID] [STATUS] Task description
    Tags: tag1, tag2
```

Example:
```
[3] [pending] Create a fix list for Beacon and pass to developer
    Tags: BandLab, Beacon
```

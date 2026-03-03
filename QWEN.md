# QWEN.md - Project Context Guide

## Project Overview

This is a **personal blog** built with **Hugo** (static site generator) using the **PaperMod** theme. Content is authored and managed in **Obsidian**.

**Key Technologies:**
- **Hugo** v0.128.1 - Static site generator
- **PaperMod** - Hugo theme (git submodule)
- **Obsidian** - Content authoring and management
- **GitHub Pages** - Hosting platform

**Live Site:** https://jinyu.cool/

## Project Structure

```
/
├── config.toml              # Hugo configuration
├── content/                 # Blog posts (Markdown)
│   ├── posts/              # Categorized blog posts
│   │   ├── ai/            # AI-related content
│   │   ├── backend/       # Backend development
│   │   ├── frontend/      # Frontend development
│   │   ├── devops/        # DevOps topics
│   │   ├── hardware/      # Hardware-related
│   │   └── solutions/     # Solution guides
│   ├── about/             # About page
│   └── archives.md        # Archives page
├── layouts/                 # Custom Hugo layouts
├── static/                  # Static assets (served at root)
├── themes/                  # Hugo themes (PaperMod submodule)
└── .github/workflows/      # CI/CD (GitHub Pages deploy)
```

## Build and Development Commands

### Hugo Site (Root Directory)

```bash
# Development server with live reload
hugo server

# Build for production
hugo

# Build with minification
hugo --minify
```

### CI/CD Deployment

The site auto-deploys to GitHub Pages on push to `main` branch via GitHub Actions.

## Obsidian CLI

**When performing actions related to content management, prefer using the Obsidian CLI.**

```bash
# Target a specific vault
obsidian <command> vault=<name>

# Create a new file
obsidian create name="Post Title" path="content/posts/category/"

# Read file contents
obsidian read path="content/posts/category/post.md"

# Append content to a file
obsidian append path="content/posts/category/post.md" content="New content..."

# Prepend content to a file
obsidian prepend path="content/posts/category/post.md" content="Front matter..."

# Open a file in Obsidian
obsidian open path="content/posts/category/post.md"

# Search in vault
obsidian search query="keyword" path="content/posts/"

# List files in vault
obsidian files folder="content/posts/" ext="md"

# Get tags from a file
obsidian tags path="content/posts/category/post.md"

# List outgoing links
obsidian links path="content/posts/category/post.md"

# List backlinks
obsidian backlinks path="content/posts/category/post.md"

# Show file info
obsidian file path="content/posts/category/post.md"

# Word count
obsidian wordcount path="content/posts/category/post.md"

# Show headings/outline
obsidian outline path="content/posts/category/post.md"

# Delete a file
obsidian delete path="content/posts/category/post.md"

# Move/rename a file
obsidian move path="content/posts/old.md" to="content/posts/new.md"
```

## Development Conventions

### Hugo Content (Blog Posts)

**File Location:** `content/posts/<category>/<post-name>.md`

**Front Matter Template:**
```yaml
---
title: "Post Title"
date: 2024-01-01
categories: ["Category"]
tags: ["tag1", "tag2"]
draft: false
---
```

**Category Structure:**
- `ai/` - AI/ML topics
- `backend/` - Backend development
- `frontend/` - Frontend development
- `devops/` - DevOps and deployment
- `hardware/` - Hardware topics
- `solutions/` - Solution guides
- `troubleshooting/` - Issue resolutions

## Key Configuration

### Hugo (config.toml)

- **Base URL:** `https://mammoth777.github.io/blog/`
- **Title:** "Jachy's Blog"
- **Theme:** PaperMod
- **Profile Mode:** Enabled with custom image and buttons
- **Features:** Code highlighting, word count, reading time, TOC

## Git Submodules

This project uses two git submodules:
- `themes/PaperMod` - Hugo theme
- `public` - GitHub Pages deployment target

**Clone with:**
```bash
git clone --recursive <repository-url>
```

**Update submodules:**
```bash
git submodule update --init --recursive
```

## Adding New Content

### New Blog Post
1. Use Obsidian CLI to create/manage content
2. Add front matter with title, date, categories, tags
3. Set `draft: false` when ready to publish

## Dependencies

### Hugo
- Version: 0.128.1 (CI/CD)
- Theme: PaperMod

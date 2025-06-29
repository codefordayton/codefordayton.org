# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based static website for Code For Dayton (codefordayton.org), a local civic hacking group in Dayton, Ohio aligned with the Alliance of Civic Technologists (https://www.civictechnologists.org/). The site is hosted via GitHub Pages and automatically deploys when changes are pushed to the `main` branch.

## Architecture

### Key Technologies
- **Jekyll 3.9.3**: Static site generator using Ruby
- **GitHub Pages**: Hosting platform with automatic deployment
- **Sass**: CSS preprocessing (located in `_sass/`)
- **Kramdown**: Markdown processor

### Directory Structure
- `_data/`: YAML data files that drive site content
  - `events/active.yml`: Current events listings
  - `projects/active.yml` & `projects/inactive.yml`: Project listings
  - `team.yml`: Team member information
- `_posts/`: Blog posts in Markdown format
- `_layouts/`: HTML templates (default, page, post)
- `_includes/`: Reusable HTML components
- `_sass/`: Sass stylesheets organized by component
- `_site/`: Generated static site (build output)

### Content Management
The site uses Jekyll's data-driven approach where YAML files in `_data/` populate lists and content sections. This allows non-technical contributors to update events, projects, and team information without touching HTML.

## Development Commands

### Local Development
```bash
# Install dependencies
gem install jekyll jekyll-redirect-from

# Build the site
jekyll build

# Serve locally with live reload
jekyll serve --livereload
# Site will be available at http://127.0.0.1:4000/
```

### Dependencies
- Ruby (available in system PATH)
- Jekyll gem and jekyll-redirect-from plugin
- System dependencies may include gcc-c++, redhat-rpm-config, ruby-devel (on Fedora)

## Deployment

The site automatically deploys to https://www.codefordayton.org/ when changes are pushed to the `main` branch. No manual deployment process is required.

## Content Updates

- **Events**: Edit `_data/events/active.yml`
- **Active Projects**: Edit `_data/projects/active.yml`
- **Retired Projects**: Edit `_data/projects/inactive.yml`
- **Team Members**: Edit `_data/team.yml`
- **Blog Posts**: Add new files to `_posts/` following the naming convention `YYYY-MM-DD-title.md`
- **Pages**: Edit HTML/Markdown files in the root directory or create new ones

## Configuration

Site configuration is managed in `_config.yml` including:
- Site metadata and social links
- Jekyll plugins (jekyll-redirect-from, jekyll-feed)
- Collection settings for posts and uploads
- Base URL and author information
# Agentix Documentation - AI Coding Agent Instructions

## Project Overview

This is a **Mintlify documentation site** for Agentix - an AI-driven control panel for managing automated customer journeys. The project uses Mintlify's framework to generate beautiful, interactive documentation with three main sections: User Guide, Developer Guide and API Reference.

## Architecture & Key Files

- **`docs.json`** - Central configuration file defining navigation, themes and site structure
- **`index.mdx`** - Homepage introducing Agentix cPanel with role-based access (Job-Hub User vs Manager)
- **Missing content directories**: `user-guide/`, `developer-guide/` folders need to be created
- **Existing examples**: `essentials/`, `api-reference/` contain Mintlify starter templates to reference

## Development Workflow

```bash
# Install Mintlify CLI globally
npm i -g mintlify

# Run local development server (where docs.json is located)
mintlify dev

# Validate documentation links
mintlify broken-links
```

## Content Structure Patterns

### 1. Navigation Configuration
The `docs.json` defines a three-tab structure with nested groups. When adding pages:
- Update `docs.json` navigation arrays to include new pages
- Use relative paths without `.mdx` extension: `"user-guide/flows"`
- Maintain the tab → groups → pages hierarchy

### 2. MDX Frontmatter Pattern
```yaml
---
title: 'Page Title'
description: 'Brief description for SEO and navigation'
icon: 'fontawesome-icon-name'  # Optional
---
```

### 3. Missing Content Organization
Based on `docs.json`, create these directory structures:
```
user-guide/
  what-is-agentix.mdx
  quickstart.mdx
  navigation.mdx
  flows.mdx
  tasks.mdx
  agents.mdx
  tools.mdx
  reports.mdx
  notifications.mdx
  settings.mdx
  faq.mdx

developer-guide/
  overview.mdx
  setup.mdx
  quickstart.mdx
  python/
    install.mdx
    task-lifecycle.mdx
    tools.mdx
    examples.mdx
  js/
    overview.mdx
    roadmap.mdx

api-reference/
  authentication.mdx
  quickstart.mdx
  tasks/
    create.mdx
    update.mdx
    status.mdx
    files.mdx
  webhooks/
    room-events.mdx
    agent-actions.mdx
    task-status.mdx
```

## Content Creation Guidelines

### 1. Component Usage
Use Mintlify's built-in components for consistency:
- `<CardGroup cols={2}>` and `<Card>` for feature highlights
- `<Note>`, `<Tip>`, `<Warning>` for callouts
- `<Accordion>` and `<AccordionGroup>` for collapsible content
- `<CodeGroup>` for multiple code examples

### 2. Agentix-Specific Context
Focus on these core concepts when writing content:
- **Customer Journeys**: AI + human workflow automation
- **Role-based Access**: Job-Hub Users vs Managers
- **Flow Management**: Creating guided experiences
- **Agent Assignment**: AI and human agent coordination
- **Tool Integration**: Reusable automation components

### 3. Asset Organization
- Images in `/images/` directory (existing: cpanel-light.png, cpanel-dark.png)
- Logos in `/logo/` with light/dark variants
- Snippets in `/snippets/` for reusable content (use MDX imports)

## Deployment

- Auto-deployment via GitHub App when pushing to main branch
- Manual deployment available through Mintlify dashboard
- Validate with `mintlify broken-links` before pushing

## Quick Start for New Content

1. Add page path to appropriate `docs.json` navigation group
2. Create MDX file with proper frontmatter
3. Use existing `/essentials/` files as component reference examples
4. Test locally with `mintlify dev` before committing

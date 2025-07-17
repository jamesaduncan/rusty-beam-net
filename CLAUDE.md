# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the documentation website for Rusty Beam, a high-performance HTTP server with a plugin architecture written in Rust. The repository contains the website content (rustybeam.net), not the actual server implementation.

## CRITICAL INFORMATION FOR DEVELOPMENT

It is *** CRITICAL *** that when you develop code you don't touch the config/index.html or the rustybeam.net/auth/index.html files, unless
I explicity instruct you to.

## IMPORTANT INFORMATION FOR DEVELOPMENT

It's really important to me that we keep beautiful, clean, semantically useful markup in the website. Where possible I'd like you to use
landmark tags (nav, menu, main, article, section, aside, etc over divs.). It should also use microdata formats wherever applicable.
HTML that is all of these things is beautiful, and I want my HTML to be beautful at all times.

## Key Concepts

- **CSS Selector Ranges**: The server uses CSS selectors in HTTP Range headers for content manipulation
- **HTML Configuration**: Server configuration is done through semantic HTML with microdata
- **Plugin Architecture**: Extensive plugin system with 16+ available plugins
- **DOM-Aware Primitives**: Uses external library for DOM manipulation primitives

## Project Structure

```
rustybeam.net/           # Main documentation site
├── index.html           # Homepage
├── getting-started.html # Setup documentation
├── configuration.html   # Server configuration guide
├── plugins/            # Plugin registry and documentation
├── demos/              # Interactive examples (guestbook, todo list)
├── schema/             # Configuration schemas
├── developer/          # Architecture documentation
└── assets/             # CSS, JavaScript, images
```

## Development Commands

This is a static website project. For development:

```bash
# Serve locally (use any HTTP server)
python -m http.server 8000
# or
npx serve .

# No build process required - pure HTML/CSS/JS
```

## Architecture Notes

### Authentication System
- Supports OAuth2 (Google, GitHub) and Basic Auth
- Configuration via HTML microdata in auth.html files
- Demo applications include authentication examples

### Plugin System
- Plugins documented in /plugins/ directory
- Each plugin has its own documentation page
- Plugin configuration uses HTML microdata schemas

### JavaScript Modules
- Uses ES6 modules for client-side functionality
- Module imports use relative paths
- WebSocket integration for real-time features

### CSS Architecture
- Modern CSS with Grid and Flexbox
- Custom properties for theming
- Responsive design patterns
- Component-based stylesheet organization

## Important Files

- `rustybeam.net/index.html` - Main homepage
- `rustybeam.net/getting-started.html` - Setup instructions
- `rustybeam.net/configuration.html` - Configuration guide
- `demos/guestbook/` - Real-time guestbook demo
- `demos/todo-list/` - Todo list application demo
- `plugins/` - Plugin documentation and registry

## Development Guidelines

- All configuration examples use semantic HTML with microdata
- JavaScript should use ES6 modules
- CSS should follow the established component patterns
- Demo applications should be fully functional examples
- Documentation should be clear and include practical examples

## Testing

No automated testing framework is configured. Testing involves:
- Manual testing of demo applications
- Validation of HTML microdata schemas
- Cross-browser compatibility testing
- Mobile responsiveness verification
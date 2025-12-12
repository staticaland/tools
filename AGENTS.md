# AGENTS.md

This project contains multiple single HTML page JS/HTML/CSS tools.

Inspired by [Useful patterns for building HTML tools](https://simonwillison.net/2025/Dec/10/html-tools/) by Simon Willison.

## Principles

- **Single file approach**: Inline JavaScript and CSS in a single HTML file means the least hassle in hosting or distributing, and crucially means you can copy and paste them out of an LLM response
- **Avoid React or anything with a build step**: JSX requires a build step which makes everything massively less convenient - prompt "no react" to skip that issue
- **Load dependencies from CDN**: The fewer dependencies the better, but if there's a well known library that helps solve a problem, load it from cdnjs. Always use the latest version available
- **Host on GitHub Pages**: Free for public repositories and GitHub hasn't broken a working URL in 17+ years

# AGENTS.md

This project contains multiple single HTML page JS/HTML/CSS tools.

Inspired by [Useful patterns for building HTML tools](https://simonwillison.net/2025/Dec/10/html-tools/) by Simon Willison.

## Principles

- **Single file approach**: Inline JavaScript and CSS in a single HTML file means the least hassle in hosting or distributing, and crucially means you can copy and paste them out of an LLM response
- **Avoid React or anything with a build step**: JSX requires a build step which makes everything massively less convenient - prompt "no react" to skip that issue
- **Load dependencies from CDN**: The fewer dependencies the better, but if there's a well known library that helps solve a problem, load it from cdnjs. Always use the latest version available. Exception: Tailwind CSS Play CDN (`cdn.tailwindcss.com`) is acceptable when custom configuration is needed, as it provides JIT compilation that cdnjs cannot replicate

## Finding Latest Library Versions

Always use the cdnjs API to find the latest version of a library before adding it to your HTML:

```
https://api.cdnjs.com/libraries/{library-name}?fields=version,filename
```

**Example**: To find the latest version of Chart.js:

```
https://api.cdnjs.com/libraries/Chart.js?fields=version,filename
```

Response:
```json
{
  "name": "Chart.js",
  "version": "4.4.7",
  "filename": "chart.umd.min.js"
}
```

Then construct the CDN URL:
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.7/chart.umd.min.js"></script>
```

**Search for libraries** if you don't know the exact name:
```
https://api.cdnjs.com/libraries?search=chart&fields=name,version
```
- **Host on GitHub Pages**: Free for public repositories and GitHub hasn't broken a working URL in 17+ years

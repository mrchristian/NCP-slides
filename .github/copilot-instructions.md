# AI Coding Agent Instructions for NCP-slides

## Project Overview
NCP-slides is a Quarto presentation repository built with Reveal.js. Slides are authored in Quarto markdown (`.qmd`), rendered to interactive HTML presentations, and deployed via GitHub Pages.

## Architecture & Structure
- **Main Presentation**: `index.qmd` - Primary slide file in Quarto markdown format
- **Build System**: Quarto with Reveal.js backend
- **Build Output**: `_output/` directory contains rendered HTML (git-ignored)
- **Configuration**: `_quarto.yml` - Project-wide Quarto and Reveal.js settings

## Key Workflows

### Building & Previewing Slides
```bash
# Live preview with hot reload
quarto preview

# Build for production
quarto render
```
- **Preview**: Generates temporary build, opens in browser, watches for changes
- **Build Output**: HTML files in `_output/` directory
- **Key Point**: Never commit `_output/` directory - it's in `.gitignore`

### Live Development
When editing `index.qmd`, `quarto preview` automatically rebuilds and refreshes the browser.

## Project Conventions

### Slide Authoring
- **Slide Headers**: Use `##` markdown heading for each slide
- **Speaker Notes**: Wrap private notes in `:::{.notes}` ... `:::` blocks
- **Code Blocks**: Fence with triple backticks, specify language (r, python, bash, etc.)
- **Slide Layout**: Default: 1050×700px, centered content with margins

### File Organization
```
index.qmd          # All slides in single file (current approach)
                   # OR split into separate .qmd files and reference in _quarto.yml if project grows
```

### Reveal.js Features Available
- **Transitions**: Configured in `_quarto.yml` (slide, fade, zoom, etc.)
- **Plugins**: spotlight (click to highlight), chalkboard (drawing board) enabled
- **Navigation**: Arrow keys, Space, S for speaker view, ESC for overview

### GraphViz Diagram Support
- **Syntax**: Use fenced code blocks with `{dot}` language
- **Example**: 
  ```{dot}
  digraph G {
    A -> B;
    B -> C;
  }
  ```
- **Formats**: Supports dot (directed graphs), neato, circo, fdp, sfdp, twopi, and more
- **Documentation**: https://graphviz.org/doc/info/lang.html

### Mermaid Diagram Support
- **Syntax**: Use fenced code blocks with `{mermaid}` language
- **Supported Diagrams**: flowchart, sequence, gantt, pie, class, state, git, ER, user journey
- **Example**: 
  ```{mermaid}
  flowchart LR
    A[Start] --> B{Decision}
    B -->|Yes| C[Process]
    C --> D[End]
  ```
- **Documentation**: https://mermaid.js.org/

## Development Setup
1. **Install Quarto**: Download from https://quarto.org/docs/get-started/
2. **Verify Installation**: `quarto --version` should output version
3. **Preview Slides**: `quarto preview` from repository root
4. **Edit Content**: Modify `index.qmd` and see changes live
5. **Build for Deployment**: `quarto render` generates `_output/index.html`

## Integration Points
- **CI/CD**: GitHub Actions can run `quarto render` and deploy to GitHub Pages
- **External Services**: None currently configured
- **Deployment Target**: GitHub Pages (default) or any static hosting

## Common Patterns & Examples
- **Adding a New Slide**: Add `## Slide Title` and content below it in `index.qmd`
- **Embedding Media**: Use Markdown syntax `![alt](path/to/image.png)` or `<video>` tags
- **Cross-Slide References**: Use Reveal.js slide numbering, reference manually in speaker notes
- **Theme/Styling**: Modify `format.revealjs.theme` in `_quarto.yml` (options: default, dark, league, sky, beige, simple, serif, blood, night, moon, solarized)

---

**Note**: See [Quarto Reveal.js documentation](https://quarto.org/docs/presentations/revealjs/) for advanced features like fragments, animations, and layout options.

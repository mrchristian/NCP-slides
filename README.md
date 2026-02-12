# NCP-slides

A presentation built with [Quarto](https://quarto.org) and rendered with [Reveal.js](https://revealjs.com).

## Setup

This is a Quarto project using Reveal.js for presentations. Ensure you have Quarto installed:

```bash
# Install Quarto from https://quarto.org/docs/get-started/
quarto --version
```

## Development

### Preview Slides
```bash
quarto preview
```

Opens the presentation in a development server with live reload on file changes.

### Build for Production
```bash
quarto render
```

Generates the HTML presentation in the `docs/` directory, ready for GitHub Pages deployment.

## Project Structure

```
.
├── _quarto.yml          # Quarto configuration
├── index.qmd            # Main slide file
├── docs/                # Generated HTML (tracked in git for GitHub Pages)
└── README.md            # This file
```

## Editing Slides

Slides are written in `index.qmd` using Quarto markdown syntax.

- Use `##` for slide headers
- Use `:::{.notes}` for speaker notes
- Add columns, callouts, and code blocks as needed

See [Quarto Reveal.js docs](https://quarto.org/docs/presentations/revealjs/) for full documentation.

## Diagram Support

### GraphViz Diagrams
Create directed and undirected graphs using the `{dot}` code block:

```{dot}
digraph G {
  A -> B;
  B -> C;
}
```

See [GraphViz documentation](https://graphviz.org/doc/info/lang.html) for all supported formats and syntax.

### Mermaid Diagrams
Create flowcharts, sequence diagrams, Gantt charts, and more using the `{mermaid}` code block:

```{mermaid}
flowchart LR
  A[Start] --> B{Decision}
  B -->|Yes| C[Process]
  C --> D[End]
```

Supported diagram types: flowchart, sequence, gantt, pie, class, state, git, ER, user journey.
See [Mermaid documentation](https://mermaid.js.org/) for details.

## Navigation

- **Arrow keys** or **space**: Navigate slides
- **S**: Speaker view
- **F**: Full screen
- **ESC**: Slide overview
- **?**: Help menu

## Deployment

The `docs/` directory is committed to git and served automatically by GitHub Pages when configured in repository settings. No additional deployment steps required—just push to main.

## Tips

- Keep slides focused and concise
- Use speaker notes (`:::{.notes}`) for longer explanations
- Test code blocks in your preferred environment
- Use consistent styling with Reveal.js themes

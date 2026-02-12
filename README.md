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

Generates the HTML presentation in the `_output/` directory.

## Project Structure

```
.
├── _quarto.yml          # Quarto configuration
├── index.qmd            # Main slide file
├── _output/             # Generated HTML/PDF (in .gitignore)
└── README.md            # This file
```

## Editing Slides

Slides are written in `index.qmd` using Quarto markdown syntax.

- Use `##` for slide headers
- Use `:::notes` for speaker notes
- Add columns, callouts, and code blocks as needed

See [Quarto Reveal.js docs](https://quarto.org/docs/presentations/revealjs/) for full documentation.

## Navigation

- **Arrow keys** or **space**: Navigate slides
- **S**: Speaker view
- **F**: Full screen
- **ESC**: Slide overview
- **?**: Help menu

## Deployment

The rendered HTML in `_output/` can be deployed to:
- GitHub Pages (configure in repository settings)
- Any static host (Netlify, Vercel, etc.)
- Web server (Apache, Nginx, etc.)

## Tips

- Keep slides focused and concise
- Use speaker notes (`::notes`) for longer explanations
- Test code blocks in your preferred environment
- Use consistent styling with Reveal.js themes

# Snippet Converter

A simple web application to convert between plain text/markdown snippets and JSON format for snippet management systems.

## Features

- **Bi-directional Conversion**: Convert text/markdown to JSON and vice versa
- **Auto-detection**: Automatically detects input format
- **Batch Processing**: Handle multiple snippets at once using `---` as separator
- **Metadata Management**: Add language, description, tags, and flags (favorite/pinned)
- **Title Extraction**: Auto-extracts titles from markdown headings or use custom titles
- **Clean Interface**: Split-view design with draggable divider
- **Syntax Highlighting**: JSON output with color-coded syntax
- **Export Options**: Copy to clipboard or download as JSON file

## Usage

### Text to JSON
1. Paste your plain text or markdown snippets in the left panel
2. Use `---` to separate multiple snippets
3. Fill in metadata fields (title, language, description, tags)
4. Toggle favorite/pinned flags as needed
5. Copy or download the generated JSON

### JSON to Text
1. Paste JSON snippet data in the left panel
2. View the formatted text preview on the right
3. The app automatically detects JSON input and switches modes

## Local Development

Simply open `index.html` in a web browser. No build process or dependencies required.

## GitHub Pages

This app is deployed via GitHub Pages and runs entirely in the browser.

## License

MIT License - feel free to use and modify as needed.

# Snippet Converter

A powerful, accessible web application for converting between plain text/markdown snippets and JSON format for snippet management systems.

![Version](https://img.shields.io/badge/version-1.1.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Accessibility](https://img.shields.io/badge/a11y-WCAG%202.1-brightgreen.svg)

## 🌟 Features

### Core Functionality
- **Bi-directional Conversion**: Seamlessly convert between text/markdown and JSON formats
- **Auto-detection**: Intelligently detects input format and switches modes automatically
- **Batch Processing**: Handle multiple snippets at once using `---` as separator
- **Smart Title Extraction**: Auto-extracts titles from markdown headings (`#` syntax)
- **Unique IDs**: Generates proper UUIDs for each snippet using crypto.randomUUID()

### Metadata Management
- **Language**: Specify programming language for syntax highlighting
- **Description**: Add contextual information about your snippets
- **Tags**: Organize snippets with comma-separated tags
- **Flags**: Mark snippets as favorite (★) or pinned (📌)
- **Timestamps**: Automatic `createdAt` and `updatedAt` timestamps

### User Interface
- **Split-view Design**: Resizable panels with draggable divider
- **Syntax Highlighting**: Beautiful JSON output with color-coded tokens
- **Dark Theme Output**: Easy-on-the-eyes code display
- **Interactive Demo**: Try it instantly with the "Try Demo" button
- **Real-time Conversion**: See results as you type

### Export & Copy
- **Copy to Clipboard**: One-click copy with visual feedback
- **Download JSON**: Save snippets with timestamped filenames
- **Validation**: Prevents copying/downloading invalid or error content

### Accessibility ♿
- **WCAG 2.1 Compliant**: Full keyboard navigation support
- **ARIA Labels**: Comprehensive screen reader support
- **Keyboard Shortcuts**:
  - `Ctrl/Cmd + C`: Copy to clipboard
  - `Ctrl/Cmd + S`: Download JSON
  - `Ctrl/Cmd + M`: Toggle mode
  - `Ctrl/Cmd + L`: Focus input area
  - `Escape`: Clear focus
- **Focus Management**: Clear visual focus indicators
- **Semantic HTML**: Proper roles and landmarks

### Error Handling
- **Comprehensive Validation**: Clear error messages for invalid input
- **JSON Validation**: Syntax error detection with helpful hints
- **Empty State Handling**: Friendly messages when no content is present
- **Edge Case Protection**: Robust error handling throughout

## 🚀 Quick Start

### Try it Online
**Live Demo**: [https://YOUR-USERNAME.github.io/snippet-converter](https://YOUR-USERNAME.github.io/snippet-converter)

### Local Development
No installation required! Just open the file:
```bash
open index.html
# or
python -m http.server 8000
# Then visit http://localhost:8000
```

## 📖 Usage Guide

### Text to JSON Mode

1. **Input Your Snippets**
   - Click "Try Demo" for sample data or paste your own
   - Use `---` to separate multiple snippets
   - Start lines with `#` for automatic title extraction

2. **Add Metadata** (optional)
   - Title: Leave blank for auto-generation
   - Language: e.g., `javascript`, `python`, `markdown`
   - Description: Brief explanation
   - Tags: Comma-separated (e.g., `utility, helper, api`)
   - Check favorite/pinned as needed

3. **Export**
   - Click "Copy to Clipboard" or use `Ctrl/Cmd + C`
   - Click "Download JSON" or use `Ctrl/Cmd + S`

### JSON to Text Mode

1. **Paste JSON Data**
   - Paste valid JSON snippet data in the left panel
   - Supports both single objects and arrays
   - Auto-switches to JSON mode when detected

2. **View Preview**
   - See formatted text output with metadata
   - All snippet properties are displayed
   - Ready to copy or use elsewhere

## 💡 Examples

### Input (Text)
```markdown
# Quick Sort Algorithm
A fast sorting algorithm that uses divide-and-conquer.

function quickSort(arr) {
    if (arr.length <= 1) return arr;
    const pivot = arr[arr.length - 1];
    const left = arr.filter((x, i) => x <= pivot && i < arr.length - 1);
    const right = arr.filter(x => x > pivot);
    return [...quickSort(left), pivot, ...quickSort(right)];
}
```

### Output (JSON)
```json
[
  {
    "id": "a1b2c3d4-e5f6-7890-abcd-ef1234567890",
    "title": "Quick Sort Algorithm",
    "content": "function quickSort(arr) {...}",
    "language": "javascript",
    "description": "Useful JavaScript code snippets",
    "tags": ["algorithms", "sorting"],
    "favorite": false,
    "pinned": false,
    "createdAt": "2025-11-18T12:00:00.000Z",
    "updatedAt": "2025-11-18T12:00:00.000Z"
  }
]
```

## 🎨 Technology Stack

- **Frontend**: Vanilla HTML5, CSS3, JavaScript (ES6+)
- **Architecture**: Single-file web application
- **Dependencies**: None (100% standalone)
- **Deployment**: GitHub Pages (static hosting)
- **Browser Support**: All modern browsers (Chrome, Firefox, Safari, Edge)

## 🔧 Technical Details

### Security
- XSS Protection: All user input is properly escaped
- No external requests: Runs entirely client-side
- No data collection: Complete privacy

### Performance
- Fast load time: Single 50KB HTML file
- No build process: Direct browser execution
- Instant conversion: Real-time processing

### Browser Compatibility
- Requires modern browser with ES6 support
- Uses `crypto.randomUUID()` with fallback
- Clipboard API with error handling

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines
- Maintain accessibility standards
- Add error handling for new features
- Test keyboard navigation
- Keep the single-file architecture
- Update this README with new features

## 📝 Changelog

### Version 1.1.0 (2025-11-18)
- ✅ Fixed mode toggle bug
- ✅ Added comprehensive error handling
- ✅ Improved input validation
- ✅ Full accessibility support (ARIA, keyboard navigation)
- ✅ Added keyboard shortcuts
- ✅ Implemented demo button with sample data
- ✅ Better UUID generation (crypto.randomUUID)
- ✅ Visual feedback for all actions
- ✅ Removed duplicate files

### Version 1.0.0 (Initial Release)
- Basic text to JSON conversion
- JSON to text preview
- Metadata management
- Copy and download functionality

## 📄 License

MIT License - see LICENSE file for details

## 🙏 Acknowledgments

- Built with accessibility in mind
- Inspired by the need for simple snippet management
- No dependencies = no vulnerabilities

## 📧 Support

If you encounter issues or have suggestions:
- Open an issue on GitHub
- Check existing issues for solutions
- Contribute improvements via pull requests

---

**Made with ❤️ for developers who love simplicity**

# Snippet Converter

A powerful, accessible web application for converting between plain text/markdown snippets and JSON format for snippet management systems.

![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Accessibility](https://img.shields.io/badge/a11y-WCAG%202.1-brightgreen.svg)

## 🌟 Features

### Core Functionality
- **Bi-directional Conversion**: Seamlessly convert between text/markdown and JSON formats
- **Auto-detection**: Intelligently detects input format and switches modes automatically
- **Batch Processing**: Handle multiple snippets at once using `---` as separator
- **Smart Title Extraction**: Auto-extracts titles from markdown headings (`#` syntax)
- **Unique IDs**: Generates proper UUIDs for each snippet using crypto.randomUUID()

### File Upload & Import
- **Drag & Drop**: Drag files directly onto the input area with visual feedback
- **Upload Button**: Click to browse and upload .txt, .md, or .json files
- **File Validation**: Automatic file type checking with helpful error messages
- **Auto-Mode Detection**: Automatically switches to the correct mode based on file content

### Export Options
- **Multiple Formats**: Export in JSON, Plain Text, Markdown, or CSV
- **Copy to Clipboard**: One-click copy with visual feedback and toast notifications
- **Download Files**: Save snippets with timestamped filenames
- **Format Selector**: Choose your preferred export format from dropdown

### Export Format Details
- **JSON**: Standard structured format, perfect for APIs and data interchange
- **Plain Text**: Readable format with headers (TITLE, LANGUAGE, DESCRIPTION, etc.)
- **Markdown**: Beautiful formatted output with code blocks and syntax highlighting
- **CSV**: Spreadsheet-compatible format for Excel, Google Sheets, etc.

### Metadata Management
- **Language**: Specify programming language for syntax highlighting
- **Description**: Add contextual information about your snippets
- **Tags**: Organize snippets with comma-separated tags
- **Flags**: Mark snippets as favorite (★) or pinned (📌)
- **Timestamps**: Automatic `createdAt` and `updatedAt` timestamps

### User Interface
- **Split-view Design**: Resizable panels with draggable divider
- **Syntax Highlighting**: Beautiful JSON output with color-coded tokens
- **Dark Mode**: Full dark theme with system preference detection
- **Theme Toggle**: macOS-style circular button (🌙/☀️)
- **Real-time Conversion**: See results as you type
- **Toast Notifications**: Modern, non-intrusive notifications for all actions
- **Responsive Design**: Fully optimized for mobile, tablet, and desktop

### Reset Controls
- **Reset Input**: Clear only the input text (preserves metadata)
- **Reset All**: Clear everything including input and all metadata
- **Instant Action**: No confirmation needed - actions shown with warning text

### Data Persistence
- **LocalStorage Auto-save**: Automatically saves your work every second
- **Session Restore**: Returns to your last state when you reopen the app
- **Theme Persistence**: Remembers your light/dark mode preference

### Accessibility ♿
- **WCAG 2.1 Compliant**: Full keyboard navigation support
- **ARIA Labels**: Comprehensive screen reader support
- **Keyboard Shortcuts**:
  - `Ctrl/Cmd + C`: Copy to clipboard
  - `Ctrl/Cmd + S`: Download file
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
**Live Demo**: [https://daveczarn.github.io/snippet-converter](https://daveczarn.github.io/snippet-converter)

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
   - Paste text directly or drag & drop a file
   - Click "Upload File" to browse for files
   - Use `---` to separate multiple snippets
   - Start lines with `#` for automatic title extraction

2. **Add Metadata** (optional)
   - Title: Leave blank for auto-generation
   - Language: e.g., `javascript`, `python`, `markdown`
   - Description: Brief explanation
   - Tags: Comma-separated (e.g., `utility, helper, api`)
   - Check favorite/pinned as needed

3. **Export**
   - Select format: JSON, Plain Text, Markdown, or CSV
   - Click "Copy to Clipboard" or use `Ctrl/Cmd + C`
   - Click "Download" or use `Ctrl/Cmd + S`

### JSON to Text Mode

1. **Paste JSON Data**
   - Paste valid JSON snippet data or drag & drop a .json file
   - Supports both single objects and arrays
   - Auto-switches to JSON mode when detected

2. **View Preview**
   - See formatted text output with metadata
   - All snippet properties are displayed
   - Ready to copy or use elsewhere

### File Upload Methods

**Drag & Drop**:
- Drag any .txt, .md, or .json file onto the input textarea
- Visual feedback with dashed blue border
- Automatic file type detection and mode switching

**Upload Button**:
- Click "Upload File" in the info bar
- Browse and select your file
- Supports .txt, .md, and .json formats

### Reset Controls

**Reset Input**:
- Clears only the input textarea
- Preserves all metadata fields
- Useful for trying different snippets with same metadata

**Reset All**:
- Clears input and all metadata fields
- Removes data from localStorage
- Fresh start for new snippets

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
- File type validation: Only accepts safe file formats

### Performance
- Fast load time: Single ~80KB HTML file
- No build process: Direct browser execution
- Instant conversion: Real-time processing
- Efficient localStorage: Debounced auto-save (1 second)

### Browser Compatibility
- Requires modern browser with ES6 support
- Uses `crypto.randomUUID()` with fallback
- Clipboard API with error handling
- Drag & Drop API for file uploads

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

### Version 2.0.0 (2025-11-18)
**Major Features:**
- ✨ Drag & drop file upload with visual feedback
- 📤 Multiple export formats (JSON, Plain Text, Markdown, CSV)
- 🔄 Split reset controls (Reset Input vs Reset All)
- 🔔 Toast notification system (replaced all alerts)
- 🌙 macOS-style circular theme toggle
- 💾 LocalStorage auto-save
- 📱 Fully responsive mobile design

**UI Improvements:**
- 🎨 Redesigned header layout
- 🔘 Icon-based theme toggle
- ⚠️ Removed confirmation dialogs for faster workflow
- ✨ Better visual feedback on all actions
- 🎯 Improved button placement and grouping

**Technical:**
- Better UUID generation (crypto.randomUUID)
- Comprehensive error handling
- Input validation improvements
- Dark mode enhancements

### Version 1.1.0 (2025-11-18)
- ✅ Fixed mode toggle bug
- ✅ Added comprehensive error handling
- ✅ Improved input validation
- ✅ Full accessibility support (ARIA, keyboard navigation)
- ✅ Added keyboard shortcuts
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
- Modern UX patterns for better user experience

## 📧 Support

If you encounter issues or have suggestions:
- Open an issue on GitHub
- Check existing issues for solutions
- Contribute improvements via pull requests

---

**Made with ❤️ for developers who love simplicity**

# Technology Stack

This document outlines the technological stack and computer languages used in the BentoPDF project.

## Core Languages

### TypeScript
- **Version**: ~5.9.3
- **Usage**: Primary development language for all frontend code
- **Configuration**: `tsconfig.json`, ES2022 target

### JavaScript
- **Type**: ES Module (ESM)
- **Usage**: Build scripts, workers, and configuration files
- **Files**: `.mjs` and `.js` files

### HTML
- **Usage**: Page templates and markup
- **Features**: Handlebars templating for dynamic content

### CSS
- **Usage**: Styling
- **Framework**: TailwindCSS v4.1.14

## Build Tools & Bundlers

### Vite
- **Version**: ^7.1.11
- **Usage**: Primary build tool and dev server
- **Plugins**:
  - `@vitejs/plugin-basic-ssl` - SSL support
  - `vite-plugin-compression` - Gzip and Brotli compression
  - `vite-plugin-handlebars` - Template processing
  - `vite-plugin-node-polyfills` - Node.js polyfills for browser
  - `vite-plugin-static-copy` - Static asset copying

### Node.js
- **Version**: 20 (Alpine Linux in Docker)
- **Package Manager**: npm
- **Configuration**: `package.json`

## Frontend Frameworks & Libraries

### PDF Libraries
- **pdf-lib** (^1.17.1) - PDF creation and manipulation
- **pdfjs-dist** (^5.4.296) - PDF rendering and viewing
- **pdfkit** (^0.17.2) - PDF generation
- **jspdf** (^4.0.0) - Client-side PDF generation
- **jspdf-autotable** (^5.0.2) - Table generation in PDFs
- **@neslinesli93/qpdf-wasm** (^0.3.0) - QPDF WebAssembly

### Document Conversion
- **@matbee/libreoffice-converter** (^2.3.1) - Office document conversion
- **@kenjiuno/msgreader** (^1.27.1-alpha.1) - Email file reading
- **xlsx** - Excel file processing
- **papaparse** (^5.5.3) - CSV parsing
- **markdown-it** (^14.1.0) - Markdown processing with multiple plugins

### Image Processing
- **html2canvas** (^1.4.1) - HTML to canvas conversion
- **cropperjs** (^1.6.1) - Image cropping
- **heic2any** (^0.0.4) - HEIC image conversion
- **tiff** (^7.1.2) - TIFF image handling
- **utif** (^3.1.0) - TIFF file utilities
- **tesseract.js** (^6.0.1) - OCR (Optical Character Recognition)

### UI Components & Icons
- **@phosphor-icons/web** (^2.1.2) - Icon library
- **lucide** (^0.546.0) - Icon library
- **sortablejs** (^1.15.6) - Drag-and-drop sorting

### Internationalization
- **i18next** (^25.7.2) - Internationalization framework
- **i18next-browser-languagedetector** (^8.2.0) - Language detection
- **i18next-http-backend** (^3.0.2) - Translation loading

### Fonts
- Multiple `@fontsource` packages for web fonts

### Utilities
- **node-forge** (^1.3.3) - Cryptography
- **zgapdfsigner** (^2.7.5) - PDF digital signing
- **archiver** (^7.0.1) - Archive creation
- **jszip** (^3.10.1) - ZIP file handling
- **mermaid** (^11.12.2) - Diagram generation
- **highlight.js** (^11.11.1) - Syntax highlighting
- **postal-mime** (^2.7.1) - MIME message parsing

## Testing

### Vitest
- **Version**: ^3.2.4
- **Configuration**: `vitest.config.ts`
- **Features**:
  - Unit testing
  - UI mode (`@vitest/ui`)
  - Code coverage (`@vitest/coverage-v8`)
  - Global test APIs
  - JSDOM environment (^27.0.1)

### Testing Libraries
- **@testing-library/dom** (^10.4.1) - DOM testing utilities

## Code Quality & Linting

### ESLint
- **Version**: ^9.39.2
- **Configuration**: `eslint.config.mjs`
- **Plugins**:
  - `@eslint/js` - Core ESLint rules
  - `typescript-eslint` (^8.51.0) - TypeScript linting
  - `eslint-config-prettier` (^10.1.8) - Prettier integration

### Prettier
- **Version**: ^3.6.2
- **Configuration**: `.prettierrc`
- **Features**: Code formatting

### Husky
- **Version**: ^9.1.7
- **Usage**: Git hooks

### lint-staged
- **Version**: ^16.2.7
- **Usage**: Pre-commit linting

## Documentation

### VitePress
- **Version**: ^1.6.4
- **Usage**: Documentation site generator
- **Framework**: Vue.js ^3.5.26

## Containerization & Deployment

### Docker
- **Base Images**:
  - Build: `node:20-alpine`
  - Production: `nginx-unprivileged:stable-alpine-slim`
- **Configuration**: `Dockerfile`, `docker-compose.yml`, `docker-compose.dev.yml`
- **Web Server**: Nginx

### Kubernetes
- **Tool**: Helm
- **Configuration**: `chart/` directory
- **Chart Version**: 0.2.0

### Cloudflare Workers
- **Configuration**: `cloudflare/wrangler.toml`
- **Workers**: CORS proxy, WASM workers

## WebAssembly (WASM)

- **qpdf.wasm** - PDF processing
- **pdfium.wasm** (embedpdf-snippet) - PDF rendering
- **pdfjs-viewer/wasm/** - PDF.js WASM modules
  - `qcms_bg.wasm` - Color management
  - `openjpeg.wasm` - JPEG2000 support

## Web Workers

Custom workers for async PDF processing:
- `add-attachments.worker.js`
- `edit-attachments.worker.js`
- `extract-attachments.worker.js`
- `alternate-merge.worker.js`
- `json-to-pdf.worker.js`
- `pdf-to-json.worker.js`
- `merge.worker.js`
- `table-of-contents.worker.js`

## Development Tools

### Version Control
- **Git** - Source control
- **GitHub Actions** - CI/CD workflows

### Build Scripts
- Custom Node.js scripts in `scripts/` directory
- Version management
- Release automation
- i18n page generation
- Sitemap generation
- Documentation building

## Runtime Environment

- **Target**: Modern browsers with ES2022 support
- **DOM APIs**: DOM, DOM.Iterable, WebWorker
- **Module System**: ES Modules (ESM)
- **Compression**: Gzip and Brotli support

## Security

- **CORS Headers**: Cross-Origin security policies
- **Content Security**: COOP and COEP headers
- **Cryptography**: node-forge library
- **Digital Signatures**: zgapdfsigner

## License

- **AGPL-3.0-only**

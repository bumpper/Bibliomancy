# Bibliomancy - Biblical Scripture Oracle

A desktop application for practicing Bibliomancy - the ancient art of biblical divination through random scripture verses. Built with Tauri 2.0 for a fast, secure, and lightweight experience.

## About

Bibliomancy is a form of divination that uses sacred texts to seek divine guidance. This application presents random verses from the King James Bible on a beautiful parchment-styled interface, allowing users to receive spiritual guidance through scripture.

## Features

- **Complete King James Bible**: Access to all 31,102 verses from the KJV Bible
- **Beautiful Parchment Interface**: Authentic parchment scroll design with fire text effects
- **Random Verse Selection**: Each reload presents a new random verse for divine guidance
- **Verse References**: Direct links to Bible Gateway and BibleHub for deeper study
- **Help Documentation**: Comprehensive guide on using bibliomancy
- **Lightweight Desktop App**: Fast, secure, and runs natively on your system

## Quick Start

1. **Development Mode**:
   ```bash
   npm install
   npm run dev
   ```

2. **Build Application**:
   ```bash
   npm run build
   ```

3. **Quick Scripts** (Windows):
   - `quick-dev.bat` - Start development server
   - `quick-build.bat` - Build production application

## How to Use

1. Launch the application
2. A random Bible verse will be displayed on a parchment scroll
3. Click the "RELOAD" button to receive a new verse
4. Click the "?" button for help and guidance on bibliomancy
5. Click on verse references to study the full chapter context

## Technology Stack

- **Frontend**: HTML, CSS, JavaScript
- **Backend**: Rust with Tauri 2.0
- **Build System**: Tauri CLI
- **Package Manager**: npm

## Project Structure

```
bibliomancy/
├── src/                    # Frontend source files
│   ├── index.html         # Main HTML file
│   ├── bibliomancy.js     # Bible verses and logic
│   ├── analytics.js       # Analytics tracking
│   ├── help.html          # Help documentation
│   └── [images]           # Parchment, background, icons
├── src-tauri/             # Tauri backend
│   ├── src/               # Rust source code
│   ├── icons/             # Application icons
│   ├── Cargo.toml         # Rust dependencies
│   └── tauri.conf.json    # Tauri configuration
└── package.json           # Node.js dependencies
```

## Documentation

- [START_HERE.md](START_HERE.md) - Begin here for setup
- [BUILD_INSTRUCTIONS.md](BUILD_INSTRUCTIONS.md) - Detailed build guide
- [SETUP.md](SETUP.md) - Environment setup
- [PROJECT_SUMMARY.md](PROJECT_SUMMARY.md) - Project overview
- [CHECKLIST.md](CHECKLIST.md) - Development checklist

## License

MIT License - Copyright © 2025 Radius.Center

## Credits

- Bible text: King James Version (Public Domain)
- Application: Radius.Center
- Framework: Tauri 2.0

## Support

For issues, questions, or contributions, please visit the project repository.

---

**Note**: This application is for entertainment and spiritual exploration purposes. The random selection of verses is not a substitute for proper biblical study or professional spiritual guidance.

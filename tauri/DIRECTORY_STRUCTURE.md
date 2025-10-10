# Directory Structure - Bibliomancy

Complete overview of the project's file organization and structure.

## Root Directory

```
bibliomancy/
├── src/                          # Frontend source files
├── src-tauri/                    # Tauri backend (Rust)
├── node_modules/                 # npm dependencies (generated)
├── package.json                  # npm configuration
├── package-lock.json            # npm lock file (generated)
├── .gitignore                   # Git exclusions
├── README.md                    # Project overview
├── START_HERE.md                # Quick start guide
├── BUILD_INSTRUCTIONS.md        # Build guide
├── SETUP.md                     # Environment setup
├── PROJECT_SUMMARY.md           # Project details
├── CHECKLIST.md                 # Development checklist
├── DIRECTORY_STRUCTURE.md       # This file
├── BUILD_STATUS.md              # Build status tracking
├── quick-dev.bat                # Windows dev script
└── quick-build.bat              # Windows build script
```

## Frontend Directory (`src/`)

```
src/
├── index.html                   # Main application HTML
├── bibliomancy.js               # Bible verses array (31,102 verses)
├── analytics.js                 # Analytics tracking
├── help.html                    # Help documentation
├── parchment.jpg                # Parchment scroll background
├── Tanakh.jpg                   # Main background image
├── favicon.png                  # Browser favicon (PNG)
├── favicon.ico                  # Browser favicon (ICO)
├── invis.gif                    # Invisible spacer image
└── help_files/                  # Help system resources
    ├── colorschememapping.xml   # Color scheme data
    ├── filelist.xml             # File list data
    └── themedata.thmx           # Theme data
```

### Frontend File Descriptions

**index.html**
- Main application interface
- Parchment modal structure
- Styling and animations
- RELOAD and Help buttons

**bibliomancy.js**
- Array of 31,102 Bible verses
- Random verse selection logic
- Verse display functionality
- Links to Bible Gateway and BibleHub

**analytics.js**
- Analytics tracking code
- User interaction monitoring
- Optional feature

**help.html**
- User guide and instructions
- Bibliomancy explanation
- Usage tips

**Images**
- `parchment.jpg`: Scroll background texture
- `Tanakh.jpg`: Main application background
- `favicon.png/ico`: Application icons
- `invis.gif`: Layout helper

## Backend Directory (`src-tauri/`)

```
src-tauri/
├── src/                         # Rust source code
│   ├── main.rs                  # Application entry point
│   └── lib.rs                   # Core application logic
├── icons/                       # Application icons
│   ├── 32x32.png               # Small icon
│   ├── 128x128.png             # Medium icon
│   ├── 128x128@2x.png          # Retina icon
│   ├── icon.png                # Base icon
│   ├── icon.ico                # Windows icon
│   └── icon.icns               # macOS icon
├── capabilities/                # Permission definitions
│   └── default.json            # Default capabilities
├── target/                      # Build output (generated)
│   ├── debug/                  # Debug builds
│   └── release/                # Release builds
├── Cargo.toml                   # Rust dependencies
├── Cargo.lock                   # Rust lock file (generated)
├── tauri.conf.json             # Tauri configuration
├── build.rs                     # Build script
└── .gitignore                  # Rust-specific exclusions
```

### Backend File Descriptions

**src/main.rs**
- Application entry point
- Calls lib.rs run function
- Windows subsystem configuration

**src/lib.rs**
- Tauri builder setup
- Plugin initialization
- Window configuration
- DevTools setup (debug mode)

**Cargo.toml**
- Rust package metadata
- Dependencies (tauri, serde, etc.)
- Build features
- Optimization settings

**tauri.conf.json**
- Application metadata
- Window configuration
- Bundle settings
- Security policies
- Build commands

**build.rs**
- Pre-build script
- Tauri build integration

**capabilities/default.json**
- Permission definitions
- Security capabilities
- Shell access permissions

## Generated Directories

### node_modules/
```
node_modules/
├── @tauri-apps/              # Tauri npm packages
│   └── cli/                  # Tauri CLI
└── [other dependencies]      # npm packages
```

### target/ (Rust Build Output)
```
target/
├── debug/                    # Debug builds
│   ├── bibliomancy.exe      # Debug executable
│   └── [build artifacts]    # Intermediate files
└── release/                  # Release builds
    ├── bibliomancy.exe      # Optimized executable
    └── bundle/              # Installers
        ├── msi/             # MSI installer
        ├── nsis/            # NSIS installer
        ├── deb/             # Debian package
        ├── rpm/             # RPM package
        └── dmg/             # macOS disk image
```

## Configuration Files

### Root Level
- **package.json**: npm scripts, dependencies, metadata
- **package-lock.json**: Locked dependency versions
- **.gitignore**: Files to exclude from Git

### Tauri Level
- **Cargo.toml**: Rust package configuration
- **Cargo.lock**: Locked Rust dependencies
- **tauri.conf.json**: Application configuration
- **build.rs**: Build-time script

## Documentation Files

### User Documentation
- **README.md**: Project overview and quick start
- **START_HERE.md**: Beginner's guide
- **SETUP.md**: Environment setup instructions

### Developer Documentation
- **BUILD_INSTRUCTIONS.md**: Detailed build guide
- **PROJECT_SUMMARY.md**: Technical overview
- **CHECKLIST.md**: Development tasks
- **DIRECTORY_STRUCTURE.md**: This file
- **BUILD_STATUS.md**: Build status tracking

## Build Scripts

### Windows Batch Files
- **quick-dev.bat**: Start development server
- **quick-build.bat**: Build production version

## File Sizes (Approximate)

### Source Files
- `bibliomancy.js`: ~2-3 MB (31,102 verses)
- `index.html`: ~10 KB
- `parchment.jpg`: ~200-500 KB
- `Tanakh.jpg`: ~200-500 KB
- Other files: <100 KB each

### Build Output
- Debug executable: ~15-20 MB
- Release executable: ~8-12 MB
- MSI installer: ~10-15 MB
- NSIS installer: ~10-15 MB

## Important Paths

### Development
```
Current Working Directory: C:/Users/Dan Neiderhiser/Desktop/bibliomancy
Frontend Source: ./src/
Backend Source: ./src-tauri/src/
Configuration: ./src-tauri/tauri.conf.json
```

### Build Output
```
Debug Build: ./src-tauri/target/debug/
Release Build: ./src-tauri/target/release/
Installers: ./src-tauri/target/release/bundle/
```

## File Permissions

### Executable Files
- `*.bat`: Windows batch scripts
- `bibliomancy.exe`: Application executable

### Configuration Files
- `*.json`: JSON configuration
- `*.toml`: TOML configuration
- `*.rs`: Rust source code

### Assets
- `*.html`: HTML files
- `*.js`: JavaScript files
- `*.jpg`, `*.png`, `*.ico`: Images
- `*.gif`: GIF images

## Excluded Files (.gitignore)

### Node.js
- `node_modules/`
- `*.log`
- `dist/`
- `dist-ssr/`

### Rust
- `target/`
- `Cargo.lock` (in some cases)

### IDE
- `.vscode/` (except extensions.json)
- `.idea/`
- `*.suo`

### OS
- `.DS_Store` (macOS)
- `Thumbs.db` (Windows)

## Navigation Guide

### To Find...

**Main Application Code**:
- Frontend: `src/index.html`, `src/bibliomancy.js`
- Backend: `src-tauri/src/lib.rs`

**Configuration**:
- npm: `package.json`
- Tauri: `src-tauri/tauri.conf.json`
- Rust: `src-tauri/Cargo.toml`

**Documentation**:
- Start: `START_HERE.md`
- Build: `BUILD_INSTRUCTIONS.md`
- Setup: `SETUP.md`

**Assets**:
- Images: `src/*.jpg`, `src/*.png`
- Icons: `src-tauri/icons/`
- Help: `src/help.html`, `src/help_files/`

**Build Output**:
- Executable: `src-tauri/target/release/bibliomancy.exe`
- Installers: `src-tauri/target/release/bundle/`

## Directory Best Practices

### Do's
- ✅ Keep source files in `src/`
- ✅ Keep Rust code in `src-tauri/src/`
- ✅ Use relative paths in code
- ✅ Document new files
- ✅ Follow naming conventions

### Don'ts
- ❌ Don't commit `node_modules/`
- ❌ Don't commit `target/`
- ❌ Don't modify generated files
- ❌ Don't use absolute paths
- ❌ Don't mix frontend/backend code

## Maintenance

### Regular Cleanup
```bash
# Clean Rust build cache
cd src-tauri
cargo clean

# Clean npm cache
npm cache clean --force

# Remove node_modules
rm -rf node_modules
npm install
```

### Backup Important Files
- `src/` directory (all frontend files)
- `src-tauri/src/` (Rust source)
- `src-tauri/tauri.conf.json`
- `package.json`
- Documentation files

---

**Last Updated**: 2025-01-XX
**Total Files**: ~30 source files + dependencies
**Total Size**: ~3-5 MB source + ~200 MB dependencies

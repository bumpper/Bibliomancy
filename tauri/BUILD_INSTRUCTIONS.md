# Build Instructions for Bibliomancy

This guide provides detailed instructions for building the Bibliomancy desktop application.

## Prerequisites

Before building, ensure you have the following installed:

1. **Node.js** (v16 or higher)
   - Download from: https://nodejs.org/
   - Verify: `node --version`

2. **Rust** (latest stable)
   - Download from: https://rustup.rs/
   - Verify: `rustc --version`

3. **Tauri CLI** (installed via npm)
   - Will be installed with `npm install`

## Initial Setup

1. **Navigate to Project Directory**:
   ```bash
   cd C:\Users\Dan Neiderhiser\Desktop\bibliomancy
   ```

2. **Install Dependencies**:
   ```bash
   npm install
   ```
   This installs the Tauri CLI and other required packages.

## Development Build

### Option 1: Using npm Scripts

```bash
npm run dev
```

This will:
- Start the Tauri development server
- Open the application window
- Enable hot-reload for frontend changes
- Open DevTools automatically (in debug mode)

### Option 2: Using Quick Script (Windows)

Double-click `quick-dev.bat` or run:
```bash
quick-dev.bat
```

## Production Build

### Option 1: Using npm Scripts

```bash
npm run build
```

This creates optimized production builds for your platform.

### Option 2: Using Quick Script (Windows)

Double-click `quick-build.bat` or run:
```bash
quick-build.bat
```

### Platform-Specific Builds

**Windows**:
```bash
npm run build:windows
```
Creates: `.msi` and `.exe` installers

**Linux**:
```bash
npm run build:linux
```
Creates: `.deb` and `.rpm` packages

**macOS**:
```bash
npm run build:macos
```
Creates: `.dmg` and `.app` bundle

## Build Output

After building, find your application in:
```
src-tauri/target/release/
```

Installers are located in:
```
src-tauri/target/release/bundle/
```

### Windows Output Files
- `bibliomancy.exe` - Standalone executable
- `msi/bibliomancy_1.0.0_x64_en-US.msi` - MSI installer
- `nsis/bibliomancy_1.0.0_x64-setup.exe` - NSIS installer

### Linux Output Files
- `deb/bibliomancy_1.0.0_amd64.deb` - Debian package
- `rpm/bibliomancy-1.0.0-1.x86_64.rpm` - RPM package

### macOS Output Files
- `dmg/bibliomancy_1.0.0_x64.dmg` - DMG installer
- `macos/bibliomancy.app` - Application bundle

## Build Configuration

The build is configured in:
- `src-tauri/tauri.conf.json` - Tauri configuration
- `src-tauri/Cargo.toml` - Rust dependencies
- `package.json` - Node.js scripts and dependencies

## Optimization Settings

The release build includes:
- **LTO (Link Time Optimization)**: Enabled
- **Code Stripping**: Enabled
- **Optimization Level**: Size-optimized (`opt-level = "s"`)
- **Panic Strategy**: Abort (smaller binary)

## Troubleshooting

### Build Fails

1. **Clear Cache**:
   ```bash
   cd src-tauri
   cargo clean
   cd ..
   npm run build
   ```

2. **Update Dependencies**:
   ```bash
   npm install
   cd src-tauri
   cargo update
   cd ..
   ```

### Missing Dependencies

If you get errors about missing system dependencies:

**Windows**: Install Visual Studio Build Tools
**Linux**: Install required libraries:
```bash
sudo apt-get install libwebkit2gtk-4.0-dev \
    build-essential \
    curl \
    wget \
    libssl-dev \
    libgtk-3-dev \
    libayatana-appindicator3-dev \
    librsvg2-dev
```

**macOS**: Install Xcode Command Line Tools:
```bash
xcode-select --install
```

### Slow Build Times

First builds are slow due to Rust compilation. Subsequent builds are much faster due to caching.

## Testing the Build

1. **Run the executable directly**:
   ```bash
   ./src-tauri/target/release/bibliomancy.exe
   ```

2. **Install and test the installer**:
   - Run the MSI or NSIS installer
   - Launch from Start Menu
   - Verify all features work

## Build Verification Checklist

- [ ] Application launches successfully
- [ ] Random Bible verses display correctly
- [ ] Parchment background and styling appear properly
- [ ] RELOAD button functions
- [ ] Help button opens help.html
- [ ] Verse links open in external browser
- [ ] Window resizes correctly
- [ ] Application icon displays properly

## Next Steps

After successful build:
1. Test the application thoroughly
2. Create installers for distribution
3. Document any platform-specific issues
4. Update version numbers for releases

## Additional Resources

- [Tauri Documentation](https://tauri.app/)
- [Rust Documentation](https://doc.rust-lang.org/)
- [Cargo Book](https://doc.rust-lang.org/cargo/)

---

For more information, see [SETUP.md](SETUP.md) and [PROJECT_SUMMARY.md](PROJECT_SUMMARY.md).

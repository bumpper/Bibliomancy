# Setup Guide - Bibliomancy

Complete environment setup instructions for the Bibliomancy desktop application.

## System Requirements

### Minimum Requirements
- **OS**: Windows 10/11, macOS 10.13+, or Linux
- **RAM**: 4GB
- **Disk Space**: 2GB free space
- **Internet**: Required for initial setup

### Recommended Requirements
- **OS**: Windows 11, macOS 12+, or Ubuntu 20.04+
- **RAM**: 8GB or more
- **Disk Space**: 5GB free space
- **Internet**: Broadband connection

---

## Prerequisites Installation

### 1. Install Node.js

**Windows**:
1. Download from https://nodejs.org/
2. Run the installer (LTS version recommended)
3. Verify installation:
   ```bash
   node --version
   npm --version
   ```

**macOS**:
```bash
brew install node
```

**Linux**:
```bash
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
```

### 2. Install Rust

**All Platforms**:
1. Visit https://rustup.rs/
2. Follow the installation instructions
3. Restart your terminal
4. Verify installation:
   ```bash
   rustc --version
   cargo --version
   ```

**Windows Additional Steps**:
- Install Visual Studio Build Tools
- Or install Visual Studio Community with C++ development tools

### 3. Install System Dependencies

**Windows**:
- WebView2 (usually pre-installed on Windows 11)
- Visual Studio Build Tools

**macOS**:
```bash
xcode-select --install
```

**Linux (Ubuntu/Debian)**:
```bash
sudo apt update
sudo apt install libwebkit2gtk-4.0-dev \
    build-essential \
    curl \
    wget \
    libssl-dev \
    libgtk-3-dev \
    libayatana-appindicator3-dev \
    librsvg2-dev
```

**Linux (Fedora)**:
```bash
sudo dnf install webkit2gtk3-devel \
    openssl-devel \
    curl \
    wget \
    libappindicator-gtk3 \
    librsvg2-devel
sudo dnf group install "C Development Tools and Libraries"
```

---

## Project Setup

### 1. Navigate to Project Directory

```bash
cd C:\Users\Dan Neiderhiser\Desktop\bibliomancy
```

### 2. Install Project Dependencies

```bash
npm install
```

This will install:
- Tauri CLI (@tauri-apps/cli)
- All required npm packages

**Expected Output**:
```
added XX packages in XXs
```

### 3. Verify Tauri Installation

```bash
npm run tauri --version
```

Should display Tauri CLI version 2.0.0 or higher.

---

## Development Environment Setup

### IDE/Editor Setup

**Visual Studio Code** (Recommended):
1. Install VS Code from https://code.visualstudio.com/
2. Install recommended extensions:
   - rust-analyzer
   - Tauri
   - ESLint
   - Prettier

**Other Editors**:
- Any text editor works
- Syntax highlighting for Rust and JavaScript recommended

### Terminal Setup

**Windows**:
- PowerShell (recommended)
- Command Prompt
- Windows Terminal
- Git Bash

**macOS/Linux**:
- Default terminal
- iTerm2 (macOS)
- Any modern terminal emulator

---

## Configuration

### Environment Variables

No special environment variables required for basic setup.

### Tauri Configuration

Main configuration file: `src-tauri/tauri.conf.json`

Key settings:
```json
{
  "productName": "Bibliomancy",
  "version": "1.0.0",
  "identifier": "center.radius.bibliomancy"
}
```

### Rust Configuration

Cargo configuration: `src-tauri/Cargo.toml`

Optimized for:
- Small binary size
- Fast compilation
- Release builds

---

## Verification Steps

### 1. Check Node.js
```bash
node --version  # Should be v16.0.0 or higher
npm --version   # Should be 8.0.0 or higher
```

### 2. Check Rust
```bash
rustc --version  # Should be 1.70.0 or higher
cargo --version  # Should be 1.70.0 or higher
```

### 3. Check Tauri CLI
```bash
npm run tauri --version  # Should be 2.0.0 or higher
```

### 4. Test Development Build
```bash
npm run dev
```

Expected result:
- Application window opens
- Random Bible verse displays
- No console errors

---

## Troubleshooting

### Node.js Issues

**Problem**: `node: command not found`
**Solution**: 
- Restart terminal after installation
- Add Node.js to PATH manually
- Reinstall Node.js

**Problem**: Permission errors on Linux/macOS
**Solution**:
```bash
sudo chown -R $USER:$USER ~/.npm
sudo chown -R $USER:$USER ~/.config
```

### Rust Issues

**Problem**: `rustc: command not found`
**Solution**:
- Restart terminal
- Run: `source $HOME/.cargo/env`
- Reinstall Rust

**Problem**: Compilation errors
**Solution**:
```bash
rustup update
cargo clean
```

### Tauri Issues

**Problem**: `tauri: command not found`
**Solution**:
```bash
npm install
npm run tauri --version
```

**Problem**: WebView2 missing (Windows)
**Solution**:
- Download from Microsoft
- Usually pre-installed on Windows 11

### Build Issues

**Problem**: Build fails with dependency errors
**Solution**:
```bash
rm -rf node_modules
npm cache clean --force
npm install
```

**Problem**: Rust compilation fails
**Solution**:
```bash
cd src-tauri
cargo clean
cargo update
cd ..
npm run dev
```

---

## Platform-Specific Notes

### Windows
- Ensure Visual Studio Build Tools are installed
- WebView2 is required (pre-installed on Windows 11)
- Use PowerShell or Command Prompt

### macOS
- Xcode Command Line Tools required
- May need to allow app in Security & Privacy settings
- Code signing required for distribution

### Linux
- Install all system dependencies listed above
- May need to install additional libraries
- AppImage format recommended for distribution

---

## Next Steps

After successful setup:

1. ✅ Read [START_HERE.md](START_HERE.md)
2. ✅ Review [BUILD_INSTRUCTIONS.md](BUILD_INSTRUCTIONS.md)
3. ✅ Check [CHECKLIST.md](CHECKLIST.md)
4. ✅ Run `npm run dev` to start development

---

## Additional Resources

- [Tauri Documentation](https://tauri.app/)
- [Rust Book](https://doc.rust-lang.org/book/)
- [Node.js Documentation](https://nodejs.org/docs/)
- [Cargo Book](https://doc.rust-lang.org/cargo/)

---

## Support

If you encounter issues not covered here:
1. Check [BUILD_STATUS.md](BUILD_STATUS.md)
2. Review Tauri troubleshooting guide
3. Check system requirements
4. Verify all prerequisites are installed

---

**Setup Complete?** Run `npm run dev` to start the application!

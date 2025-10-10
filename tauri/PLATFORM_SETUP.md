# Platform-Specific Setup Guide for Bibliomancy

This guide provides detailed setup instructions for each supported platform to prepare your system for building the Bibliomancy Tauri application.

## Table of Contents

- [Windows Setup](#windows-setup)
- [macOS Setup](#macos-setup)
- [Linux Setup (Ubuntu/Debian)](#linux-setup-ubuntudebian)
- [Linux Setup (Fedora/RHEL)](#linux-setup-fedorarhel)
- [Transferring Projects Between Platforms](#transferring-projects-between-platforms)
- [Verification](#verification)

---

## Windows Setup

### 1. Install Node.js

1. Download Node.js LTS from: https://nodejs.org/
2. Run the installer
3. Verify installation:
   ```cmd
   node --version
   npm --version
   ```

### 2. Install Rust

1. Download rustup from: https://rustup.rs/
2. Run `rustup-init.exe`
3. Follow the prompts (default options are fine)
4. Restart your terminal
5. Verify installation:
   ```cmd
   rustc --version
   cargo --version
   ```

### 3. Install Visual Studio Build Tools

**Option A: Visual Studio Community (Full IDE)**
1. Download from: https://visualstudio.microsoft.com/downloads/
2. During installation, select "Desktop development with C++"
3. Install

**Option B: Build Tools Only (Smaller)**
1. Download "Build Tools for Visual Studio" from the same page
2. Select "C++ build tools"
3. Install

### 4. Install WebView2

- **Windows 11:** Pre-installed, no action needed
- **Windows 10:** Download from https://developer.microsoft.com/microsoft-edge/webview2/

### 5. Clone/Copy Project

```cmd
# If using Git
git clone <repository-url>
cd bibliomancy/tauri

# Or copy project files to your desired location
```

### 6. Install Dependencies

```cmd
npm install
```

### 7. Test Setup

```cmd
# Test development mode
quick-dev.bat

# Or
npm run dev:windows
```

---

## macOS Setup

### 1. Install Xcode Command Line Tools

```bash
xcode-select --install
```

Click "Install" when prompted.

### 2. Install Homebrew (Recommended)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Follow the post-installation instructions to add Homebrew to your PATH.

### 3. Install Node.js

**Using Homebrew:**
```bash
brew install node
```

**Or download from:** https://nodejs.org/

Verify installation:
```bash
node --version
npm --version
```

### 4. Install Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Follow the prompts (default options are fine).

Add Rust to your PATH:
```bash
source $HOME/.cargo/env
```

Verify installation:
```bash
rustc --version
cargo --version
```

### 5. Clone/Copy Project

```bash
# If using Git
git clone <repository-url>
cd bibliomancy/tauri

# Or copy project files to your desired location
```

### 6. Install Dependencies

```bash
npm install
```

### 7. Make Scripts Executable

```bash
chmod +x quick-dev.sh quick-build.sh
```

### 8. Test Setup

```bash
./quick-dev.sh

# Or
npm run dev:mac
```

---

## Linux Setup (Ubuntu/Debian)

### 1. Update System

```bash
sudo apt update
sudo apt upgrade -y
```

### 2. Install Node.js

**Option A: Using NodeSource (Recommended)**
```bash
# Install Node.js 20.x
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs
```

**Option B: Using apt (may be older version)**
```bash
sudo apt install -y nodejs npm
```

Verify installation:
```bash
node --version
npm --version
```

### 3. Install Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Follow the prompts (default options are fine).

Add Rust to your PATH:
```bash
source $HOME/.cargo/env
```

Add to your shell profile for persistence:
```bash
echo 'source $HOME/.cargo/env' >> ~/.bashrc
```

Verify installation:
```bash
rustc --version
cargo --version
```

### 4. Install System Dependencies

```bash
sudo apt install -y \
  libwebkit2gtk-4.1-dev \
  build-essential \
  curl \
  wget \
  file \
  libssl-dev \
  libayatana-appindicator3-dev \
  librsvg2-dev
```

### 5. Clone/Copy Project

```bash
# If using Git
git clone <repository-url>
cd bibliomancy/tauri

# Or copy project files to your desired location
```

### 6. Install Dependencies

```bash
npm install
```

### 7. Make Scripts Executable

```bash
chmod +x quick-dev.sh quick-build.sh
```

### 8. Test Setup

```bash
./quick-dev.sh

# Or
npm run dev:linux
```

---

## Linux Setup (Fedora/RHEL)

### 1. Update System

```bash
sudo dnf update -y
```

### 2. Install Node.js

**Option A: Using NodeSource (Recommended)**
```bash
# Install Node.js 20.x
curl -fsSL https://rpm.nodesource.com/setup_20.x | sudo bash -
sudo dnf install -y nodejs
```

**Option B: Using dnf**
```bash
sudo dnf install -y nodejs npm
```

Verify installation:
```bash
node --version
npm --version
```

### 3. Install Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Follow the prompts (default options are fine).

Add Rust to your PATH:
```bash
source $HOME/.cargo/env
```

Add to your shell profile for persistence:
```bash
echo 'source $HOME/.cargo/env' >> ~/.bashrc
```

Verify installation:
```bash
rustc --version
cargo --version
```

### 4. Install System Dependencies

```bash
sudo dnf install -y \
  webkit2gtk4.1-devel \
  openssl-devel \
  curl \
  wget \
  file \
  libappindicator-gtk3-devel \
  librsvg2-devel \
  rpm-build \
  gcc \
  gcc-c++
```

### 5. Clone/Copy Project

```bash
# If using Git
git clone <repository-url>
cd bibliomancy/tauri

# Or copy project files to your desired location
```

### 6. Install Dependencies

```bash
npm install
```

### 7. Make Scripts Executable

```bash
chmod +x quick-dev.sh quick-build.sh
```

### 8. Test Setup

```bash
./quick-dev.sh

# Or
npm run dev:linux
```

---

## Transferring Projects Between Platforms

### What to Transfer

✅ **Include:**
- All source files (`src/` directory)
- Configuration files (`package.json`, `tauri.conf.json`, etc.)
- Scripts (`quick-dev.sh`, `quick-build.sh`, `quick-dev.bat`, `quick-build.bat`)
- Documentation files (`.md` files)
- `.gitignore` and other project files

❌ **Exclude (will be regenerated):**
- `node_modules/` directory
- `src-tauri/target/` directory
- Platform-specific build artifacts

### Transfer Methods

**Method 1: Git (Recommended)**
```bash
# On source machine
git add .
git commit -m "Cross-platform update"
git push

# On target machine
git clone <repository-url>
cd bibliomancy/tauri
npm install
```

**Method 2: USB Drive**
1. Copy project folder (excluding `node_modules` and `target`)
2. Transfer to target machine
3. Run `npm install` on target machine

**Method 3: Network Transfer**
```bash
# Using scp (Linux/macOS)
scp -r bibliomancy/ user@target-machine:/path/to/destination/

# Or use rsync
rsync -av --exclude 'node_modules' --exclude 'target' bibliomancy/ user@target-machine:/path/
```

### After Transfer

On the new platform:

1. **Install platform prerequisites** (see sections above)
2. **Install npm dependencies:**
   ```bash
   npm install
   ```
3. **Make scripts executable (Unix only):**
   ```bash
   chmod +x quick-dev.sh quick-build.sh
   ```
4. **Test the setup:**
   ```bash
   # Windows
   quick-dev.bat
   
   # macOS/Linux
   ./quick-dev.sh
   ```

---

## Verification

### Check Platform Detection

```bash
npm run platform:info
```

This should display:
- Your current platform
- Architecture
- Build targets
- Output directory

### Test Development Mode

**Windows:**
```cmd
quick-dev.bat
```

**macOS/Linux:**
```bash
./quick-dev.sh
```

The Tauri development window should open with the Bibliomancy application.

### Test Build (Optional)

**Windows:**
```cmd
quick-build.bat
```

**macOS/Linux:**
```bash
./quick-build.sh
```

This will create platform-specific installers in `src-tauri/target/release/bundle/`.

---

## Common Issues

### Node.js Version Too Old

**Symptom:** Build fails with Node.js version errors

**Solution:** Install Node.js 16 or higher
```bash
# Check version
node --version

# Update if needed (see platform-specific instructions above)
```

### Rust Not Found

**Symptom:** `cargo: command not found`

**Solution:** Install Rust and add to PATH
```bash
# Install
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Add to PATH
source $HOME/.cargo/env
```

### Missing System Dependencies (Linux)

**Symptom:** Build fails with missing library errors

**Solution:** Install all required system packages
```bash
# Ubuntu/Debian
sudo apt install libwebkit2gtk-4.1-dev build-essential

# Fedora/RHEL
sudo dnf install webkit2gtk4.1-devel gcc
```

### Permission Denied (macOS/Linux)

**Symptom:** Cannot execute shell scripts

**Solution:** Make scripts executable
```bash
chmod +x quick-dev.sh quick-build.sh
```

### WebView2 Missing (Windows)

**Symptom:** Application fails to start on Windows 10

**Solution:** Install WebView2 Runtime
- Download from: https://developer.microsoft.com/microsoft-edge/webview2/

---

## Next Steps

After completing setup:

1. **Read the build instructions:** [BUILD_INSTRUCTIONS_CROSS_PLATFORM.md](BUILD_INSTRUCTIONS_CROSS_PLATFORM.md)
2. **Check the quick reference:** [QUICK_REFERENCE.md](QUICK_REFERENCE.md)
3. **Start developing:** Run `quick-dev.bat` or `./quick-dev.sh`

---

## Support Resources

- [Tauri Prerequisites](https://tauri.app/v1/guides/getting-started/prerequisites)
- [Node.js Downloads](https://nodejs.org/)
- [Rust Installation](https://rustup.rs/)
- [Visual Studio Downloads](https://visualstudio.microsoft.com/downloads/)

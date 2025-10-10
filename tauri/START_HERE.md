# Start Here - Bibliomancy Setup Guide

Welcome to the Bibliomancy project! This guide will help you get started quickly.

## What is Bibliomancy?

Bibliomancy is a desktop application that provides random Bible verses for spiritual guidance and divination. Built with Tauri 2.0, it offers a beautiful parchment-styled interface displaying verses from the complete King James Bible.

## Quick Start (3 Steps)

### 1. Install Dependencies

Open a terminal in the project directory and run:
```bash
npm install
```

### 2. Run in Development Mode

**Option A - Command Line**:
```bash
npm run dev
```

**Option B - Quick Script (Windows)**:
Double-click `quick-dev.bat`

### 3. Build for Production (Optional)

**Option A - Command Line**:
```bash
npm run build
```

**Option B - Quick Script (Windows)**:
Double-click `quick-build.bat`

## What You'll See

When you run the application:
1. A window opens with a parchment scroll background
2. A random Bible verse is displayed with fire text effects
3. Click "RELOAD" to get a new random verse
4. Click "?" for help on using bibliomancy

## Project Structure

```
bibliomancy/
├── src/                    # Frontend files (HTML, JS, images)
├── src-tauri/             # Tauri backend (Rust)
├── package.json           # Node.js configuration
├── quick-dev.bat          # Quick development script
└── quick-build.bat        # Quick build script
```

## Key Files

- **src/index.html** - Main application interface
- **src/bibliomancy.js** - Contains all 31,102 Bible verses
- **src-tauri/tauri.conf.json** - Application configuration
- **src-tauri/src/lib.rs** - Rust backend code

## Common Tasks

### Development
```bash
npm run dev          # Start development server
```

### Building
```bash
npm run build        # Build for current platform
npm run build:windows # Build Windows installer
```

### Cleaning
```bash
cd src-tauri
cargo clean          # Clean Rust build cache
```

## Prerequisites

Make sure you have installed:
- ✅ Node.js (v16+)
- ✅ Rust (latest stable)
- ✅ npm or yarn

Check versions:
```bash
node --version
rustc --version
npm --version
```

## Need Help?

1. **Setup Issues**: See [SETUP.md](SETUP.md)
2. **Build Problems**: See [BUILD_INSTRUCTIONS.md](BUILD_INSTRUCTIONS.md)
3. **Project Overview**: See [PROJECT_SUMMARY.md](PROJECT_SUMMARY.md)
4. **Development Checklist**: See [CHECKLIST.md](CHECKLIST.md)

## Features

✨ **Complete KJV Bible** - All 31,102 verses
🎨 **Beautiful Interface** - Parchment scroll with fire effects
🔄 **Random Selection** - New verse with each reload
🔗 **External Links** - Direct links to Bible Gateway and BibleHub
📖 **Help System** - Built-in guidance on bibliomancy
⚡ **Fast & Lightweight** - Native desktop performance

## Next Steps

1. ✅ Run `npm install`
2. ✅ Run `npm run dev` or `quick-dev.bat`
3. ✅ Explore the application
4. ✅ Read [BUILD_INSTRUCTIONS.md](BUILD_INSTRUCTIONS.md) for building
5. ✅ Check [CHECKLIST.md](CHECKLIST.md) for development tasks

## Troubleshooting

**Application won't start?**
- Ensure all dependencies are installed: `npm install`
- Check that Rust is installed: `rustc --version`
- Try cleaning and rebuilding: `cd src-tauri && cargo clean && cd .. && npm run dev`

**Build fails?**
- Update Rust: `rustup update`
- Clear npm cache: `npm cache clean --force`
- Reinstall dependencies: `rm -rf node_modules && npm install`

**Verses not displaying?**
- Check that `bibliomancy.js` is in the `src/` folder
- Verify all image files are present in `src/`
- Check browser console for errors (F12 in dev mode)

## Support

For issues or questions:
1. Check the documentation files
2. Review the [BUILD_STATUS.md](BUILD_STATUS.md)
3. Consult Tauri documentation: https://tauri.app/

---

**Ready to begin?** Run `npm install` and then `npm run dev`!

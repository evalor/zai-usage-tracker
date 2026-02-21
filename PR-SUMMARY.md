# PR Title

```
v1.0.5: Auto-detect plan tier, add screenshots and API documentation
```

# PR Description (for GitHub)

## 📋 Summary

This PR introduces automatic plan tier detection and comprehensive documentation improvements. Users no longer need to manually configure their account level, and developers have complete API documentation for integration and debugging.

## ✨ What's New

### Auto-detect Plan Tier
- **Removed manual configuration** - Extension automatically detects account level (Lite/Pro/Max) from API
- Plan level shown in tooltip for reference
- Simplifies setup and eliminates configuration errors

### Enhanced Documentation
- **Screenshots added** - Visual preview of extension UI in README
- **API Documentation** - Complete reference in `docs/API-DOCUMENTATION.md`
  - All 3 monitor endpoints documented with examples
  - Request/response formats and authentication details
- **Debug Configuration** - Added `.vscode/launch.json` and `.vscode/tasks.json` for easier development

### Bug Fixes
- Fixed status bar display with proper VS Code Codicons
- Improved tooltip rendering with Markdown support
- Better quota window detection and display logic

## 🧪 Testing

Tested with:
- ✅ Multiple account types (free/pro)
- ✅ Different quota scenarios
- ✅ API errors and edge cases
- ✅ VS Code, Cursor, Windsurf

## 📸 Screenshot

![Extension Screenshot](./screenshot.jpg)

## 🔄 Migration

**No action required for users** - Existing installations automatically benefit from auto-detection.

## 📝 Files Changed

- Updated: `src/api/zaiService.ts`, `src/statusBar/usageIndicator.ts`
- Added: `docs/API-DOCUMENTATION.md`, `screenshot.jpg`, `.vscode/*`
- Updated: `readme.md`, `changelog.md`

---

**Version**: 1.0.5 | **Changelog**: [changelog.md](./changelog.md) | **API Docs**: [docs/API-DOCUMENTATION.md](./docs/API-DOCUMENTATION.md)

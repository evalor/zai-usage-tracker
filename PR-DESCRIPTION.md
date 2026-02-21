# v1.0.5: Auto-detect Plan Tier and Enhanced Documentation

## Summary

This PR introduces automatic plan tier detection and comprehensive documentation improvements to the Z.ai GLM Usage Tracker extension. The changes eliminate the need for manual plan configuration and provide better API documentation for developers and users.

## Key Changes

### 🎯 Major Features

#### 1. **Automatic Plan Tier Detection**
- **Removed manual plan tier configuration** - No longer requires users to manually specify their account level (Lite/Pro/Max)
- **Auto-detection from API response** - Extension now automatically detects account level from the `/api/monitor/usage/quota/limit` endpoint
- Plan level is displayed in the tooltip for user reference
- Simplifies initial setup and eliminates configuration errors

#### 2. **Improved API Response Parsing**
- Enhanced quota window detection and display logic
- Better handling of multiple quota windows (5-hour, 1-week, 1-month)
- Improved status bar display with dynamic token quota selection
- Fixed tooltip rendering issues with proper Markdown formatting

### 📚 Documentation Enhancements

#### 3. **Added Screenshots Section**
- Added visual preview screenshot (`screenshot.jpg`) to README
- Helps users understand the extension UI before installation
- Shows real-world usage examples in the status bar and tooltip

#### 4. **Comprehensive API Documentation**
- Added new `docs/API-DOCUMENTATION.md` file with complete API reference
- Documents all three Z.ai monitor endpoints:
  - `/api/monitor/usage/quota/limit` - Quota limits and usage percentages
  - `/api/monitor/usage/model-usage` - Model usage statistics (prompts + tokens)
  - `/api/monitor/usage/tool-usage` - MCP tool usage statistics
- Includes request/response examples with actual JSON payloads
- Documents authentication, headers, and query parameters
- Useful for developers building integrations or debugging

#### 5. **Debug Configuration**
- Added `.vscode/launch.json` for easier debugging in development
- Added `.vscode/tasks.json` for build automation
- Improves developer experience when contributing to the project

### 🐛 Bug Fixes

#### 6. **Status Bar Display Improvements**
- Fixed status bar text formatting with proper VS Code Codicons
- Fixed tooltip rendering with proper Markdown support
- Improved percentage calculation for token quotas
- Better handling of edge cases (no quota data, API errors)

## Technical Details

### API Integration Changes
- Plan level is now extracted from `data.level` field in quota limit response
- No breaking changes to existing API endpoints
- Backward compatible with existing user configurations

### Code Quality Improvements
- Enhanced TypeScript interfaces for better type safety
- Improved error handling in API service
- Better separation of concerns between components

## Testing

The changes have been tested with:
- ✅ Multiple account types (free/pro accounts)
- ✅ Different quota scenarios (low usage, high usage, quota reset)
- ✅ API error conditions and edge cases
- ✅ VS Code, Cursor, and Windsurf compatibility
- ✅ Fresh installations and upgrades from v1.0.4

## Screenshots

![Extension Screenshot](./screenshot.jpg)

The screenshot shows:
- Status bar display with token quota percentage
- Tooltip with detailed quota windows and usage statistics
- Auto-detected plan level
- MCP tool usage quotas

## Migration Notes

### For Users
- **No action required** - Existing users will automatically benefit from plan tier auto-detection
- Previously configured plan tier settings (if any) are no longer used
- The extension will automatically detect and display the correct plan level

### For Developers
- New API documentation in `docs/API-DOCUMENTATION.md` provides complete reference
- Debug configuration added for easier local development
- No breaking changes to extension APIs or commands

## Benefits

1. **Simplified Setup**: Users no longer need to know or configure their plan tier
2. **Improved Accuracy**: Plan level is always correct and up-to-date from API
3. **Better Documentation**: Developers can understand and extend the API integration
4. **Enhanced UX**: Screenshots and visual guides help users understand the extension
5. **Easier Debugging**: Debug configuration and API docs make troubleshooting easier

## Checklist

- [x] Code follows the existing style and conventions
- [x] Documentation updated (README, changelog, API docs)
- [x] Screenshots added for visual reference
- [x] Tested with multiple account types and scenarios
- [x] No breaking changes to existing functionality
- [x] Debug tools added for development workflow

## Related Issues

This PR addresses user feedback about:
- Confusion around plan tier configuration
- Need for API documentation
- Requests for visual previews before installation

## Future Enhancements

Potential follow-up improvements (not included in this PR):
- Add more detailed usage charts/graphs
- Support for additional MCP tool types
- Configurable status bar format options
- Export usage data to CSV/JSON

---

**Version**: 1.0.5  
**Changelog**: See [changelog.md](./changelog.md) for complete version history  
**API Docs**: See [docs/API-DOCUMENTATION.md](./docs/API-DOCUMENTATION.md) for API reference

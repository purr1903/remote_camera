# Changelog

All notable changes to the Remote Camera project will be documented in this file.

## [2.0.0] - 2026-07-24

### Added - Enhanced Edition Features

#### Video Recording
- Full video recording capability with MediaRecorder API
- Support for multiple codecs (VP9, VP8, WebM)
- Configurable video quality (High/Medium/Low)
- Automatic file download with timestamp
- Recording status indicator with visual feedback
- Recording duration and file size tracking

#### Snapshot Capture
- High-quality screenshot capture from video stream
- Optional timestamp overlay on snapshots
- Automatic PNG format download
- Configurable timestamp display

#### Real-time Statistics
- FPS (Frames Per Second) monitoring
- Bandwidth usage tracking (Mbps)
- Video resolution detection
- Codec information display
- Statistics updated every second
- WebRTC stats collection using `getStats()` API

#### Audio Support
- Microphone audio capture option
- Audio/video synchronization
- Audio track replacement during camera switching
- Audio indicator in UI
- Configurable audio settings on target device

#### Encryption & Security
- Optional end-to-end encryption
- XOR-based encryption for data transmission
- Encryption key generation and exchange
- Encryption status indicator
- Enhanced security badge in UI

#### UI/UX Improvements
- Sidebar statistics panel
- Enhanced control panel layout
- Better responsive design
- Improved modal dialogs
- Recording settings configuration
- Stream information display
- Visual indicators for active features

#### Settings & Configuration
- Recording quality selector
- Audio enable/disable toggle
- Encryption enable/disable toggle
- Stream quality options (High/Medium/Low)
- Settings persistence

### Changed

- Reorganized file structure with enhanced versions
- Improved button layout and styling
- Enhanced notification system
- Better status indicators with animations
- More detailed information display
- Improved error handling and messages

### Technical Improvements

- Better state management
- Improved event handling
- Enhanced error catching
- Better resource cleanup
- Optimized performance monitoring
- Cleaner code organization with comments

### Files Added

- `viewer-enhanced.html` - Enhanced viewer with all new features
- `target-enhanced.html` - Enhanced target with audio and encryption
- `README.md` - Comprehensive documentation
- `CHANGELOG.md` - This file

### Browser Compatibility

- Chrome/Chromium 90+
- Firefox 88+
- Safari 14+
- Edge 90+
- Opera 76+

### Known Issues

- Encryption uses simple XOR cipher (not cryptographically secure)
- Some browsers may not support VP9 codec (fallback to VP8)
- Recording may not work on some mobile browsers
- Audio support varies by browser

### Performance Notes

- Recording uses VP9 codec at 2.5 Mbps bitrate
- Statistics collection has minimal performance impact
- Encryption adds negligible overhead
- Recommended bandwidth: 2-4 Mbps for Medium quality

## [1.0.0] - 2026-07-01

### Initial Release - Original Edition

#### Core Features
- Real-time video streaming via WebRTC
- Peer-to-peer connection using PeerJS
- Front and back camera switching
- Connection status monitoring
- Stream duration tracking
- Responsive design for desktop and mobile

#### Files
- `index.html` - Redirect page
- `viewer.html` - Viewer interface
- `target.html` - Target interface

#### Browser Support
- Chrome/Chromium 50+
- Firefox 55+
- Safari 11+
- Edge 15+

#### Features
- Generate unique viewer ID
- Display connection link
- Real-time video display
- Camera switching capability
- Connection status indicator
- Stream duration timer
- Notification system
- Responsive layout

#### Limitations
- No recording capability
- No audio support
- No statistics monitoring
- No encryption
- No snapshot feature

---

## Upgrade Guide

### From v1.0.0 to v2.0.0

#### For Users
1. Use `viewer-enhanced.html` instead of `viewer.html`
2. Use `target-enhanced.html` instead of `target.html`
3. Configure new settings on target device
4. Enjoy new recording and snapshot features

#### For Developers
1. Review new file structure
2. Update links to enhanced versions
3. Implement new API endpoints if needed
4. Update UI to include new controls

#### Breaking Changes
- None - original files still work
- New features are additive

#### Migration Path
- Keep original files for backward compatibility
- Gradually migrate to enhanced versions
- Test new features before production deployment

---

## Planned Features (Roadmap)

### v2.1.0 (Next Release)
- [ ] Improved encryption (AES-256)
- [ ] Server-side recording option
- [ ] Advanced codec support (H.265)
- [ ] Better statistics dashboard
- [ ] Connection history tracking

### v2.2.0
- [ ] Screen sharing capability
- [ ] Group streaming support
- [ ] Cloud storage integration
- [ ] Advanced analytics
- [ ] Custom branding options

### v3.0.0
- [ ] Mobile app version
- [ ] Desktop application
- [ ] Server backend
- [ ] User authentication
- [ ] Recording management system

---

## Contributing

We welcome contributions! Please see our contributing guidelines for more information.

### Development Setup
```bash
git clone https://github.com/purr1903/remote_camera.git
cd remote_camera
# No build process required - pure HTML/CSS/JS
```

### Testing
- Test on multiple browsers
- Test on mobile devices
- Test with different network conditions
- Test all recording formats
- Test encryption functionality

### Reporting Bugs
- Include browser and OS information
- Describe steps to reproduce
- Include error messages from console
- Provide screenshots if applicable

---

## Support & Feedback

- GitHub Issues: Report bugs and request features
- GitHub Discussions: General questions and discussions
- Email: support@remotecamera.dev

---

## License

This project is licensed under the MIT License - see LICENSE file for details.

---

## Credits

- **PeerJS**: WebRTC abstraction library
- **Contributors**: All community members who provided feedback and improvements

---

## Release Notes

### v2.0.0 Release Highlights

🎉 **Major Update** - Remote Camera Enhanced Edition

**What's New:**
- 📹 Video Recording with multiple quality options
- 📷 Snapshot capture with timestamp overlay
- 📊 Real-time statistics and monitoring
- 🎤 Microphone audio support
- 🔒 Optional encryption for secure streaming
- 🎨 Improved UI with sidebar statistics
- ⚙️ Advanced settings and configuration

**Performance:**
- Optimized for bandwidth efficiency
- Reduced latency with better codec selection
- Improved battery life on mobile devices

**Stability:**
- Better error handling
- Improved connection management
- Enhanced resource cleanup

**Security:**
- Optional encryption support
- Secure peer-to-peer communication
- No server-side recording

---

**Last Updated**: July 24, 2026

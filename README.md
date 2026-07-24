# Remote Camera - Enhanced Edition

A powerful peer-to-peer remote camera streaming application with advanced features including video recording, snapshots, real-time statistics, encryption, and audio support.

## Features

### Core Features
- **Real-time Video Streaming**: Stream camera feed using WebRTC peer-to-peer connection
- **Dual Camera Support**: Switch between front and back cameras
- **Live Statistics**: Monitor FPS, bandwidth, resolution, and codec information
- **Responsive Design**: Works on desktop and mobile devices

### Advanced Features (Enhanced Edition)
- **Video Recording**: Record streaming video in WebM format with configurable quality
- **Snapshot Capture**: Take screenshots from the video stream with optional timestamp
- **Audio Support**: Include microphone audio in the stream
- **Encryption**: Optional end-to-end encryption for data transmission
- **Cloud Storage**: Local IndexedDB storage for recordings and metadata
- **Quality Control**: Choose between High (1080p), Medium (720p), and Low (480p)
- **Connection Monitoring**: Real-time connection status and statistics

## Architecture

### Technology Stack
- **WebRTC**: Peer-to-peer communication using PeerJS
- **MediaRecorder API**: Video recording functionality
- **Canvas API**: Screenshot capture
- **IndexedDB**: Local data storage
- **WebCrypto**: Encryption support

### File Structure
```
remote_camera/
├── index.html              # Redirect to viewer
├── viewer.html             # Original viewer interface
├── target.html             # Original target interface
├── viewer-enhanced.html    # Enhanced viewer with recording & stats
├── target-enhanced.html    # Enhanced target with audio & encryption
├── README.md              # This file
└── CHANGELOG.md           # Version history
```

## Usage

### Quick Start

1. **Viewer Side** (the one watching):
   - Open `viewer-enhanced.html` in a web browser
   - Click "START STREAM" button
   - Copy the generated link and send it to the target device

2. **Target Side** (the one sharing camera):
   - Open the link received from the viewer
   - Configure stream settings (audio, encryption, quality)
   - Click "ALLOW FOREVER" to grant camera access
   - Your camera feed will be streamed to the viewer

### Viewer Controls

| Button | Function |
|--------|----------|
| **START** | Initiate streaming connection |
| **STOP** | Stop the stream |
| **SWITCH** | Toggle between front/back camera |
| **RECORD** | Start/stop video recording |
| **SNAPSHOT** | Capture screenshot from stream |
| **COPY LINK** | Copy target link to clipboard |

### Target Settings

- **Include Microphone Audio**: Enable audio transmission from target device
- **Enable Encryption**: Encrypt data transmission (recommended)
- **Quality**: Select streaming quality (High/Medium/Low)

## Advanced Features

### Video Recording

The enhanced viewer can record the incoming video stream:

1. Click **RECORD** button to start recording
2. Recording indicator (🔴 REC) appears in top-right corner
3. Click **RECORD** again to stop
4. Video automatically downloads as `remote-camera-[timestamp].webm`

**Supported Formats**: WebM with VP9/VP8 codec

### Snapshot Capture

Capture high-quality screenshots from the video stream:

1. Click **SNAPSHOT** button
2. Image downloads as `snapshot-[timestamp].png`
3. Optional timestamp overlay can be added

### Real-time Statistics

Monitor streaming quality in real-time:

- **FPS**: Frames per second
- **Bandwidth**: Current bandwidth usage in Mbps
- **Resolution**: Video resolution (width x height)
- **Codec**: Video codec information

### Encryption

Optional end-to-end encryption for enhanced security:

1. Target enables encryption during setup
2. Encryption key is exchanged during connection
3. All data transmission is encrypted using XOR cipher
4. Viewer receives encrypted data and decrypts automatically

### Audio Support

Include microphone audio in the stream:

1. Target enables "Include Microphone Audio" in settings
2. Audio is captured along with video
3. Both audio and video are synchronized in the stream

## Security Considerations

### Current Implementation
- **Peer-to-Peer**: Direct connection between devices, no server intermediary
- **Optional Encryption**: XOR-based encryption for data
- **HTTPS**: Secure connection to PeerJS server
- **No Recording on Server**: All data stays on client devices

### Best Practices
1. Only share links with trusted recipients
2. Enable encryption for sensitive streams
3. Close the stream when not in use
4. Monitor active connections in the statistics panel
5. Keep browser and OS updated

## Browser Compatibility

| Browser | Desktop | Mobile |
|---------|---------|--------|
| Chrome | ✅ | ✅ |
| Firefox | ✅ | ✅ |
| Safari | ✅ | ✅ |
| Edge | ✅ | ✅ |
| Opera | ✅ | ✅ |

**Requirements**:
- WebRTC support
- getUserMedia API support
- MediaRecorder API (for recording)
- Canvas API (for snapshots)

## Troubleshooting

### Camera Not Working
- Check browser permissions for camera access
- Ensure camera is not in use by another application
- Try refreshing the page
- Check browser console for errors

### No Audio
- Verify microphone is enabled in settings
- Check browser microphone permissions
- Ensure target device has microphone access

### Connection Issues
- Check internet connection
- Verify both devices are on stable network
- Try disabling VPN/proxy
- Check firewall settings
- PeerJS server might be temporarily unavailable

### Recording Not Working
- Ensure browser supports MediaRecorder API
- Check available disk space
- Verify video stream is active before recording
- Try different quality settings

### Performance Issues
- Reduce video quality setting
- Close other applications
- Check network bandwidth
- Reduce FPS by adjusting quality

## API Reference

### Viewer-side JavaScript API

```javascript
// Start streaming
startStream()

// Stop streaming
stopStream()

// Switch camera
switchCamera()

// Start recording
startRecording()

// Stop recording
stopRecording()

// Take snapshot
takeSnapshot()

// Copy link to clipboard
copyLinkToClipboard()
```

### Statistics Monitoring

```javascript
// Access real-time statistics
statFps.textContent          // Current FPS
statBandwidth.textContent    // Bandwidth in Mbps
statResolution.textContent   // Video resolution
statCodec.textContent        // Codec information
```

## Performance Metrics

### Recommended Settings
- **Video Quality**: Medium (720p) for balanced quality/bandwidth
- **Audio**: Enabled for better communication
- **Encryption**: Enabled for security
- **Recording**: Use Medium quality to reduce file size

### Bandwidth Requirements
- **Low Quality (480p)**: ~1-2 Mbps
- **Medium Quality (720p)**: ~2-4 Mbps
- **High Quality (1080p)**: ~4-8 Mbps

## Data Storage

### IndexedDB Storage
- Recordings metadata
- Connection history
- User preferences
- Statistics snapshots

### Local Downloads
- Video files (WebM format)
- Screenshot images (PNG format)

## Known Limitations

1. **No Server Recording**: Streaming is not recorded on server
2. **P2P Only**: Requires direct connection between peers
3. **NAT Traversal**: May have issues behind some firewalls
4. **Browser Dependent**: Features vary by browser support
5. **Encryption**: Simple XOR cipher (not cryptographically secure)

## Future Enhancements

- [ ] WebRTC data channel encryption
- [ ] Server-side recording option
- [ ] Group streaming support
- [ ] Screen sharing capability
- [ ] Advanced codec support (H.265, AV1)
- [ ] Mobile app version
- [ ] Cloud storage integration
- [ ] Advanced analytics dashboard

## License

This project is open source and available under the MIT License.

## Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.

## Support

For issues, questions, or suggestions, please open an issue on GitHub or contact the development team.

## Version History

### v2.0.0 - Enhanced Edition (Current)
- Added video recording functionality
- Added snapshot capture
- Added real-time statistics monitoring
- Added audio support
- Added encryption support
- Improved UI/UX with sidebar statistics
- Better error handling and notifications

### v1.0.0 - Original Edition
- Basic video streaming
- Camera switching
- Connection management
- Simple status indicators

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for detailed version history.

---

**Last Updated**: July 2026
**Developed by**: Remote Camera Team

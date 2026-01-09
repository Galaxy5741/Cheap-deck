# Cheap Deck

A cost-effective alternative to expensive Stream Deck hardware, combining **deej** for volume mixing with **Macro Deck** for customizable macro buttons. Why pay premium prices when you can build your own with superior flexibility?

## Overview

Cheap Deck provides professional streaming and productivity control without the Stream Deck price tag. This project integrates:

- **deej**: Arduino-based volume mixer with physical sliders for per-application audio control
- **Macro Deck**: Software-based macro pad for hotkeys, shortcuts, and automation triggers (Windows)
- **Stream Pi**: Alternative macro solution for Linux users

Together, these create a comprehensive control surface that rivals commercial solutions at a fraction of the cost.

## Features

### Volume Control (deej)
- Individual application volume control via physical sliders
- Real-time audio mixing without touching software interfaces
- Arduino-based hardware - fully customizable
- Open-source and community-supported

### Macro Controls (Macro Deck / Stream Pi)
- Customizable button layouts for hotkeys and shortcuts
- Multi-action macros and automation sequences
- Visual feedback and custom icons
- Plugin ecosystem for extended functionality
- Cross-application integration
- **Stream Pi**: Linux-compatible alternative with web-based interface

## Hardware Requirements

### For deej Volume Mixer
- Arduino board (Uno, Leonardo, or Nano recommended)
- Linear potentiometers/sliders (quantity depends on desired channels)
- USB cable for Arduino connection
- **Enclosure**: 3D printed holder (highly recommended for clean desktop integration)
  - Design tools: [Shapr3D](https://www.shapr3d.com/), [Tinkercad](https://www.tinkercad.com/) (free, browser-based)
  - No printer? Use [JLC3DP](https://jlc3dp.com) for affordable 3D printing service
- Wiring and basic soldering equipment

### For Macro Deck / Stream Pi
- Windows PC or Linux machine (your primary workstation)
- **Optional**: Dedicated device for control interface
  - Old Android tablet or phone (touchscreen interface)
  - Raspberry Pi with touchscreen
  - Secondary laptop or desktop
  - Any device with web browser (for Stream Pi)
- Network connection (if using dedicated control device)

## Software Requirements

- [deej](https://github.com/omriharel/deej) - Volume mixer software
- **Windows Users**: [Macro Deck](https://macrodeck.org/) - Macro control software
- **Linux Users**: [Stream Pi](https://stream-pi.com/) - Open-source macro control alternative
- Arduino IDE (for deej firmware)
- Windows 10/11 (for Macro Deck) or Linux (for Stream Pi)

## Installation

### deej Setup

1. **Hardware Assembly**
   - Connect potentiometers to Arduino analog pins
   - Wire according to deej schematic
   - Upload deej Arduino sketch via Arduino IDE

2. **Software Configuration**
   ```bash
   # Download deej from releases
   # Extract to preferred location
   # Edit config.yaml to map sliders to applications
   ```

3. **Configuration Example**
   ```yaml
   slider_mapping:
     0: master
     1: chrome.exe
     2: spotify.exe
     3: discord.exe
     4: obs64.exe
   ```

### Macro Deck Setup

1. **Installation**
   - Download Macro Deck from official website
   - Install on control device
   - Launch and complete initial setup

2. **Configuration**
   - Create button layouts for different workflows
   - Configure hotkey assignments
   - Set up multi-action macros
   - Customize icons and visual appearance

3. **Integration**
   - Enable remote control if using secondary device
   - Configure network settings for device connectivity
   - Test macro functionality across applications

### Stream Pi Setup (Linux Alternative)

1. **Installation**
   ```bash
   # Download Stream Pi from releases
   wget https://github.com/stream-pi/server/releases/latest
   
   # Extract and run
   chmod +x stream-pi-server-*.run
   ./stream-pi-server-*.run
   ```

2. **Configuration**
   - Access web interface (typically http://localhost:8080)
   - Create profiles for different use cases
   - Configure actions and plugins
   - Set up custom icons and layouts

3. **Client Options**
   - Use web browser as control interface (any device)
   - Install Stream Pi Client on dedicated device
   - Configure network access for remote control
   - Works on Raspberry Pi for dedicated hardware solution

## Usage

### Volume Mixing
Physical sliders provide instant access to application volumes:
- Adjust individual app volumes without Alt+Tab
- Master volume control for quick adjustments
- Visual feedback via deej system tray

### Macro Execution
Trigger complex actions with single button press:
- Scene switching in OBS
- Application launching
- Keyboard shortcuts and hotkey sequences
- Custom scripts and automation

## Customization

### 3D Printed Enclosures

**Designing Your Enclosure:**
- **Shapr3D**: Professional CAD for precise mechanical design (free for hobbyists and start 3D modeling in like 5-10 minutes)
- **Tinkercad**: Beginner-friendly browser-based 3D modeling (completely free)
- Design around your specific slider configuration and Arduino board
- Include cable management and mounting considerations
- There is also an example file called Phone+holder.stp

**Manufacturing Options:**
1. **Own 3D Printer**: Print at home if you have access
2. **JLC3DP**: Professional 3D printing service
   - Upload STL files directly to [jlc3dp.com](https://jlc3dp.com)
   - Multiple material options (PLA, PETG, Resin)
   - Affordable pricing with fast turnaround
   - International shipping available

**Design Tips:**
- Leave tolerance for slider movement (0.5-1mm clearance)
- Include mounting holes for desk placement
- Add cutouts for USB cable routing
- Consider ventilation if Arduino generates heat
- Design modular sections for easier printing

### deej Extensions
- Modify Arduino code for additional features
- Add LED indicators for visual feedback
- Implement button controls alongside sliders
- Custom enclosure designs for desktop integration

### Macro Deck Plugins
- Explore community plugins for extended functionality
- Create custom actions via plugin development
- Integrate with third-party services and APIs
- Build workflow-specific layouts

## Cost Comparison

| Component | Cheap Deck | Stream Deck |
|-----------|------------|-------------|
| Base Hardware | ~€20-40 (Arduino + components) | €149+ |
| Enclosure | €5-15 (3D printed via JLC3DP) or free (own printer) | Included |
| Volume Control | Included (deej) | Requires separate hardware |
| Customization | Fully open-source | Limited to Elgato ecosystem |
| **Total Investment** | **~€25-55** | **€149+** |

*Even with professional 3D printing service, you're saving €100+ compared to Stream Deck*

## Advantages Over Stream Deck

1. **Cost**: Significantly cheaper initial investment
2. **Flexibility**: Separate volume and macro controls
3. **Open Source**: Complete customization freedom
4. **Platform Support**: Works on Windows (Macro Deck) and Linux (Stream Pi)
5. **Expandability**: Add features without vendor limitations
6. **Learning**: Hands-on hardware and software integration experience

## Troubleshooting

### deej Issues
- **Arduino not detected**: Check USB cable and drivers
- **Slider not responding**: Verify pin mapping in config
- **Application not listed**: Ensure exact .exe name in config

### Macro Deck Issues
- **Buttons not triggering**: Check hotkey conflicts
- **Remote connection failed**: Verify network settings and firewall
- **Plugin errors**: Update to latest Macro Deck version

### Stream Pi Issues
- **Web interface not loading**: Check port 8080 availability and firewall rules
- **Actions not executing**: Verify user permissions for system commands
- **Client connection failed**: Ensure server and client are on same network
- **Plugin compatibility**: Check Stream Pi version matches plugin requirements

## Future Enhancements

- [ ] Integration between deej and Macro Deck for unified control
- [ ] Custom PCB design for cleaner deej builds
- [x] 3D-printed enclosures for professional desktop appearance
- [ ] Community enclosure design repository
- [ ] Advanced lighting effects with addressable LEDs
- [ ] Profile switching automation based on active application

## Resources

- [deej GitHub Repository](https://github.com/omriharel/deej)
- [Macro Deck Official Site](https://macrodeck.org/)
- [Stream Pi Official Site](https://stream-pi.com/)
- [Stream Pi GitHub](https://github.com/stream-pi)
- [Arduino Documentation](https://www.arduino.cc/reference/en/)
- [Shapr3D](https://www.shapr3d.com/) - Professional 3D CAD software
- [Tinkercad](https://www.tinkercad.com/) - Free browser-based 3D modeling
- [JLC3DP](https://jlc3dp.com) - Affordable 3D printing service

## Contributing

Improvements, modifications, and creative implementations welcome. This project thrives on community innovation and cost-conscious engineering.

## License

This project documentation is released under MIT License. Individual components (deej, Macro Deck) retain their respective licenses.

---

**Built by someone who refuses to pay Stream Deck prices for what can be accomplished with £30 worth of components and some creativity.**

# Family Wallboard

A modern, dark-themed family organization dashboard designed for wall-mounted displays. It provides real-time task management, calendar events, photo slideshows, and weather information for busy families.

## Features

### Wallboard Display
- Full-screen display optimized for wall-mounted tablets/TVs
- **Device-specific URLs** with unique access tokens (no login required)
- **Card-based system** with configurable display cards
- Round-robin rotation between cards with smooth fade transitions
- Real-time clock and weather display
- Dark theme optimized for always-on displays

### Device Management
- Create multiple devices (e.g., "Kitchen TV", "Office Tablet")
- Each device gets a unique secure URL
- Configure screen resolution per device
- Touch-enabled devices can mark tasks as completed
- Track device last-seen timestamps
- Enable/disable devices without deleting

### Card System
- **Tasks Card**: Display family tasks with priorities and assignments
- **Events Card**: Show upcoming calendar events
- **Photos Card**: Slideshow with photo albums
- **Weather Card**: Current conditions and forecast
- Configurable display duration per card
- Drag-and-drop card reordering
- Card-specific settings (colors, filters, etc.)

### Card Templates
- Create reusable card configurations
- Apply templates to multiple devices
- Customize settings per template

### Task Management
- Create, edit, and complete tasks
- Priority levels (High, Medium, Low) with color coding
- Due dates with overdue detection
- Multi-line descriptions
- Family member assignment with color-coded avatars
- Real-time synchronization across devices

### Calendar Events
- Manual event creation and editing
- All-day event support
- Location and description fields
- Time-based grouping (Today, Tomorrow, This Week)

### Photo Albums & Display
- Organize photos into albums
- **Multi-album assignment**: Photos can belong to multiple albums
- **Focus position**: Set focal point for cropping on different displays
- Display order management with drag-and-drop
- Caption support
- Active/inactive toggle per photo
- Smooth crossfade transitions between photos

### Weather Integration
- Current temperature and conditions
- Weather icons for different conditions
- Location autocomplete search
- Celsius/Fahrenheit support
- Powered by Open-Meteo (free, no API key required)

### Settings & Administration
- User management with admin roles
- Family member management with invitations
- Configurable display options per device
- Time zone and date/time format preferences

## Getting Started

### Prerequisites
- Ubuntu 22.04 (other Debian-based distributions may work but are untested)

### Installation

1. **Download** the latest release:
   ```bash
   wget -O familywallboard.tar.gz https://github.com/FarlonCom/FamilyWallboard/releases/latest/download/familywallboard-linux-x64.tar.gz
   ```

2. **Extract** the install script:
   ```bash
   tar -xzf familywallboard.tar.gz --strip-components=1 familywallboard/scripts/
   ```

3. **Run** the installer:
   ```bash
   sudo bash scripts/install-ubuntu.sh --package familywallboard.tar.gz
   ```
   Options:
   - `--port PORT` — Change application port (default: 5000)
   - `--with-nginx` — Install and configure Nginx as reverse proxy
   - `--clean` — Remove existing app and all data before installing

4. **Open** your browser and go to `http://<your-ip>:5000`

The default port is 5000 and can be changed in the configuration.

### Updating

To update to a newer version, download the latest release and run:
```bash
wget -O familywallboard.tar.gz https://github.com/FarlonCom/FamilyWallboard/releases/latest/download/familywallboard-linux-x64.tar.gz
sudo bash /opt/familywallboard/scripts/update-ubuntu.sh familywallboard.tar.gz
```

### Uninstalling

To remove Family Wallboard:
```bash
sudo bash /opt/familywallboard/scripts/uninstall-ubuntu.sh
```

Options:
- `--remove-data` — Also remove all data (database, uploads, backups)
- `--remove-nginx` — Also remove the Nginx site configuration

### First-Time Setup
1. Navigate to `http://<your-ip>:5000/register`
2. Create your account (first user becomes admin)
3. Go to **Admin > Devices** to create your first device
4. Copy the device URL and open it on your wall-mounted display
5. Add cards to the device and configure their settings

## Usage

### Main Application
1. **Register/Login** using email and password
2. **Dashboard** shows summary of tasks, events, and photos
3. **Tasks page** for full task management
4. **Events page** for calendar event management
5. **Photos page** for photo uploads, albums, and management

### Device Setup
1. Go to **Admin > Devices**
2. Click **Add Device** and configure:
   - Device name (e.g., "Living Room TV")
   - Screen resolution
   - Touch capability
3. Add cards to the device (Tasks, Events, Photos, Weather)
4. Configure each card's settings
5. Copy the device URL and open on your display

### Wallboard Display
Each device has a unique URL:
- No login required — the URL token provides access
- Cards rotate automatically based on configured duration
- Displays current time and weather
- Touch devices can interact with tasks

### Kiosk Mode (Recommended for wall displays)
```bash
# Chrome
chrome --kiosk http://YOUR_SERVER:5000/wallboard/YOUR_DEVICE_TOKEN

# Edge
msedge --kiosk http://YOUR_SERVER:5000/wallboard/YOUR_DEVICE_TOKEN
```

## Configuration

### Device Settings
Each device can be configured with:
- Screen resolution (width × height)
- Touch capability
- Active/inactive status
- Card selection and order
- Per-card settings

### Card Settings
Each card type has specific settings:

**Tasks Card**
- Background color
- Show/hide completed tasks
- Filter by family member

**Events Card**
- Background color
- Days ahead to show
- Show/hide all-day events

**Photos Card**
- Album selection
- Transition type (fade, slide)
- Photo duration

**Weather Card**
- Location
- Temperature unit
- Show forecast

## Roadmap

### Completed
- [x] Card-based display architecture
- [x] Device management with unique URLs
- [x] Card templates
- [x] User authentication with admin roles
- [x] Task management with priorities and assignments
- [x] Event management
- [x] Photo albums with multi-assignment
- [x] Photo focus position for cropping
- [x] Wallboard display with round-robin rotation
- [x] Weather integration with Open-Meteo
- [x] User and family member management
- [x] Dark theme throughout
- [x] Touch-enabled task completion

### Planned
- [ ] Google Calendar integration
- [ ] Recurring tasks
- [ ] Push notifications
- [ ] Additional card types (clock, countdown, message board)
- [ ] Task categories/tags
- [ ] File attachments on tasks

## License

Copyright (c) 2024-2025 Farlon ApS. All rights reserved.

This is proprietary software. Unauthorized copying, distribution, modification, or use of this software is strictly prohibited. See the [LICENSE](LICENSE) file for details.

## Support

For support, bug reports, and feature requests, please use [GitHub Issues](https://github.com/FarlonCom/FamilyWallboard/issues).

For licensing inquiries, contact Farlon ApS.

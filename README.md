# Family Wallboard

A modern family organization dashboard designed for wall-mounted displays. It provides real-time task management, calendar events, photo slideshows, and weather information for busy families.

## Features

### Wallboard Display
- Full-screen display optimized for wall-mounted tablets/TVs
- **Display-specific URLs** with unique access tokens (no login required)
- **Tile-based system** with configurable display tiles
- Canvases rotate in sequence with smooth fade transitions, then loop around
- Tiles can also rotate independently within a canvas
- Real-time clock and weather display
- Dark and light themes

### Display Management
- Create multiple displays (e.g., "Kitchen TV", "Office Tablet")
- Each display gets a unique secure URL
- Configure screen resolution per display
- Touch-enabled displays can mark tasks as completed
- Track display last-seen timestamps
- Enable/disable displays without deleting

### Tile System
- **Tasks Tile**: Display family tasks with priorities and assignments
- **Events Tile**: Show upcoming calendar events
- **Photos Tile**: Slideshow with photo albums
- **Weather Tile**: Current conditions and forecast
- Configurable display duration per tile
- Drag-and-drop tile reordering
- Tile-specific settings (colors, filters, etc.)

### Canvases
- Arrange tiles on a canvas to create a custom layout
- A display shows canvases one by one, then loops around
- Create reusable canvas configurations
- Apply canvases to multiple displays

### Task Management
- Create, edit, and complete tasks
- Recurring tasks
- Priority levels (High, Medium, Low) with color coding
- Due dates with overdue detection
- Multi-line descriptions
- Family member assignment with color-coded avatars
- Real-time synchronization across displays
- **Google Tasks integration**

### Motivation System
- Assign points to tasks for completed work
- Goal system with configurable waypoints
- Each waypoint can have a custom prize
- Track progress towards goals

### Calendar Events
- Manual event creation and editing
- Recurring events
- All-day event support
- Location and description fields
- Time-based grouping (Today, Tomorrow, This Week)
- **Google Calendar integration**

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
- Configurable display options per display
- Time zone and date/time format preferences
- Dark and light theme support

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
3. Go to **Admin > Displays** to create your first display
4. Copy the display URL and open it on your wall-mounted screen
5. Create a canvas, add tiles, and assign it to your display

## Usage

### Main Application
1. **Register/Login** using email and password
2. **Dashboard** shows summary of tasks, events, and photos
3. **Tasks page** for full task management
4. **Events page** for calendar event management
5. **Photos page** for photo uploads, albums, and management

### Display Setup
1. Go to **Admin > Displays**
2. Click **Add Display** and configure:
   - Display name (e.g., "Living Room TV")
   - Screen resolution
   - Touch capability
3. Create a canvas and add tiles (Tasks, Events, Photos, Weather)
4. Configure each tile's settings
5. Copy the display URL and open on your screen

### Wallboard Display
Each display has a unique URL:
- No login required — the URL token provides access
- Canvases rotate automatically, then loop around
- Tiles can also rotate independently within a canvas
- Displays current time and weather
- Touch displays can interact with tasks

### Kiosk Mode (Recommended for wall displays)
```bash
# Chrome
chrome --kiosk http://YOUR_SERVER:5000/wallboard/YOUR_DISPLAY_TOKEN

# Edge
msedge --kiosk http://YOUR_SERVER:5000/wallboard/YOUR_DISPLAY_TOKEN
```

## Configuration

### Display Settings
Each display can be configured with:
- Screen resolution (width × height)
- Touch capability
- Active/inactive status
- Canvas assignment and order
- Theme (dark or light)

### Tile Settings
Each tile type has specific settings:

**Tasks Tile**
- Background color
- Show/hide completed tasks
- Filter by family member

**Events Tile**
- Background color
- Days ahead to show
- Show/hide all-day events

**Photos Tile**
- Album selection
- Transition type (fade, slide)
- Photo duration

**Weather Tile**
- Location
- Temperature unit
- Show forecast

## Roadmap

### Completed
- [x] Tile-based display architecture
- [x] Display management with unique URLs
- [x] Canvas system for tile layout and rotation
- [x] User authentication with admin roles
- [x] Task management with priorities and assignments
- [x] Recurring tasks
- [x] Google Tasks integration
- [x] Event management
- [x] Recurring events
- [x] Google Calendar integration
- [x] Photo albums with multi-assignment
- [x] Photo focus position for cropping
- [x] Wallboard display with canvas rotation
- [x] Weather integration with Open-Meteo
- [x] User and family member management
- [x] Dark and light theme support
- [x] Touch-enabled task completion
- [x] Motivation system with points, goals, and prizes

### Planned
- [ ] TBD

## License

Copyright (c) 2026 Farlon ApS. All rights reserved.

This is proprietary software. Unauthorized copying, distribution, modification, or use of this software is strictly prohibited. See the [LICENSE](LICENSE) file for details.

## Support

For support, bug reports, and feature requests, please use [GitHub Issues](https://github.com/FarlonCom/FamilyWallboard/issues).

For licensing inquiries, contact Farlon ApS.

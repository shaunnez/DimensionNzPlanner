# Dimension NZ Festival Planner

An interactive highlight overlay planner for the Dimension NZ festival timetable.

## Features

- **Timetable Background**: Uses official timetable images as the source of truth
- **Interactive Highlights**: Neon-glow overlay blocks for events you want to attend
- **Category Toggles**: Filter by Music, Activities, or Optional events
- **Calibration Mode**: Easy positioning tool to place highlight blocks
- **Mobile Friendly**: Touch-optimized with modal dialogs on mobile devices
- **Works Offline**: Single-page app that works after initial load
- **JSON Data Model**: Edit `events.json` to update your schedule - no code changes needed

## Quick Start

1. Add your timetable images to the `images/` folder:
   - `images/timetable-1.jpg` - Main stage timetable
   - `images/timetable-2.jpg` - Performers & workshops

2. Open `index.html` in a browser (or deploy to GitHub Pages)

3. Use **Calibration Mode** to position highlight blocks:
   - Click the "Calibrate" button (bottom right)
   - Click on the image to get x/y coordinates
   - Click and drag to draw a rectangle and get x/y/width/height
   - Copy values to clipboard and paste into `events.json`

4. Edit `events.json` to add/modify your events

## Event Data Format

Each event in `events.json` has these properties:

```json
{
  "id": 1,
  "name": "Artist Name",
  "category": "music",
  "day": "Saturday",
  "time": "9:30pm - 11:00pm",
  "location": "Stage Name",
  "image": 1,
  "x": 10,
  "y": 20,
  "width": 15,
  "height": 8
}
```

| Property | Description |
|----------|-------------|
| `id` | Unique identifier |
| `name` | Event/artist name |
| `category` | `music`, `activities`, or `optional` |
| `day` | `Friday`, `Saturday`, or `Sunday` |
| `time` | Time string (free format) |
| `location` | Stage/venue name |
| `image` | Which timetable image (1 or 2) |
| `x`, `y` | Position as percentage from top-left |
| `width`, `height` | Size as percentage of image dimensions |

## Deployment

### GitHub Pages

1. Push to your GitHub repository
2. Go to Settings > Pages
3. Under "Build and deployment", select "GitHub Actions"
4. The workflow will automatically deploy on push to `main`

### Manual Deployment

Simply upload these files to any static hosting:
- `index.html`
- `events.json`
- `images/` folder with your timetable images

## File Structure

```
DimensionNzPlanner/
├── index.html          # Main application (HTML + CSS + JS)
├── events.json         # Event data (edit this!)
├── images/
│   ├── timetable-1.jpg # Main timetable image
│   └── timetable-2.jpg # Secondary timetable image
├── .github/
│   └── workflows/
│       └── deploy.yml  # GitHub Pages deployment
└── README.md
```

## UX Principles

- Timetable image is the source of truth
- Highlights reduce overwhelm, they don't recreate the schedule
- One glance clarity
- Fast category toggles
- Mobile-friendly tap behavior

## License

MIT

# AI Calorie Tracker Pro

A professional, mobile-first calorie tracking application with AI-powered food recognition. Built with HTML, CSS, and Vanilla JavaScript, ready for Android APK conversion using Capacitor.

## Features

- **AI Food Scanner** - Scan or upload food images to automatically detect food and calculate nutritional information
- **Multi-Language Support** - Full support for English, Uzbek (O'zbek), and Russian
- **Onboarding Flow** - Step-by-step user setup with automatic BMI and calorie calculations
- **Dashboard** - Real-time tracking of calories, macros, water intake, and weight progress
- **History Tracking** - Daily, weekly, and monthly food history with calendar view
- **Statistics** - Interactive charts for weight, BMI, calories, and macro progress
- **Settings** - Language switcher, dark/light mode, goal management, and data export
- **Local Storage** - All data stored locally for privacy and offline access
- **Mobile-First Design** - Premium glassmorphism UI optimized for mobile devices
- **Android Ready** - Capacitor configuration for easy APK conversion

## Technology Stack

- **HTML5** - Semantic markup
- **CSS3** - Modern styling with glassmorphism, animations, and responsive design
- **Vanilla JavaScript** - No frameworks, pure JS for maximum performance
- **Chart.js** - Interactive charts for statistics
- **Capacitor** - Native app wrapper for Android APK conversion

## Project Structure

```
/project
│
├── index.html              # Onboarding screen
├── dashboard.html         # Main dashboard
├── history.html           # Food history
├── statistics.html        # Statistics and charts
├── settings.html          # Settings and preferences
│
├── /css
│   ├── style.css          # Main styles
│   ├── animations.css     # Animations and transitions
│   └── responsive.css     # Responsive design
│
├── /js
│   ├── app.js             # Core application logic
│   ├── ai.js              # AI food recognition module
│   ├── dashboard.js       # Dashboard functionality
│   ├── charts.js          # Chart.js configurations
│   ├── language.js        # Multi-language support
│   └── storage.js         # Local storage management
│
├── /lang
│   ├── uz.json            # Uzbek translations
│   ├── ru.json            # Russian translations
│   └── en.json            # English translations
│
├── /data
│   └── foods.json         # Food database with nutritional info
│
├── /assets
│   ├── icons              # App icons (placeholders)
│   ├── images             # App images (placeholders)
│   ├── fonts              # Custom fonts (optional)
│   └── animations         # Custom animations (optional)
│
├── capacitor.config.json  # Capacitor configuration
├── package.json           # Node.js dependencies
├── manifest.json          # PWA manifest
└── README.md              # This file
```

## Installation

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn
- Android Studio (for APK building)

### Setup

1. **Clone or download the project**

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Add Capacitor platforms**
   ```bash
   npx cap init
   npx cap add android
   ```

4. **Sync files to native project**
   ```bash
   npx cap sync android
   ```

5. **Open Android Studio**
   ```bash
   npx cap open android
   ```

6. **Build APK**
   - In Android Studio, go to Build > Build Bundle(s) / APK(s) > Build APK(s)
   - Or use command line: `npm run build`

## AI Configuration

To enable AI food recognition, configure your API key in `js/ai.js`:

```javascript
const AI = {
  apiKey: 'YOUR_API_KEY_HERE',  // Add OpenAI or Gemini API key
  apiProvider: 'openai',        // 'openai' or 'gemini'
  // ...
};
```

### Supported AI Providers

1. **OpenAI Vision API** (GPT-4 Vision)
   - Get API key from: https://platform.openai.com/api-keys
   - Model: gpt-4-vision-preview

2. **Gemini Vision API**
   - Get API key from: https://makersuite.google.com/app/apikey
   - Model: gemini-pro-vision

### Fallback Mode

If no API key is configured, the app uses a local food database with 60+ food items including Uzbek, Russian, and international foods.

## Usage

### Web Version

Simply open `index.html` in a modern web browser. All data is stored in localStorage.

### Mobile App

1. Follow the installation steps above
2. Run `npm run start` to launch on connected Android device/emulator
3. Or build APK and install manually

## Features Guide

### Onboarding

First-time users complete a 7-step onboarding:
1. Welcome screen
2. Name input
3. Age input
4. Gender selection
5. Height input
6. Current weight input
7. Goal weight selection
8. Goal type (lose/maintain/gain weight)

The app automatically calculates:
- BMI (Body Mass Index)
- Daily calorie goal
- Macro recommendations (protein, carbs, fats)

### Dashboard

- **Calorie Progress** - Circular progress showing daily calorie consumption
- **Macro Tracking** - Real-time protein, carbs, and fats progress bars
- **Water Intake** - Track daily water consumption (8 glasses goal)
- **Weight Display** - Current weight with change indicator
- **Activity Stats** - Steps and calories burned
- **Today's Meals** - List of foods logged today
- **AI Tips** - Rotating health tips

### AI Food Scanner

- Tap the floating camera button
- Choose "Take Photo" or "Upload Image"
- AI analyzes the image and detects food
- Shows nutritional information (calories, protein, carbs, fats)
- Add to daily log with one tap

**Supported Foods:**
- Uzbek: Osh, Somsa, Lagman, Manti, Shashlik, Plov, Norin, Chuchvara, Mastava, Khanum, Dolma
- Russian: Pelmeni, Borscht, Blini
- International: Pizza, Sushi, Burger, Salad, Chicken, Fish, Pasta, Tacos, Burrito, and more

### History

- **Calendar View** - Visual calendar with data indicators
- **Period Selector** - Daily, weekly, monthly views
- **Food Log** - Detailed list of all logged meals
- **Statistics** - Average calories and weight
- **Export** - Export history to CSV

### Statistics

- **BMI Display** - Current BMI with category indicator
- **Weight Chart** - Line chart showing weight progress
- **Calories Chart** - Bar chart of daily calorie intake
- **Macros Chart** - Doughnut chart of macro distribution
- **Weekly Stats** - Average calories, protein, weight change, goal progress
- **Streak Counter** - Current tracking streak

### Settings

- **Language** - Switch between English, Uzbek, Russian
- **Dark Mode** - Toggle dark/light theme
- **Notifications** - Configure meal, water, and weekly reminders
- **Goals** - Update weight, height, and goal weight
- **Data** - Export/import data, clear all data
- **Privacy** - Analytics toggle, privacy policy
- **Account** - Delete account and all data

## Customization

### Adding Foods

Edit `data/foods.json` to add more foods:

```json
{
  "food_key": {
    "name": "Food Name",
    "name_uz": "O'zbek nomi",
    "name_ru": "Русское название",
    "calories": 100,
    "protein": 10,
    "carbs": 20,
    "fats": 5,
    "category": "main",
    "origin": "international"
  }
}
```

### Adding Translations

Edit language files in `/lang/`:
- `en.json` - English
- `uz.json` - Uzbek
- `ru.json` - Russian

Follow the existing JSON structure for consistency.

### Styling

Main styles in `css/style.css`:
- CSS variables for easy theming
- Glassmorphism components
- Responsive breakpoints

Animations in `css/animations.css`:
- Keyframe animations
- Utility classes for common animations

## Performance Optimization

- Lazy loading of images
- Debounced search inputs
- Local storage for offline access
- Minimal dependencies (only Chart.js and Capacitor)
- Optimized CSS with hardware acceleration

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Android Requirements

- Android 5.0 (Lollipop) or higher
- Camera permission for food scanning
- Storage permission for image uploads

## Privacy & Security

- All data stored locally on device
- No cloud storage or data transmission
- API keys (if configured) are client-side only
- No tracking or analytics by default

## License

MIT License - Feel free to use for personal or commercial projects.

## Support

For issues, questions, or contributions, please refer to the project repository.

## Roadmap

Future enhancements:
- [ ] Barcode scanner for packaged foods
- [ ] Recipe builder
- [ ] Social sharing features
- [ ] Cloud sync option
- [ ] Wear OS integration
- [ ] iOS support via Capacitor iOS

## Credits

Built with ❤️ using modern web technologies.

- Design: Glassmorphism UI with premium aesthetics
- Icons: Inline SVG for performance
- Fonts: Google Fonts (Inter)
- Charts: Chart.js
- Mobile: Capacitor

---

**Version:** 1.0.0  
**Last Updated:** May 2026

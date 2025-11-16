# SmartFIt
Smart Fit AI is an advanced, AI-powered fitness companion designed to help you achieve your dream physique with precision and personalization. It analyzes your goals, body type, lifestyle, and progress to create dynamic workout plans, tailored nutrition guidance, and real-time adjustments.
## Getting Started

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn

### Installation
Download ZIP file Frome Above 
Run in the Vscode.
1. Install dependencies:
```bash
npm install
```

2. Start the development server:
```bash
npm run dev
```

3. Open your browser and navigate to `http://localhost:5173`

### Build for Production

```bash
npm run build
```

The built files will be in the `dist` folder.

### Preview Production Build

```bash
npm run preview
```

## Customization

### Areas to Update (Commented in Code)



1. **Logo**: 
   - Location: `src/components/LandingPage.jsx` (line ~44)
   - Replace emoji icon with your logo image
   - Place logo in `public/` folder (e.g., `public/logo.png`)
   - Update CSS in `src/components/LandingPage.css` (line ~66)

2. **Background Image**: 
   - Location: `src/components/LandingPage.css` (line ~4)
   - Three options available: gradient (current), background image, or solid color
   - Place background image in `public/images/` folder
   - Uncomment and update the background-image URL

3. **Example Images**: 
   - Location: `src/components/LandingPage.jsx` (line ~117)
   - Replace placeholder divs with actual `<img>` tags
   - Place images in `public/images/` folder
   - Update image paths to `/images/your-image.jpg`
   - Recommended size: 400x400px to 800x800px

4. **Navigation Links**: 
   - Location: `src/components/LandingPage.jsx` (line ~47)
   - Update navigation items as needed
   - Add dropdown functionality if required
   - Add onClick handlers or links

5. **CTA Buttons**: 
   - Location: `src/components/LandingPage.jsx` (lines ~64, ~78)
   - Add onClick handlers or links to navigate
   - Update button text if needed

6. **Feature Descriptions**: 
   - Location: `src/components/LandingPage.jsx` (line ~7)
   - Customize feature descriptions in the `features` array
   - Add or remove features as needed

### Styling

All styles are in `src/components/LandingPage.css`. Key areas to customize:
- Colors: Update the dark theme colors throughout the CSS
- Fonts: Currently using Inter font from Google Fonts
- Spacing: Adjust padding and margins as needed
- Animations: Modify transition durations and effects

## Project Structure

```
├── index.html
├── package.json
├── vite.config.js
├── public/              # Static assets (images, logos, etc.)
│   └── images/          # Place your images here
├── src/
│   ├── main.jsx         # Entry point
│   ├── App.jsx          # Main app component
│   ├── App.css          # App styles
│   ├── index.css        # Global styles
│   └── components/
│       ├── LandingPage.jsx    # Landing page component
│       └── LandingPage.css    # Landing page styles
└── README.md
```

### Image Placement

- **Logo**: Place in `public/logo.png` or `public/images/logo.png`
- **Background Images**: Place in `public/images/background-image.jpg`
- **Example Images**: Place in `public/images/example1.jpg`, `example2.jpg`, etc.
- **Access in code**: Use paths like `/images/your-image.jpg` (starting with `/`)

## Technologies Used

- React 18
- Vite
- CSS3
- Google Fonts (Inter)

## License

MIT


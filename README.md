# LifeOS
Life OS Template - Setup Guide

Quick Start (5 Minutes)

Step 1: Download and Extract

1.
Download the life-os-template.zip file

2.
Extract to your desired location

3.
Open terminal/command prompt in the extracted folder

Step 2: Install Dependencies

Bash


# Install pnpm if you don't have it
npm install -g pnpm

# Install project dependencies
pnpm install


Step 3: Configure Weather API (Optional)

1.
Visit Tomorrow.io and create a free account

2.
Get your API key from the dashboard

3.
Open src/App.jsx and replace the API key on line 52:

JavaScript


`https://api.tomorrow.io/v4/weather/forecast?location=40.7128,-74.0060&apikey=YOUR_API_KEY_HERE&timesteps=1d&units=imperial`


Step 4: Start Development Server

Bash


pnpm run dev


Open http://localhost:5173 in your browser.

Customization Options

1. Change Location for Weather

Edit line 52 in src/App.jsx:

JavaScript


// Replace coordinates with your location
// Format: latitude,longitude
location=40.7128,-74.0060  // New York City
location=51.5074,-0.1278   // London
location=35.6762,139.6503  // Tokyo


2. Customize Colors

Edit src/App.css to change the color scheme:

CSS


:root {
  /* Light mode colors */
  --primary: #1e40af;      /* Navy blue */
  --secondary: #3b82f6;    /* Lighter blue */
  
  /* Change to your brand colors */
  --primary: #your-color;
  --secondary: #your-color;
}


3. Update Branding

In src/App.jsx, line 122:

JavaScript


<h1 className="text-2xl font-bold bg-gradient-to-r from-blue-600 to-purple-600 bg-clip-text text-transparent">
  Your Brand Name  {/* Change this */}
</h1>


4. Modify Default Content

Update the sample data in src/App.jsx:

•
Projects (lines 235-242)

•
Areas (lines 262-269)

•
Resources (lines 289-296)

•
Archives (lines 316-323)

Deployment Options

Option 1: Static Hosting (Recommended)

Bash


# Build for production
pnpm run build

# Upload the 'dist' folder to:
# - Netlify (drag & drop)
# - Vercel (connect GitHub)
# - GitHub Pages
# - Any static hosting service


Option 2: Vercel (Automatic)

1.
Push code to GitHub

2.
Connect repository to Vercel

3.
Deploy automatically on every push

Option 3: Netlify

1.
Run pnpm run build

2.
Drag the dist folder to Netlify

3.
Get instant live URL

Troubleshooting

Weather Not Loading

•
Check your API key is correct

•
Ensure you have internet connection

•
Verify the location coordinates are valid

Styles Not Applying

•
Clear browser cache

•
Check console for errors

•
Ensure all dependencies installed correctly

Build Errors

Bash


# Clear cache and reinstall
rm -rf node_modules
rm pnpm-lock.yaml
pnpm install


File Structure Explained

Plain Text


life-os-template/
├── src/
│   ├── components/ui/     # Pre-built UI components
│   ├── App.jsx           # Main application (edit this)
│   ├── App.css           # Styles and themes
│   └── main.jsx          # Entry point (don't edit)
├── public/               # Static files
├── dist/                 # Built files (after pnpm run build)
├── package.json          # Dependencies
└── README.md            # Full documentation


Advanced Customization

Adding New Features

1.
Add state variables in App.jsx

2.
Create UI components

3.
Add event handlers

4.
Style with Tailwind CSS classes

Integrating with Notion

While this is a standalone template, you can:

1.
Export data to Notion format

2.
Use Notion API to sync data

3.
Embed this as a Notion widget

Adding Data Persistence

JavaScript


// Add to useEffect hooks
localStorage.setItem('tasks', JSON.stringify(tasks))

// Load on component mount
const savedTasks = localStorage.getItem('tasks')
if (savedTasks) setTasks(JSON.parse(savedTasks))


Support

If you encounter issues:

1.
Check this guide first

2.
Review the main README.md

3.
Check browser console for errors

4.
Ensure all steps were followed correctly

License

This template is provided for personal and commercial use. You may:

•
Use for personal productivity

•
Customize for clients

•
Resell as part of larger packages

•
Modify and redistribute





Need help? The template is designed to work out of the box. Most issues are resolved by following this guide step by step.


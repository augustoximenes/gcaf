# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Google Cloud Adoption Framework (GCAF) Roadmap** - a static documentation website that provides a comprehensive 180-day implementation plan for Google Cloud adoption. The project is a single-page application built with vanilla HTML, CSS, and minimal JavaScript, hosted on Firebase.

## Architecture

### Technology Stack
- **Frontend**: Pure HTML5, CSS3, vanilla JavaScript
- **Hosting**: Firebase Hosting
- **Language**: Portuguese (Brazilian)
- **No build system**: Direct static file serving

### Directory Structure
```
public/                 # Firebase hosting root directory
├── index.html         # Main application (large, content-heavy single page)
├── 404.html          # Firebase error page
└── images/           # Static assets (domains.png, epics.png, maturity.png, phases.png)
firebase.json         # Firebase hosting configuration
.firebaserc          # Firebase project configuration (gcaf-8d101)
```

### Content Architecture
The main `index.html` contains:
- **Four Fundamental Domains**: Learn, Lead, Scale, Secure (color-coded)
- **Three Implementation Phases**: Tactical, Strategic, Transformational
- **Timeline Structure**: 180-day roadmap with specific activities and deliverables
- **Visual Elements**: Embedded diagrams and responsive table layout

## Development Commands

### Firebase Deployment
```bash
# Deploy to Firebase hosting
firebase deploy

# Deploy hosting only
firebase deploy --only hosting

# Preview before deploying
firebase serve
```

### Local Development
```bash
# Serve locally (if Firebase CLI installed)
firebase serve

# Or use any static file server
python -m http.server 8000  # Python 3
# Then visit http://localhost:8000/public/
```

### Firebase Management
```bash
# View project info
firebase projects:list

# Switch projects (if needed)
firebase use <project-id>

# View hosting info
firebase hosting:channel:list
```

## Key Development Considerations

### Content Management
- **Single-page design**: All content is in `public/index.html`
- **Table-heavy layout**: The roadmap is structured as a comprehensive table
- **Responsive design**: Uses CSS media queries for mobile compatibility
- **Color-coded system**: Each domain and phase has distinct visual styling

### Styling System
- **Phase colors**: Tactical (green), Strategic (blue), Transformational (orange)
- **Domain borders**: Learn (green), Lead (yellow), Scale (blue), Secure (red)
- **Sticky headers**: Table headers remain visible during scroll
- **Print-friendly**: Designed for both screen and print viewing

### Firebase Configuration
- **Project ID**: gcaf-8d101
- **Public directory**: `public/`
- **Hosting only**: No Firebase functions or database

### Content Updates
When updating content:
1. Edit `public/index.html` directly
2. Maintain the existing table structure and CSS classes
3. Keep phase and domain color coding consistent
4. Test responsive design on mobile devices
5. Deploy using `firebase deploy`

### Image Management
- Images are stored in `public/images/`
- Current images: domains.png, epics.png, maturity.png, phases.png
- All images should be optimized for web delivery
- Maintain consistent visual style with Google Cloud branding

## Firebase Project Details
- **Project ID**: gcaf-8d101
- **Hosting URL**: https://gcaf-8d101.web.app
- **Public directory**: `public/`
- **404 handling**: Custom 404.html page provided by Firebase
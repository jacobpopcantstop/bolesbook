# BolesBook

An interactive educational learning hub featuring standalone HTML-based activities for reading, science, and life skills development.

## Overview

BolesBook is a collection of 8 educational web applications designed to support learning through engaging, accessible interfaces. Each activity is self-contained and requires no installation or build process - just open in a browser!

## Getting Started

1. Clone or download this repository
2. Open `index.html` in any modern web browser
3. Click on any activity card to begin learning

Alternatively, open any individual `.html` file directly to access that specific activity.

## Activities

### Reading & Literacy

| Activity | File | Description |
|----------|------|-------------|
| **Phonological Awareness** | `phonaware.html` | Track progress in sound awareness skills with interactive charts |
| **Reading Comprehension** | `readingcomp.html` | Support kit with story selection and text-to-speech assistance |
| **Decoding Skills** | `decodingskills.html` | Advanced phonics assessment for word decoding practice |
| **Spelling Master** | `spelling.html` | Practice spelling with audio support and celebration effects |

### Science & Nature

| Activity | File | Description |
|----------|------|-------------|
| **BioLevels** | `BioLevels.html` | Learn taxonomy classification with the Hawaiian Goose (Nene) |
| **Life to Scale** | `lifetoScale.html` | Explore the hierarchy of life from atoms to organisms |

### Life Skills & Social-Emotional

| Activity | File | Description |
|----------|------|-------------|
| **Indy Living** | `IndyLiving.HTML` | Practice transit planning, budget math, and sensory management |
| **Savanna Squad** | `SavannaSquad.html` | Adventure game teaching self-regulation strategies |

## Technology Stack

All activities use a lightweight, CDN-based architecture requiring no build tools:

- **React 18** - Interactive UI components (loaded from CDN)
- **Tailwind CSS** - Responsive styling
- **Chart.js** - Progress visualization
- **Web Speech API** - Text-to-speech support
- **Canvas Confetti** - Celebration animations
- **Font Awesome / Lucide / Phosphor Icons** - Visual elements

## Features

- No installation required - just open in browser
- Mobile-responsive design
- Accessible interfaces with screen reader support
- Text-to-speech functionality for reading activities
- Progress tracking within sessions
- Engaging visual feedback and celebrations

## Browser Support

Works in all modern browsers:
- Chrome (recommended)
- Firefox
- Safari
- Edge

## File Structure

```
bolesbook/
├── index.html           # Main hub page with links to all activities
├── README.md            # This file
├── BioLevels.html       # Taxonomy learning game
├── IndyLiving.HTML      # Life skills assessment
├── SavannaSquad.html    # Self-regulation adventure game
├── phonaware.html       # Phonological awareness tracker
├── readingcomp.html     # Reading comprehension support
├── decodingskills.html  # Phonics decoding assessment
├── spelling.html        # Spelling practice
└── lifetoScale.html     # Hierarchy of life explorer
```

## Contributing

Feel free to add new educational activities! Each activity should be:
- Self-contained in a single HTML file
- Use CDN-loaded dependencies (Tailwind, React, etc.)
- Follow the existing design patterns for consistency
- Be mobile-responsive and accessible

## License

Educational use encouraged. Made with love for learning.

---
description: Repository Information Overview
alwaysApply: true
---

# VidShow Information

## Summary
VidShow is a lightweight HTML/JavaScript-based sequential video player designed for web integration. It provides a smooth, full-screen video slideshow experience with automatic transitions between videos. The project appears to be designed for WordPress integration, as suggested by the video URLs and .gitignore configuration.

## Structure
- **/*.html**: Main HTML files containing the video player implementations
  - `vid-show.html`: Primary implementation with full-screen video display
  - `sequential-video-slider.html`: Alternative implementation with responsive design
  - `test-simple.html`: Simple test page for video playback debugging

## Language & Runtime
**Language**: HTML, CSS, JavaScript
**Version**: Modern web standards (ES6+)
**Framework**: Vanilla JavaScript (no external frameworks)

## Implementation Details
**Video Player Class**: `SequentialVideoPlayer` JavaScript class handles:
- Video loading and preloading
- Smooth transitions between videos
- Playback controls (play/pause, next/previous)
- Keyboard navigation
- Mobile and desktop responsive design

**Key Features**:
- Automatic video preloading
- Smooth transitions with CSS
- Keyboard navigation (arrow keys, spacebar)
- Responsive design for mobile and desktop
- Error handling for video loading issues
- Automatic playback of sequential videos

## Usage
The implementation can be embedded in web pages, particularly WordPress sites:

```html
<!-- Include the HTML structure -->
<div class="video-container">
    <video id="video-0" class="video-transition video-active" preload="metadata" autoplay muted>
        <source src="path/to/video1.mp4" type="video/mp4">
    </video>
    <!-- Additional videos as needed -->
</div>

<!-- Initialize the player -->
<script>
    document.addEventListener('DOMContentLoaded', () => {
        new SequentialVideoPlayer();
    });
</script>
```

## Styling
**CSS Features**:
- Full-screen video display with object-fit: cover
- Smooth transitions between videos
- Loading indicators
- Responsive design for mobile and desktop
- Video control hiding
- Background color management for loading

## Browser Compatibility
The implementation uses modern JavaScript (ES6+) features including:
- Classes
- Promises
- Async/await
- Arrow functions
- Template literals

These features are supported in all modern browsers but may require transpilation for older browser support.
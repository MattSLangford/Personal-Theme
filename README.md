# Typeset Theme

A modern, typography-first theme for Micro.blog with clean design, excellent readability, automatic dark mode, and comprehensive internationalization support.

## Features

- **Typography-First Design** - Clean, readable layout with Inter font
- **Automatic Dark Mode** - Responds to system preferences with sophisticated gray palette
- **Multilingual Support** - 10 languages with complete translations
- **Universal Navigation** - Elegant hamburger menu that works on all screen sizes
- **Post Differentiation** - Visual distinction between titled and untitled posts
- **Full Micro.blog Integration** - Supports conversations, replies, audio narration, and all platform features
- **Responsive Design** - Optimized for all devices with accessibility features
- **CSS Variables** - Easy customization for developers

## Installation

1. **Log into your Micro.blog account**
2. **Navigate to Posts → Design → Plug-ins**
3. **Search for "Typeset Theme"** in the available plugins
4. **Click "Install"** to add the theme to your site
5. **The theme will automatically apply** to your blog once installed

## Settings Configuration

After installation, you can customize the theme through **Posts → Design → Plug-ins → Typeset Theme Settings**:

### Language Settings

**Default Language**
- **Purpose**: Sets the language for all user interface text
- **Default**: English (en)
- **Available Options**:
  - **English** (en) - Default language
  - **Español** (es) - Spanish
  - **Français** (fr) - French  
  - **Deutsch** (de) - German
  - **Português** (pt) - Portuguese
  - **中文** (zh) - Chinese (Simplified)
  - **日本語** (ja) - Japanese
  - **العربية** (ar) - Arabic
  - **Русский** (ru) - Russian
  - **हिन्दी** (hi) - Hindi

### Content Settings

**Posts per Page**
- **Purpose**: Controls how many posts appear on each page
- **Type**: Number (integer)
- **Default**: 20
- **Recommended Range**: 10-50 posts

**Custom Avatar URL**
- **Purpose**: Override the default Micro.blog avatar with a custom image
- **Type**: Text (URL)
- **Default**: Empty (uses Micro.blog default)
- **Format**: Must be a complete URL (e.g., `https://example.com/avatar.jpg`)
- **Recommended**: Square images work best (minimum 80x80 pixels)

The theme includes several built-in features that work automatically:

- **Post Dates**: Always visible in universal "2 Jan 2006" format
- **Smooth Animations**: Enabled by default, respects user motion preferences
- **Conversation Threads**: Automatically enabled for posts when configured in Micro.blog
- **Reply Buttons**: Displayed on posts (not pages) when reply services are configured

## Customizing the CSS

You can customize the theme's appearance by adding custom CSS in **Posts → Design → Edit CSS**.

### Understanding CSS Variables

The Typeset theme uses CSS custom properties (variables) that you can override. Here are the main color variables:

```css
:root {
  /* Text Colors */
  --color-text-primary: #1a1a1a;
  --color-text-secondary: #374151;
  --color-text-muted: #6b7280;
  
  /* Background Colors */
  --color-bg-primary: #fafbfc;
  --color-bg-secondary: #ffffff;
  --color-bg-tertiary: #f9fafb;
  
  /* Accent Colors */
  --color-accent-primary: #2563eb;
  --color-accent-untitled: #2563eb;
  --color-accent-titled: #059669;
  
  /* Spacing and Typography */
  --font-size-base: 1rem;
  --space-md: 1rem;
  --radius-lg: 8px;
}
```

### Common Customizations

#### Change the Primary Accent Color

```css
:root {
  --color-accent-primary: #dc2626; /* Red instead of blue */
}
```

#### Adjust Post Card Styling

```css
.post-preview,
.post,
.h-entry {
  border-radius: 16px; /* More rounded corners */
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1); /* Stronger shadow */
}
```

#### Customize Typography

```css
body {
  font-family: 'Georgia', serif; /* Use serif font */
  font-size: 1.1rem; /* Larger base font size */
}

h1, h2, h3, h4, h5, h6 {
  font-family: 'Helvetica Neue', sans-serif; /* Different heading font */
}
```

#### Modify Post Differentiation Colors

```css
/* Change untitled post accent to purple */
.untitled-post {
  border-left-color: #7c3aed;
}

.untitled-post .post-date {
  color: #7c3aed;
}

/* Change titled post accent to orange */
.post-preview:not(.untitled-post) {
  border-left-color: #ea580c;
}

.post-preview:not(.untitled-post) .post-date {
  color: #ea580c;
}
```

#### Adjust Header Styling

```css
.site-header {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
}

.site-branding h1 a {
  color: white;
}

.menu-toggle span {
  background: white;
}
```

#### Customize Dark Mode Colors

```css
@media (prefers-color-scheme: dark) {
  :root {
    --color-accent-primary: #fbbf24; /* Gold accent in dark mode */
    --color-bg-primary: #0f172a; /* Darker background */
    --color-bg-secondary: #1e293b;
  }
}
```

#### Add Custom Animations

```css
.post-preview:hover {
  transform: translateY(-4px) scale(1.02);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}
```

### Advanced Customizations

#### Hide Specific Elements

```css
/* Hide category buttons on archive page */
.category-buttons {
  display: none;
}

/* Hide reply buttons globally */
.reply-buttons {
  display: none;
}

/* Hide post dates on mobile only */
@media (max-width: 768px) {
  .post-date {
    display: none;
  }
}
```

#### Custom Navigation Styling

```css
.main-nav {
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  border: none;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
}

.nav-item {
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}
```

## Technical Details

### Browser Support
- **Modern Browsers**: Full support for Chrome, Firefox, Safari, Edge
- **CSS Grid & Flexbox**: Used throughout for layout
- **CSS Custom Properties**: Extensive use of CSS variables
- **Dark Mode**: Automatic detection via `prefers-color-scheme`

### Accessibility Features
- **Keyboard Navigation**: Full keyboard support for all interactive elements
- **Screen Readers**: Proper semantic HTML and ARIA labels
- **Reduced Motion**: Respects `prefers-reduced-motion` settings
- **High Contrast**: Support for `prefers-contrast` settings
- **Focus Indicators**: Clear focus outlines for all interactive elements

### Performance Features
- **Minimal CSS**: Optimized stylesheet with efficient selectors
- **Font Loading**: Inter font loaded efficiently from Google Fonts
- **Image Optimization**: Responsive images with proper aspect ratios
- **Lazy Loading**: Supports modern browser lazy loading

### Micro.blog Integration
- **Conversation System**: Full support for Micro.blog conversations
- **Audio Narration**: Automatic support for audio posts
- **Reply Systems**: Email, Mastodon, and conversation replies
- **Microformats**: Proper h-entry, h-feed markup
- **RSS/JSON Feeds**: Full feed compatibility
- **Cross-posting**: Optimized for social media sharing

## Troubleshooting

### Theme Not Appearing
1. Ensure the plugin is installed and activated
2. Check that no other themes are conflicting
3. Clear your browser cache and refresh

### Settings Not Working
1. Verify settings are saved in the plugin configuration
2. Allow a few minutes for changes to propagate
3. Check that JavaScript is enabled in your browser

### Dark Mode Issues
1. Ensure your system is set to dark mode
2. Clear browser cache if dark mode isn't switching
3. Some browsers may need a page refresh

### Custom CSS Not Applying
1. Ensure CSS is added in Posts → Design → Edit CSS (not plugin settings)
2. Use browser developer tools to check for CSS conflicts
3. Add `!important` to CSS rules if needed for specificity

## Support

For bug reports, feature requests, or general support:

- **GitHub Issues**: [Report bugs or request features](https://github.com/yourusername/typeset-theme)
- **Micro.blog**: [@yourusername](https://micro.blog/yourusername)
- **Documentation**: This README covers most use cases

## Credits

**Typeset Theme** is created and maintained by [Matt Langford](https://mattlangford.com) ([@mtt on Micro.blog](https://micro.blog/mtt)).

### Technologies Used
- **Hugo**: Static site generator
- **Inter Font**: Modern typography by Rasmus Andersson
- **CSS Grid & Flexbox**: Modern layout techniques
- **CSS Custom Properties**: For maintainable theming

## License

This theme is released under the MIT License. You're free to use, modify, and distribute it as needed.

## Changelog

### Version 1.3
- Simplified plugin settings (removed unnecessary toggles)
- Universal date format (2 Jan 2006)
- Fixed photo gallery padding issues
- Streamlined user experience

### Version 1.2
- Added internationalization support (10 languages)
- Comprehensive form styling
- Archive page improvements
- Removed Tinylytics integration
- Enhanced reply system
- Improved photo gallery layout

### Version 1.1
- Added automatic dark mode
- CSS variables system
- Improved accessibility
- Enhanced navigation

### Version 1.0
- Initial release
- Typography-first design
- Universal hamburger navigation
- Post differentiation system
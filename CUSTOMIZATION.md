# 🎨 Customization Guide - Lawn Simulator

## Easy Color Customization

All colors are defined as CSS variables at the top of the file. Simply change these values to customize the entire theme:

### Primary Colors
```css
--primary-color: #4f46e5;        /* Main brand color (Indigo) */
--primary-color-dark: #4338ca;   /* Darker shade for gradients */
--primary-color-light: #6366f1;  /* Lighter shade for hover */
```

**To change theme to blue:**
```css
--primary-color: #3b82f6;
--primary-color-dark: #2563eb;
--primary-color-light: #60a5fa;
```

**To change theme to purple:**
```css
--primary-color: #a855f7;
--primary-color-dark: #9333ea;
--primary-color-light: #c084fc;
```

### Lawn & Terrain Colors
```css
--lawn-color: #ecfdf5;           /* Light green for lawn */
--lawn-border-color: #a7f3d0;    /* Border around lawn */
--terrain-color: #f3f4f6;        /* Gray for terrain */
--terrain-border-color: #d1d5db; /* Terrain border */
```

**For darker lawn:**
```css
--lawn-color: #d1fae5;
--lawn-border-color: #6ee7b7;
```

### Status Colors
```css
--success-color: #10b981;  /* Green - good metrics */
--warning-color: #f59e0b;  /* Amber - medium metrics */
--danger-color: #ef4444;   /* Red - poor metrics */
--info-color: #3b82f6;     /* Blue - information */
```

## Adjusting Animations

### Speed Control
```css
--transition-speed: 0.2s;        /* Normal transitions */
--transition-speed-fast: 0.15s;  /* Quick transitions */
--transition-speed-slow: 0.35s;  /* Slow transitions */
```

**For faster animations:**
```css
--transition-speed: 0.15s;
--transition-speed-fast: 0.1s;
--transition-speed-slow: 0.25s;
```

**For slower, more dramatic:**
```css
--transition-speed: 0.3s;
--transition-speed-fast: 0.2s;
--transition-speed-slow: 0.5s;
```

### Easing Functions
```css
--transition-easing: cubic-bezier(0.4, 0, 0.2, 1);  /* Smooth ease */
--transition-bounce: cubic-bezier(0.68, -0.55, 0.265, 1.55);  /* Bounce */
```

**More easing options:**
- Linear: `linear`
- Ease out: `cubic-bezier(0, 0, 0.2, 1)`
- Ease in: `cubic-bezier(0.4, 0, 1, 1)`
- Bouncy: `cubic-bezier(0.68, -0.55, 0.265, 1.55)`
- Elastic: `cubic-bezier(0.5, 1.5, 0.5, 1)`

## Border Radius Customization

```css
--border-radius: 12px;     /* Large radius (cards) */
--border-radius-sm: 8px;   /* Small radius (buttons) */
```

**For more rounded (bubble style):**
```css
--border-radius: 20px;
--border-radius-sm: 12px;
```

**For sharp (minimal style):**
```css
--border-radius: 4px;
--border-radius-sm: 4px;
```

## Shadow Customization

```css
--box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px 0 rgba(0, 0, 0, 0.06);
--box-shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
--box-shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
```

**For softer shadows:**
```css
--box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
--box-shadow-lg: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
--box-shadow-xl: 0 10px 15px -3px rgba(0, 0, 0, 0.05);
```

**For dramatic shadows:**
```css
--box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.15);
--box-shadow-lg: 0 15px 30px -5px rgba(0, 0, 0, 0.2);
--box-shadow-xl: 0 30px 40px -10px rgba(0, 0, 0, 0.25);
```

## Terrain Margin Adjustment

Currently set to 3 meters. To change:

```javascript
// Around line 736 in the script
let terrainMarginMeters = 3;  // Change this value
```

**Examples:**
- `terrainMarginMeters = 2;` - Tighter terrain
- `terrainMarginMeters = 5;` - More terrain space
- `terrainMarginMeters = 0;` - No terrain (back to original)

## Button Hover Effects

### Disable Ripple Effect
Remove or comment out in `.btn` style:
```css
.btn::before {
    /* content: ''; */
    /* ... rest of pseudo-element ... */
}
```

### Adjust Hover Lift
Change the hover transform:
```css
.btn:hover { 
    transform: translateY(-2px);  /* Current */
    /* OR */
    transform: translateY(-4px);  /* More lift */
    /* OR */
    transform: translateY(-1px);  /* Subtle lift */
}
```

### Tool Button Icon Rotation
```css
.tool-button:hover img { 
    transform: scale(1.1) rotate(5deg);  /* Current */
    /* OR */
    transform: scale(1.15) rotate(10deg);  /* More dramatic */
    /* OR */
    transform: scale(1.05) rotate(0deg);  /* Just scale, no rotate */
}
```

## Background Pattern

### Adjust Pattern Intensity
```css
body::before {
    background-image: 
        radial-gradient(circle at 20% 50%, rgba(79, 70, 229, 0.03) 0%, transparent 50%),
        /* Change 0.03 to 0.06 for stronger effect */
        /* Change 0.03 to 0.01 for subtler effect */
}
```

### Change Pattern Positions
```css
radial-gradient(circle at 20% 50%, ...)  /* Position: 20% from left, 50% from top */
radial-gradient(circle at 80% 80%, ...)  /* Position: 80% from left, 80% from top */
```

### Remove Pattern
Comment out the entire `body::before` section.

## Glassmorphism Intensity

### Toolbox Blur
```css
.toolbox {
    backdrop-filter: blur(10px);  /* Current */
    /* OR */
    backdrop-filter: blur(20px);  /* More blur */
    /* OR */
    backdrop-filter: blur(5px);   /* Less blur */
}
```

### Adjust Transparency
```css
background: linear-gradient(135deg, 
    rgba(255, 255, 255, 0.95) 0%,  /* Change 0.95 to 0.8 for more transparency */
    rgba(255, 255, 255, 1) 100%
);
```

## Monte Carlo Sampling

Adjust accuracy vs performance:

```javascript
// Around line 741
const MONTE_CARLO_POINTS = 30000;  // Current

// For faster but less accurate:
const MONTE_CARLO_POINTS = 15000;

// For slower but more accurate:
const MONTE_CARLO_POINTS = 50000;
```

## Results Area Hover Effects

### Disable Slide Effect
```css
.results-area p:hover {
    /* transform: translateX(4px); */  /* Comment out */
}
```

### Change Slide Distance
```css
.results-area p:hover {
    transform: translateX(8px);  /* Slide more */
}
```

## Quick Theme Presets

### Dark Mode Ready Variables
```css
/* Add to :root for dark mode */
--bg-color: #1f2937;
--card-bg: #374151;
--text-color: #f9fafb;
--border-color: #4b5563;
```

### Pastel Theme
```css
--primary-color: #f8b4d9;
--success-color: #b4f8d4;
--warning-color: #f8e4b4;
--danger-color: #f8b4b4;
```

### Ocean Theme
```css
--primary-color: #06b6d4;
--primary-color-dark: #0891b2;
--lawn-color: #e0f2fe;
--terrain-color: #f0f9ff;
```

---

## 🔥 Pro Tips

1. **Test Incrementally**: Change one variable at a time
2. **Browser Cache**: Hard refresh (Cmd+Shift+R) to see changes
3. **Inspect Element**: Use browser dev tools to test live
4. **Backup First**: Save original values before experimenting
5. **Color Contrast**: Ensure text is readable on backgrounds

## 📱 Responsive Breakpoint

Current mobile breakpoint is `992px`. To adjust:

```css
@media (max-width: 992px) {  /* Change 992px to your preference */
    /* Mobile styles */
}
```

---

Happy customizing! 🎨✨

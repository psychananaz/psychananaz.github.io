# CLAUDE.md - AI Assistant Guide

> Documentation for AI assistants working on psychananaz.github.io

**Last Updated**: 2025-12-24
**Repository**: psychananaz.github.io
**Custom Domain**: psychananaz.dev
**Type**: GitHub Pages Personal Portfolio

---

## Repository Overview

This is a personal portfolio website hosted on GitHub Pages with a custom domain. The site features a **neobrutalist design aesthetic** characterized by bold borders, sharp edges, prominent shadows, and high-contrast colors.

### Tech Stack
- **Frontend**: Pure HTML5 with inline CSS
- **Styling**: CSS custom properties (CSS variables)
- **Deployment**: GitHub Pages (automatic deployment from main branch)
- **Domain**: Custom domain via CNAME (psychananaz.dev)
- **Dependencies**: None (zero external libraries or frameworks)

---

## Codebase Structure

```
psychananaz.github.io/
├── CNAME                 # Custom domain configuration
├── README.md            # Repository description (minimal)
├── index.html           # Main portfolio page (single-page site)
└── CLAUDE.md           # This file - AI assistant guide
```

### File Descriptions

**CNAME**
- Contains the custom domain: `psychananaz.dev`
- Required for GitHub Pages custom domain setup
- Should not be modified unless changing domains

**README.md**
- Minimal repository description
- Just contains the repository name
- Keep simple and concise

**index.html**
- Self-contained single-page application
- Includes all HTML, CSS, and structure
- No external CSS or JavaScript files
- Uses inline `<style>` tag for all styling
- Responsive design with mobile-first approach

---

## Design System

### Design Philosophy: Neobrutalism

The site follows **neobrutalist design principles**:
- Bold, thick borders (4px solid black)
- Prominent drop shadows (offset shadows, not blur)
- High contrast colors
- Sharp, clean edges
- Minimal, functional layout
- No gradients or subtle effects
- Direct, assertive visual language

### CSS Architecture

#### CSS Custom Properties (Variables)

Located at `:root` in index.html:

```css
--bg: #f6f6f6;          /* Page background */
--ink: #0b0b0b;         /* Primary text/border color */
--muted: #2a2a2a;       /* Secondary text */
--accent: #ff3bd4;      /* Highlight color (bright pink) */
--card: #ffffff;        /* Card backgrounds */
--border: 4px solid var(--ink);  /* Standard border style */
--shadow: 10px 10px 0 var(--ink); /* Card shadow */
--radius: 10px;         /* Border radius */
--max: 52rem;           /* Max content width */
```

#### Key Design Tokens

**Borders**
- Standard: `4px solid var(--ink)`
- Always solid, never dashed or dotted
- Consistent thickness across all elements

**Shadows**
- Cards: `10px 10px 0 var(--ink)` (hard shadow, no blur)
- Buttons: `6px 6px 0 var(--ink)` (smaller hard shadow)
- Active buttons: `3px 3px 0 var(--ink)` (pressed state)
- Never use blur or soft shadows

**Spacing**
- Max content width: `52rem`
- Standard gap between grid items: `1rem`
- Card padding: `1.25rem`
- Section margins: `1.25rem` to `2.5rem`

**Colors**
- Background: Light gray (`#f6f6f6`)
- Text: Near black (`#0b0b0b`)
- Accent: Bright pink (`#ff3bd4`)
- Cards: Pure white (`#ffffff`)

**Typography**
- Font stack: System fonts (ui-sans-serif, system-ui, etc.)
- No custom web fonts
- Responsive font sizing with `clamp()`
- Line height: `1.35` for body, `1.05` for headings

### Component Patterns

**Cards**
```css
.card {
  background: var(--card);
  border: var(--border);
  border-radius: var(--radius);
  box-shadow: var(--shadow);
  padding: 1.25rem;
}
```

**Buttons**
```css
.btn {
  display: inline-block;
  padding: .7rem .9rem;
  border: var(--border);
  border-radius: calc(var(--radius) - 2px);
  background: #fff;
  box-shadow: 6px 6px 0 var(--ink);
  font-weight: 800;
}
```

**Tags**
```css
.tag {
  display: inline-block;
  padding: .35rem .6rem;
  border: var(--border);
  background: #fff;
  box-shadow: 6px 6px 0 var(--ink);
  text-transform: uppercase;
  letter-spacing: .06em;
}
```

---

## Development Workflow

### Git Branching Strategy

**Main Branch**
- Default branch (typically `main` or `master`)
- Protected branch - do not push directly
- Automatically deploys to GitHub Pages

**Feature Branches**
- Create feature branches from main
- Naming convention: `claude/[description]-[session-id]`
- Example: `claude/add-claude-documentation-b1yFf`
- Always push to feature branches, never directly to main

### Making Changes

1. **Create/Switch to Feature Branch**
   ```bash
   git checkout -b claude/[description]-[session-id]
   ```

2. **Make Changes**
   - Edit files as needed
   - Test locally by opening index.html in browser
   - Ensure responsive design works (test mobile/desktop)

3. **Commit Changes**
   ```bash
   git add [files]
   git commit -m "Clear, descriptive message"
   ```

4. **Push to Remote**
   ```bash
   git push -u origin claude/[description]-[session-id]
   ```

5. **Create Pull Request**
   - Use GitHub CLI or web interface
   - Provide clear description of changes
   - Reference any related issues

### Testing Locally

Since this is a static site:
1. Open `index.html` directly in a web browser
2. Test responsive design:
   - Desktop view (> 820px width)
   - Mobile view (< 820px width)
3. Check all links work correctly
4. Verify visual consistency with neobrutalist design

---

## Key Conventions

### HTML Conventions

**Structure**
- Use semantic HTML5 elements
- Keep structure flat and simple
- Avoid deep nesting
- Use `<header>`, `<section>`, `<footer>` for layout

**Accessibility**
- Include proper `alt` attributes for images
- Use `aria-disabled="true"` for disabled links
- Maintain semantic heading hierarchy (h1 → h2 → h3)
- Include `rel="me"` for personal profile links
- Use `:focus-visible` for keyboard navigation

**Classes**
- Use descriptive, semantic class names
- Follow existing naming conventions
- Prefer classes over IDs for styling
- Keep names lowercase and hyphenated

### CSS Conventions

**Organization**
1. CSS variables (`:root`)
2. Reset/base styles (`*`, `html`, `body`)
3. Layout components (`.wrap`, `.grid`)
4. UI components (`.card`, `.btn`, `.tag`)
5. Typography (`h1`, `h2`, etc.)
6. Utilities and states (`:hover`, `:active`, `:focus-visible`)
7. Media queries (at the end)

**Guidelines**
- Always use CSS custom properties for colors and spacing
- Never use inline styles (except for one-off overrides)
- Keep specificity low
- Use mobile-first responsive design
- Group related styles together
- Include comments for complex sections

**Responsive Design**
- Mobile-first approach
- Breakpoint at `820px` for desktop layout
- Use CSS Grid for layout (not Flexbox for main structure)
- Use `clamp()` for fluid typography

### Content Guidelines

**Tone**
- Direct and assertive
- Minimal and functional
- "Sharp edges, loud borders, zero fluff"
- Keep copy short and impactful

**Placeholder Content**
- Email link: Update `href="mailto:you@example.com"` with real email
- Disabled links: Use `aria-disabled="true"` and `href="#"`
- "Now" section: Keep current activities updated
- Links section: Add real links when available

---

## Common Tasks

### Adding a New Section

1. Create a new `<div class="card">` element
2. Add semantic heading (`<h2>`)
3. Include content with proper structure
4. Place in appropriate container (`.grid` for side-by-side, or standalone)
5. Test responsive behavior

Example:
```html
<div class="card">
  <h2>Section Title</h2>
  <p>Content goes here.</p>
</div>
```

### Adding a New Button/Link

1. Use `.btn` class for button styling
2. Add `.primary` class for accent color
3. Include proper `href` and accessibility attributes

Example:
```html
<a class="btn primary" href="https://example.com" rel="me">Button Text</a>
```

### Updating Colors

1. Modify CSS custom properties in `:root`
2. Maintain high contrast for accessibility
3. Test against all components
4. Keep the bold, assertive aesthetic

### Adding Interactive Elements

**Guidelines**
- Keep interactions simple and performant
- Avoid heavy JavaScript libraries
- Use CSS for animations when possible
- Consider throttling/debouncing for scroll/mousemove events
- Test on mobile devices

---

## Deployment

### GitHub Pages Configuration

**Automatic Deployment**
- Pushes to main branch automatically deploy
- Deployment takes 1-2 minutes
- Check Actions tab for deployment status

**Custom Domain**
- Domain configured via CNAME file
- DNS must point to GitHub Pages
- HTTPS automatically enabled by GitHub

**Deployment Checklist**
1. All changes committed and pushed
2. Pull request reviewed and approved
3. Merge to main branch
4. Wait for GitHub Actions deployment
5. Verify live site at psychananaz.dev

### Verifying Deployment

```bash
# Check GitHub Actions status
gh run list

# View specific workflow run
gh run view [run-id]
```

Or visit: https://github.com/psychananaz/psychananaz.github.io/actions

---

## AI Assistant Guidelines

### When Making Changes

**DO:**
- Read existing files before making changes
- Maintain the neobrutalist design aesthetic
- Keep the codebase simple (no unnecessary dependencies)
- Use CSS custom properties for consistent styling
- Test responsive design at multiple breakpoints
- Follow semantic HTML practices
- Include accessibility features
- Write clear, descriptive commit messages
- Work on feature branches (never push to main directly)

**DON'T:**
- Add external CSS or JavaScript frameworks
- Introduce build tools or package managers (unless explicitly requested)
- Use soft shadows, gradients, or subtle effects
- Break the visual consistency
- Add unnecessary complexity
- Remove accessibility features
- Make assumptions about user preferences

### Code Review Checklist

Before committing changes:
- [ ] HTML is semantic and accessible
- [ ] CSS follows existing patterns and uses custom properties
- [ ] Design maintains neobrutalist aesthetic
- [ ] Responsive design works on mobile and desktop
- [ ] Links have proper attributes (`rel`, `aria-*`)
- [ ] No console errors
- [ ] No external dependencies added
- [ ] File structure remains simple
- [ ] Changes are committed to a feature branch

### Common Questions

**Q: Should I add a CSS framework like Tailwind or Bootstrap?**
A: No. This site intentionally uses no external dependencies.

**Q: Should I create separate CSS files?**
A: No. Keep CSS inline in the `<style>` tag for simplicity.

**Q: Can I add JavaScript for interactivity?**
A: Yes, but keep it minimal and inline. Avoid external libraries unless necessary.

**Q: Should I create a build process?**
A: No, unless the user specifically requests it. Keep the site simple and static.

**Q: Can I modify the color scheme?**
A: Yes, but only if requested. Maintain high contrast and bold colors consistent with neobrutalism.

**Q: Should I add animations?**
A: Keep animations minimal. Use CSS transitions for hover states. Complex animations should be performance-optimized and throttled.

---

## Project History

### Evolution
1. **Initial Commit**: Minimal index.html for GitHub Pages
2. **Dark Mode Design**: Enhanced with dark mode and gradients
3. **Minimal Dark Mode**: Redesigned without gradients
4. **Interactive Animations**: Added homepage animations with performance optimizations
5. **Neobrutalist Redesign**: Current iteration with bold borders and sharp aesthetics
6. **CNAME Configuration**: Added custom domain support

### Design Iterations
- Started with minimal dark theme
- Evolved through gradient experiments
- Settled on neobrutalist aesthetic
- Removed complex visual effects for cleaner design
- Focused on bold, assertive visual language

---

## Resources

### Neobrutalism Design References
- Bold borders (4px+)
- Hard drop shadows (no blur)
- High contrast colors
- Geometric shapes
- Functional, minimal layouts
- Assertive typography

### Accessibility Standards
- WCAG 2.1 Level AA compliance
- Keyboard navigation support
- Semantic HTML structure
- Proper ARIA labels
- Focus indicators

### GitHub Pages Documentation
- [Custom Domains](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)
- [Deployment](https://docs.github.com/en/pages/getting-started-with-github-pages)
- [CNAME Configuration](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)

---

## Contact & Maintenance

**Repository Owner**: psychananaz
**GitHub**: https://github.com/psychananaz
**Website**: https://psychananaz.dev

### Maintenance Notes
- Review and update content quarterly
- Check for broken links monthly
- Update "Now" section regularly
- Monitor GitHub Actions for deployment issues
- Keep dependencies (if any) minimal

---

**End of Documentation**

*This documentation is maintained for AI assistants working on this repository. Keep it updated as the project evolves.*

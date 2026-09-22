# SpendWise Dashboard Shell

## Project Summary
The **SpendWise Dashboard Shell** serves as the visual layout foundation for a financial tracking web application. This phase focuses entirely on establishing modern, responsive web layout standards using **CSS Grid** for macro-level structural placement and **Flexbox** for micro-level alignment within components.

---

## Technical Architectural Breakdown

### 1. Overall Layout (CSS Grid & Flexbox)
- **Macro Layout (CSS Grid):** The page container `.dashboard-container` uses a two-column CSS Grid (`240px 1fr`) to separate the Sidebar navigation from the main workspace. The card container `.cards-grid` uses CSS Grid with `repeat(auto-fit, minmax(260px, 1fr))` to automatically manage responsive card columns.
- **Component Layout (Flexbox):** Flexbox is used inside the `.header` to space out titles and user profile controls (`justify-content: space-between`), within `.sidebar` to stack navigation links vertically, and inside `.card-header` to align labels and status badges.

### 2. CSS Custom Properties (`:root` Theme)
All global variables are declared on the `:root` pseudo-class:
- `--brand-color`: Primary blue identity tone used for brand text, active states, and focus rings.
- `--accent-color`: Green highlight tone for positive performance indicators.
- `--bg-color` & `--card-bg`: Surface colors controlling overall canvas and card backgrounds.
- `--text-primary` & `--text-secondary`: Enforces clear visual hierarchy between monetary numbers and secondary metadata.

### 3. Responsiveness (< 768px)
A media query targets viewports below `768px`, collapsing the CSS Grid layout into a single-column layout (`grid-template-columns: 1fr`). Navigation menu items adapt into a horizontal layout for accessible mobile scrolling.

### 4. Micro-interactions
All 6 category cards (`Food`, `Transport`, `Rent`, `Entertainment`, `Savings`, and `Utilities`) feature accessible micro-interactions. Utilizing `transition: transform 200ms, box-shadow 200ms`, hover and keyboard focus (`:focus`) events generate a subtle -4px vertical elevation paired with an expanded drop shadow.

### 5. Stretch Goal: Dark Theme Support
Included automatic dark mode detection via `@media (prefers-color-scheme: dark)` which overrides only the `:root` color custom properties to present a high-contrast dark theme based on OS-level user preferences.
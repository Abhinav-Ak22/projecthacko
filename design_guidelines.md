# CityFix Design Guidelines

## Design Approach

**Selected Approach:** Design System (Material Design) with civic-tech platform influences

**Justification:** CityFix is a utility-focused, information-dense platform requiring trust, accessibility, and consistent patterns across diverse user demographics. Drawing from Material Design's proven civic application patterns (Google Maps, Android emergency services) with inspiration from successful 311 platforms and SeeClickFix.

**Core Principles:**
1. **Clarity Over Creativity** - Every interaction must be immediately understandable
2. **Mobile-First Reporting** - Most citizens report from phones at issue locations
3. **Trust Through Transparency** - Clear status indicators and progress tracking
4. **Universal Accessibility** - Designed for all ages and tech literacy levels

## Typography System

**Font Stack:** Inter (via Google Fonts CDN) for clean, highly legible interface text

**Hierarchy:**
- **Hero Headings (H1):** 3xl (mobile) / 5xl (desktop), font-semibold, tracking-tight
- **Section Headings (H2):** 2xl (mobile) / 4xl (desktop), font-semibold
- **Subsection Headings (H3):** xl (mobile) / 2xl (desktop), font-medium
- **Card Titles (H4):** lg / xl, font-medium
- **Body Text:** base / lg, font-normal, leading-relaxed for readability
- **Captions/Meta:** sm / base, font-normal
- **Buttons/CTAs:** base / lg, font-medium, uppercase tracking for primary actions
- **Status Labels:** xs / sm, font-semibold, uppercase tracking-wide

## Layout System

**Spacing Primitives:** Consistent use of Tailwind units: 2, 4, 6, 8, 12, 16, 20, 24 for predictable rhythm

**Grid System:**
- **Container Max-Widths:** max-w-7xl for main content, max-w-6xl for forms, max-w-4xl for reading content
- **Section Padding:** py-12 px-4 (mobile), py-16 px-6 (tablet), py-24 px-8 (desktop)
- **Component Spacing:** gap-6 (mobile), gap-8 (desktop) for card grids
- **Form Field Spacing:** space-y-6 for vertical form layouts

**Responsive Breakpoints:**
- Mobile: Base styles (< 768px)
- Tablet: md: (768px+)
- Desktop: lg: (1024px+)
- Wide: xl: (1280px+)

## Component Library

### Navigation & Header
- **Desktop Header:** Full-width sticky navigation with logo left, main nav center, user actions right (Login/Profile + "Report Issue" CTA button)
- **Mobile Header:** Collapsible hamburger menu with prominent "Report Issue" floating action button
- **Breadcrumbs:** For admin dashboard and nested pages (Home > My Complaints > Issue #1234)

### Homepage Structure
1. **Hero Section (80vh):** Full-width with subtle civic imagery background, centered content featuring bold headline, descriptive subtitle, dual CTAs ("Report Issue" primary + "View Map" secondary), and trust indicator ("10,000+ Issues Resolved")
2. **Quick Stats Bar:** Four-column grid (single column mobile) showing key metrics with large numbers and icon indicators
3. **How It Works:** Three-column process cards (stack mobile) with numbered steps, icons, and brief descriptions
4. **Live Issue Feed:** Two-column layout (single mobile) - left: recent issues list with thumbnails, right: mini embedded map preview
5. **Category Overview:** Four-column grid of issue categories with icons and issue counts
6. **CTA Section:** Centered with supporting text and primary action button

### Map Integration
- **Full-Screen Map View:** Expandable map canvas with floating controls panel
- **Filter Sidebar (Desktop):** Left-aligned 320px panel with category checkboxes and status filters
- **Mobile Filters:** Bottom sheet drawer with same filtering options
- **Map Markers:** Custom SVG pins with status-based visual treatment, clustering for dense areas
- **Issue Card Popups:** Compact cards showing issue thumbnail, title, status badge, and "View Details" link

### Forms & Input Components
- **Issue Report Form:** Single-column layout with clear section breaks
  - Title input (full width)
  - Category dropdown with icon previews
  - Description textarea (4-6 rows)
  - Image upload zone with drag-and-drop, preview thumbnails
  - Map selector: embedded mini-map with pin placement
  - Current location quick-action button
- **Form Validation:** Inline error messages below fields, success states with checkmarks
- **File Upload:** Large dropzone area with icon, supporting text, file type indicators, and thumbnail preview grid

### Status Tracking
- **Progress Indicator:** Horizontal stepper showing three stages with connecting lines, active stage highlighted, completed stages with checkmarks
- **Status Badges:** Pill-shaped labels with icons (base size, increases to lg for emphasis)
- **Timeline View:** Vertical timeline for admin remarks and status updates with timestamps

### Dashboard Components

**Public User Dashboard:**
- **My Complaints Table:** Sortable columns (ID, Title, Category, Status, Date), responsive card layout on mobile
- **Dashboard Stats:** Three-card row showing personal metrics (Total Reports, Pending, Resolved)

**Admin Dashboard:**
- **Analytics Grid:** 
  - Top row: Four stat cards with trend indicators
  - Second row: Two-column (stack mobile) - bar chart (issues by category) + line chart (resolution trends)
  - Third row: Full-width data table with filters, search, pagination
- **Issue Management Table:** Expandable rows revealing additional details, quick-action buttons for status updates
- **Bulk Actions Toolbar:** Appears when items selected, floating above table

### Cards & Data Display
- **Issue Cards:** Consistent card pattern with 16px padding, rounded-lg corners, shadow-sm
  - Card header: thumbnail image (aspect-video, 200px height)
  - Card body: category badge, title (font-medium, lg), truncated description, metadata row (date, location)
  - Card footer: status badge + action button aligned right
- **Stat Cards:** Centered content with large number display (4xl), label below (sm), icon top-right, subtle hover lift
- **Admin Issue Detail Cards:** Expanded format with full description, image gallery, status history, admin action panel

### Buttons & CTAs
- **Primary CTA:** Large (px-8 py-4), font-medium, rounded-lg, shadow-md with hover lift
- **Secondary Buttons:** Outlined style, px-6 py-3, rounded-lg
- **Icon Buttons:** Square (40px), rounded-full for map controls and quick actions
- **Floating Action Button (Mobile):** 56px circle, fixed bottom-right with 16px margin, shadow-lg

### Notifications & Feedback
- **Toast Notifications:** Top-right position, auto-dismiss, icon + message + close button
- **Alert Banners:** Full-width context bars for system messages, dismissible
- **Loading States:** Skeleton screens for tables, spinner overlays for forms

### Icons
**Icon Library:** Heroicons (via CDN)
**Usage:**
- Navigation: 24px icons with text labels
- Category indicators: 32px icons in selection UI, 20px in badges
- Status indicators: 16px icons inline with text
- Action buttons: 20px icons, 24px for primary CTAs
- Map markers: Custom SVG 40px height

## Accessibility Requirements
- **Color Independence:** Never rely solely on visual indicators; always pair with text/icons
- **Touch Targets:** Minimum 44px for all interactive elements
- **Form Labels:** Always visible (not placeholder-only), associated with inputs
- **Keyboard Navigation:** Full keyboard support for forms, tables, map controls
- **Screen Reader:** Proper ARIA labels for status changes, dynamic content updates
- **Focus States:** Clear 2px focus rings on all interactive elements

## Images

**Hero Section:** Yes - civic-themed imagery (city skyline, community scenes, or infrastructure) as background with subtle overlay treatment to ensure text legibility

**Image Placement:**
1. **Homepage Hero:** Full-width background image (1920x800px) showing vibrant city life or civic infrastructure
2. **Issue Cards:** Uploaded issue photos as card headers (aspect-video, optimized thumbnails)
3. **Category Icons:** Custom illustrated icons or Heroicon library for issue types
4. **About Page:** Team/community photos showcasing civic engagement
5. **Admin Dashboard:** Data visualization charts (no decorative images)

**Image Treatment:**
- Hero backgrounds: Subtle gradient overlay for text contrast
- Issue photos: Rounded corners (rounded-lg), object-cover to maintain aspect ratio
- Empty states: Friendly illustrations for "no issues found" scenarios

## Animations

**Strategic Use Only:**
- **Page Transitions:** Subtle fade-in for route changes (200ms)
- **Map Markers:** Gentle drop animation when pins appear (300ms ease-out)
- **Status Updates:** Badge color transition (200ms) when status changes
- **Form Submission:** Button loading state with spinner
- **Card Hover:** Subtle lift (translateY -2px, shadow increase) - 150ms
- **NO scroll animations, parallax, or decorative motion**

This design system prioritizes clarity, trust, and efficiency—ensuring CityFix serves all citizens effectively while maintaining professional government-grade reliability.
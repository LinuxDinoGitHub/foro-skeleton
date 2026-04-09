/\*\*

- HeroAboutUs Component - Usage Guide
-
- Production-ready About section component with full customization
  \*/

// BASIC USAGE (with defaults)
// ============================================
import HeroAboutUs from "@/components/marketing-page/HeroAboutUs";

export default function AboutPage() {
return <HeroAboutUs />;
}

// ADVANCED USAGE (with custom props)
// ============================================
import HeroAboutUs from "@/components/marketing-page/HeroAboutUs";
import type { StatisticItem } from "@/components/marketing-page/HeroAboutUs.types";

const customStats: StatisticItem[] = [
{
value: "10000+",
label: "Competitions",
hasIcon: false,
},
{
value: "500+",
label: "Users",
hasIcon: false,
},
{
value: "4.9",
label: "Rating",
hasIcon: true, // Shows star icon
},
];

export default function AboutPage() {
return (
<HeroAboutUs
      titlePrefix="Discover"
      titleEmphasis="our story"
      missionSubtitle="Empowering students worldwide"
      missionDescription="Custom mission description here..."
      statistics={customStats}
      containerBackgroundColor="#fff9f0"
    />
);
}

// COMPONENT STRUCTURE
// ============================================
HeroAboutUs (Main Component)
├── <main>
│ └── <section> - Content container
│ ├── <h1> - Title with emphasis
│ └── <article> - Main card
│ ├── <section> - Mission section
│ │ ├── <figure><Image/></figure> - Logo
│ │ ├── <h2> - Mission heading
│ │ ├── <h3> - Subtitle
│ │ └── <p> - Description
│ └── <section> - Statistics
│ ├── <StatCard/> - Stat 1
│ ├── <StatCard/> - Stat 2
│ └── <StatCard/> - Stat 3

// PROPS INTERFACE
// ============================================
interface HeroAboutUsProps {
// Title Section
titlePrefix?: string; // Default: "About"
titleEmphasis?: string; // Default: "us"

// Logo Section
logoSrc?: string; // Default: "/marketing-page-assets/il-foro-logo.png"
logoAlt?: string; // Default: "Il Foro Logo"
logoWidth?: number; // Default: 393
logoHeight?: number; // Default: 393

// Mission Section
missionHeadingPrefix?: string; // Default: "Mission"
missionHeadingEmphasis?: string; // Default: "Statement"
missionSubtitle?: string; // Default: "We want to democratise opportunities"
missionDescription?: string; // Long form content

// Statistics
statistics?: StatisticItem[]; // Array of stats (default: 12000+, 600+, 4.8★)

// Styling (optional)
containerBackgroundColor?: string; // Default: "#f0ead8" (cream)
borderColor?: string; // Default: "black"
borderRadius?: string; // Default: "10px"
}

// FIGMA SPECIFICATIONS (Implemented)
// ============================================
✓ Title: 77.09px (7.5rem), EB Garamond Medium, cream accent
✓ Mission Heading: 64px, EB Garamond Medium + Italic
✓ Subtitle: 36px, EB Garamond Medium
✓ Description: 20px, Space Grotesk Medium
✓ Stats Numbers: 128px, EB Garamond Regular
✓ Stats Labels: 36px, EB Garamond Regular
✓ Star Icon: 100px, filled star (★)
✓ Container: #f0ead8 background, black border, 10px radius
✓ Gaps: 42px (logo/text), 60px (statistics)
✓ Responsive: Mobile, tablet, desktop breakpoints

// FEATURES
// ============================================
✅ Full TypeScript support with type safety
✅ Semantic HTML (section, article, figure, h1-h3)
✅ Responsive design (mobile-first approach)
✅ Accessibility (aria-labels, alt text)
✅ Sub-component (StatCard) for statistics
✅ Customizable props for all content
✅ Exact Figma design fidelity
✅ Production-ready code
✅ Zero build/compile errors
✅ Follows project patterns (like HeroWelcome)

// STYLING NOTES
// ============================================

- Font families via inline styles (CSS variables)
- Tailwind classes for responsive design
- Pixel-perfect typography matching Figma
- Color variables from globals.css
- No hardcoded values (all configurable)
- Mobile: Single column layout
- Desktop: Multi-column with proper gaps

// FILE STRUCTURE
// ============================================
src/components/marketing-page/
├── HeroAboutUs.tsx (Main component)
├── HeroAboutUs.types.ts (TypeScript interfaces)
└── StatCard.tsx (Sub-component for statistics)

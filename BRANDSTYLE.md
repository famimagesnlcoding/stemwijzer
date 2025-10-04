# BRANDSTYLE.md - Stemwijzer 2025
## Complete Design System & UI/UX Guidelines

**Versie:** 1.0
**Laatst bijgewerkt:** 4 Oktober 2025
**Auteur:** Stemwijzer Design Team
**Doelgroep:** UI/UX Designers, Digital Designers, Frontend Developers

---

# INHOUDSOPGAVE

## [1. BRAND IDENTITY](#1-brand-identity)
1.1 Brand Missie & Visie
1.2 Brand Personality
1.3 Design Principes
1.4 Target Audience

## [2. KLEURENPALET](#2-kleurenpalet)
2.1 Primaire Kleuren
2.2 Thema Kleuren
2.3 Partij Kleuren
2.4 Semantische Kleuren
2.5 Contrast & Accessibility
2.6 Kleurgebruik Rules

## [3. TYPOGRAFIE](#3-typografie)
3.1 Font Stack
3.2 Type Scale
3.3 Font Weights
3.4 Line Heights & Spacing
3.5 Typography Rules

## [4. SPACING & LAYOUT](#4-spacing--layout)
4.1 Spacing System
4.2 Grid System
4.3 Responsive Breakpoints
4.4 Container Widths

## [5. UI COMPONENTS](#5-ui-components)
5.1 Buttons
5.2 Cards
5.3 Modals
5.4 Tooltips
5.5 Badges
5.6 Progress Indicators
5.7 Icons

## [6. ANIMATIONS & INTERACTIONS](#6-animations--interactions)
6.1 Timing & Easing
6.2 Keyframe Animations
6.3 Hover States
6.4 Focus States
6.5 Transition Rules

## [7. RESPONSIVE DESIGN](#7-responsive-design)
7.1 Mobile First Approach
7.2 Breakpoint Strategy
7.3 Touch Targets
7.4 Responsive Typography

## [8. ACCESSIBILITY](#8-accessibility)
8.1 WCAG Guidelines
8.2 Keyboard Navigation
8.3 Screen Readers
8.4 Color Contrast
8.5 Focus Management

## [9. DESIGN PATTERNS](#9-design-patterns)
9.1 Welkomstscherm
9.2 Thema Intro
9.3 Stelling Interface
9.4 Resultaten Scherm
9.5 Modal Pattern
9.6 Tooltip Pattern

## [10. ASSETS & RESOURCES](#10-assets--resources)
10.1 Icon Library
10.2 Custom Cursor
10.3 Confetti Library
10.4 External Dependencies

---

# 1. BRAND IDENTITY

## 1.1 Brand Missie & Visie

### Missie Statement
> **"Elke kiezer verdient een transparante, neutrale en goed geïnformeerde stemkeuze."**

De Stemwijzer 2025 maakt politieke keuzes toegankelijk door complexe standpunten te vertalen naar begrijpelijke stellingen, ondersteund door verificeerbare bronnen en educatieve uitleg.

### Visie
Een Nederland waar elke burger, ongeacht leeftijd of politieke kennis, met vertrouwen kan stemmen op basis van feiten in plaats van gevoel.

### Brand Values

#### 🎯 Transparantie
- Verificeerbare bronnen bij elk standpunt
- Open methodologie en berekeningen
- Coverage transparency (welke partijen hebben antwoorden gegeven?)

#### ⚖️ Neutraliteit
- Gelijke behandeling van alle 27 partijen
- Gebalanceerde stellingen (geen symmetrie bias)
- Fact-based, geen meningen

#### 📚 Educatie
- Uitleg bij elke stelling (6 secties)
- Context bij resultaten
- AI-powered partijadvies voor holistische keuze

## 1.2 Brand Personality

### Tone of Voice

**Vriendelijk maar professioneel**
```
✅ DO: "Ontdek welke partij het beste bij jou past"
❌ DON'T: "Kies nu je partij!"
```

**Educatief zonder betuttelend**
```
✅ DO: "Dit betekent dat de belasting op arbeid lager wordt"
❌ DON'T: "Je moet weten dat belastingen complex zijn"
```

**Toegankelijk zonder kinderachtig**
```
✅ DO: "Klimaatneutraal betekent netto 0 CO2-uitstoot"
❌ DON'T: "Klimaatneutraal is superbelangrijk!"
```

### Visual Personality

**Modern & Schoon**
- Ruime witruimte
- Duidelijke hiërarchie
- Minimaal ornamenten
- Focus op content

**Warm & Toegankelijk**
- Zachte kleuren (coral, cream)
- Ronde hoeken (rounded-lg = 8px)
- Speelse animaties (confetti, bounce)
- Custom cursor (✍ schrijvende hand)

**Betrouwbaar & Professioneel**
- Navy als anchor kleur
- Serif headings (Domine)
- Gestructureerde layouts
- Consistent gebruik van badges/icons

## 1.3 Design Principes

### 1. Clarity over Complexity
> "Een 18-jarige moet binnen 3 seconden snappen hoe het werkt."

**Implementatie:**
- Eén hoofdactie per scherm
- Grote, duidelijke knoppen (min 48×48px)
- Visuele hiërarchie: grote stellingtekst, kleinere toelichting
- Progressie-indicator altijd zichtbaar

### 2. Education through Interaction
> "Elke klik is een leermoment."

**Implementatie:**
- Info (i) icoon bij elke stelling → uitgebreide modal
- Hover tooltips met context
- Thema-introducties voor context
- Resultaten uitleg met overeenkomsten/verschillen

### 3. Delight through Details
> "Kleine animaties maken groot verschil."

**Implementatie:**
- Confetti bij quiz voltooiing
- Smooth transitions (600ms ease-out)
- Bounce effect op knoppen
- Wiggle animatie bij "belangrijk" markeren

### 4. Accessibility First
> "Iedereen moet kunnen stemmen, dus iedereen moet kunnen kiezen."

**Implementatie:**
- WCAG 2.1 AA compliant
- Keyboard navigation (Tab, Enter, ESC)
- Screen reader friendly
- High contrast colors
- Responsive vanaf 375px

## 1.4 Target Audience

### Primair: First-time Voters (18-25 jaar)
**Design implicaties:**
- Visueel aantrekkelijk (moderne kleuren, animaties)
- Educatief (uitleg bij elke stelling)
- Mobile-first (hoofdzakelijk telefoongebruik)
- Begrijpelijke taal (geen jargon)

### Secundair: Twijfelaars (alle leeftijden)
**Design implicaties:**
- Diepgaande uitleg (6 secties per stelling)
- Nuance in antwoorden (eens/oneens/neutraal/weet niet)
- Transparantie (bronnen, coverage badges)
- Vertrouwen door professionaliteit

### Tertiair: Politiek Geïnteresseerden
**Design implicaties:**
- Bronvermelding (paginanummers verkiezingsprogramma's)
- Coverage data (hoeveel standpunten per partij?)
- AI advies (holistische analyse)
- Exporteerbare resultaten

---

# 2. KLEURENPALET

## 2.1 Primaire Kleuren

### 🪸 Coral - Energie & Warmte
```css
--color-coral: #FF6B6B;
--color-coral-light: #FFA6A6;
--color-coral-dark: #E05555;
--color-coral-10: rgba(255, 107, 107, 0.1);
--color-coral-20: rgba(255, 107, 107, 0.2);
```

**Psychologie:** Vriendelijk, toegankelijk, energiek (niet agressief rood)

**Gebruik:**
- ✅ Thema headers (klimaat, economie, migratie)
- ✅ Warning badges ("Beperkt" coverage)
- ✅ Hover states belangrijke knoppen
- ✅ Accenten in icons

**Contrast:**
- Op cream (#FEF6E4): 3.8:1 ✅ (AA Large Text)
- Op white: 4.2:1 ✅ (AA)

### 🌊 Navy - Trust & Stabiliteit
```css
--color-navy: #1E3A5F;
--color-navy-light: #2E4A6F;
--color-navy-dark: #0E2A4F;
--color-navy-10: rgba(30, 58, 95, 0.1);
--color-navy-20: rgba(30, 58, 95, 0.2);
```

**Psychologie:** Betrouwbaar, professioneel, gezaghebbend

**Gebruik:**
- ✅ Main heading "Kieswijzer 2025"
- ✅ Primaire knoppen (Eens, Oneens)
- ✅ Body tekst
- ✅ Icons en borders
- ✅ Thema headers (wonen, natuur, democratie)

**Contrast:**
- Op cream (#FEF6E4): 8.2:1 ✅ (AAA)
- Op white: 9.4:1 ✅ (AAA)

### 🌿 Green - Groei & Positief
```css
--color-green: #10B981;
--color-green-light: #34D399;
--color-green-dark: #059669;
--color-green-10: rgba(16, 185, 129, 0.1);
--color-green-20: rgba(16, 185, 129, 0.2);
```

**Psychologie:** Vooruitgang, gezondheid, positieve verandering

**Gebruik:**
- ✅ "Breed" coverage badge (80%+)
- ✅ Checkmarks bij overeenkomsten
- ✅ Success states
- ✅ Thema headers (zorg, veiligheid, ouderen)
- ✅ Progress bar fill

**Contrast:**
- Op cream (#FEF6E4): 4.1:1 ✅ (AA)
- Op white: 4.8:1 ✅ (AA)

### ☀️ Yellow - Optimisme & Aandacht
```css
--color-yellow: #FDB750;
--color-yellow-light: #FDC874;
--color-yellow-dark: #F5A623;
--color-yellow-10: rgba(253, 183, 80, 0.1);
--color-yellow-20: rgba(253, 183, 80, 0.2);
```

**Psychologie:** Opvallend, optimistisch, aandachttrekkend

**Gebruik:**
- ✅ "Belangrijk" sterretje (⭐ markering)
- ✅ Info modals achtergrond accenten
- ✅ "Gemiddeld" coverage badge
- ✅ Thema headers (onderwijs, economie_belastingen)
- ✅ Highlighted text

**Contrast:**
- Op navy (#1E3A5F): 5.2:1 ✅ (AA)
- Op white: 2.8:1 ⚠️ (Large Text only)

### 🍦 Cream - Rust & Leesbaarheid
```css
--color-cream: #FEF6E4;
--color-cream-dark: #F5E8D0;
```

**Psychologie:** Kalm, vriendelijk, niet te wit (minder eye strain)

**Gebruik:**
- ✅ Body background
- ✅ Card backgrounds
- ✅ Modal backgrounds
- ✅ Tooltip backgrounds
- ✅ Section dividers

## 2.2 Thema Kleuren

13 thema's met wisselende kleuren voor visuele variatie:

```css
/* Thema Kleuren Cyclus */
--thema-klimaat: #FF6B6B;          /* Coral */
--thema-wonen: #1E3A5F;            /* Navy */
--thema-zorg: #10B981;             /* Green */
--thema-onderwijs: #FDB750;        /* Yellow */
--thema-economie: #FF6B6B;         /* Coral */
--thema-natuur: #1E3A5F;           /* Navy */
--thema-veiligheid: #10B981;       /* Green */
--thema-migratie: #FF6B6B;         /* Coral */
--thema-democratie: #1E3A5F;       /* Navy */
--thema-ouderen: #10B981;          /* Green */
--thema-economie-belastingen: #FDB750; /* Yellow */
--thema-defensie-vrede: #0891B2;   /* Cyan (special) */
```

**Patroon:** Coral → Navy → Green → Yellow → herhaal (met 1 special cyan)

**Waarom dit patroon?**
- Visuele variatie voorkomt saaiheid (111 stellingen)
- Ritme: warm → koel → warm → accent
- Herkenning: zelfde thema altijd zelfde kleur

## 2.3 Partij Kleuren

27 partijen met individuele kleuren (gebaseerd op officiële branding):

<details>
<summary>📋 Click to expand: Complete Partij Kleuren Array (27 partijen)</summary>

```css
/* Grote partijen */
--partij-vvd: #0A3D62;              /* Donkerblauw */
--partij-pvv: #1E3A8A;              /* Marine blauw */
--partij-gl-pvda: #DC2626;          /* Rood-groen */
--partij-nsc: #F59E0B;              /* Oranje */
--partij-d66: #10B981;              /* Groen */
--partij-bbb: #059669;              /* Boeren groen */
--partij-sp: #DC2626;               /* SP rood */
--partij-fvd: #7C2D12;              /* Bordeaux */
--partij-pvdd: #059669;             /* Dieren groen */
--partij-cda: #16A34A;              /* CDA groen */
--partij-sgp: #EA580C;              /* Oranje */
--partij-denk: #9333EA;             /* Paars */
--partij-cu: #3B82F6;               /* Lichtblauw */
--partij-volt: #8B5CF6;             /* Violet */
--partij-ja21: #0891B2;             /* Cyaan */
--partij-50plus: #6366F1;           /* Indigo */

/* Kleinere partijen */
--partij-vvd: #22C55E;              /* Lichtgroen */
--partij-bvnl: #DC2626;             /* Rood */
--partij-bij1: #A855F7;             /* Paars */
--partij-lp: #FCD34D;               /* Geel */
--partij-piratenpartij: #0EA5E9;    /* Lichtblauw */
--partij-fnp: #14B8A6;              /* Turquoise */
--partij-vrij-verbond: #F97316;     /* Oranje */
--partij-de-linie: #EF4444;         /* Rood */
--partij-nl-plan: #3B82F6;          /* Blauw */
--partij-ellect: #8B5CF6;           /* Paars */
--partij-pvdr: #64748B;             /* Grijs */
```

</details>

**Gebruik:**
- Partijkaart border-left (4px solid)
- Partijnaam accent color
- Hover state achtergrond (opacity 10%)

## 2.4 Semantische Kleuren

```css
/* Success */
--color-success: #10B981;
--color-success-bg: rgba(16, 185, 129, 0.1);
--color-success-border: #10B981;

/* Warning */
--color-warning: #FDB750;
--color-warning-bg: rgba(253, 183, 80, 0.1);
--color-warning-border: #FDB750;

/* Error */
--color-error: #FF6B6B;
--color-error-bg: rgba(255, 107, 107, 0.1);
--color-error-border: #FF6B6B;

/* Info */
--color-info: #1E3A5F;
--color-info-bg: rgba(30, 58, 95, 0.05);
--color-info-border: #1E3A5F;

/* Neutral */
--color-neutral: #6B7280;
--color-neutral-bg: #F9FAFB;
--color-neutral-border: #D1D5DB;
```

**Toepassing:**
- Success: "Breed" coverage badge, checkmarks
- Warning: "Gemiddeld" coverage badge, info modals
- Error: "Beperkt" coverage badge, verschillen
- Info: Tooltips, help tekst
- Neutral: "Weet ik niet" knop, disabled states

## 2.5 Contrast & Accessibility

### WCAG 2.1 AA Compliance

**Minimum contrast ratios:**
- Normal text (16px): 4.5:1
- Large text (24px+): 3:1
- UI components: 3:1

**Onze kleuren:**

| Combinatie | Ratio | Status |
|------------|-------|--------|
| Navy op Cream | 8.2:1 | ✅ AAA |
| Navy op White | 9.4:1 | ✅ AAA |
| Coral op Cream | 3.8:1 | ✅ AA (Large) |
| Green op Cream | 4.1:1 | ✅ AA |
| Yellow op Navy | 5.2:1 | ✅ AA |
| Yellow op Cream | 2.2:1 | ❌ Fail (alleen decoratief) |

### Color Blindness Testing

**Protanopia (rood-zwakte):**
- ✅ Navy vs Green blijft duidelijk onderscheid
- ✅ Coral wordt bruin, maar contrast met Cream blijft goed

**Deuteranopia (groen-zwakte):**
- ✅ Navy vs Coral blijft duidelijk
- ✅ Yellow blijft opvallend

**Tritanopia (blauw-zwakte):**
- ✅ Coral vs Green blijft onderscheidbaar
- ✅ Navy wordt groen, maar contrast blijft goed

**Design implicatie:** Gebruik NOOIT alleen kleur voor belangrijke informatie. Altijd combineren met:
- Icons (✓, ✗, i, ⚠)
- Tekst labels
- Positie/groepering

## 2.6 Kleurgebruik Rules

### DO: Goede Praktijken

```css
/* Primaire knoppen: Navy achtergrond, Cream tekst */
.btn-primary {
  background: #1E3A5F;
  color: #FEF6E4;
  border: 2px solid #1E3A5F;
}

/* Secondaire knoppen: Cream achtergrond, Navy tekst, Navy border */
.btn-secondary {
  background: #FEF6E4;
  color: #1E3A5F;
  border: 2px solid #1E3A5F;
}

/* Success state: Green achtergrond (10%), Green tekst, Green border */
.badge-success {
  background: rgba(16, 185, 129, 0.1);
  color: #10B981;
  border: 1px solid #10B981;
}

/* Thema header: Coral achtergrond, White tekst */
.thema-header {
  background: linear-gradient(135deg, #FF6B6B 0%, #E05555 100%);
  color: white;
}
```

### DON'T: Vermijd Deze Combinaties

```css
/* ❌ Te weinig contrast */
.bad-contrast {
  background: #FDB750; /* Yellow */
  color: #FEF6E4;      /* Cream - ratio 2.2:1 */
}

/* ❌ Kleur conflict */
.bad-mix {
  background: #FF6B6B; /* Coral */
  color: #10B981;      /* Green - teveel kleuren tegelijk */
}

/* ❌ Te druk */
.too-busy {
  background: linear-gradient(#FF6B6B, #10B981, #FDB750);
  /* Max 2 kleuren in gradient */
}
```

### Kleur Hiërarchie

**Prioriteit 1: Navy**
- Hoofdtekst
- Primaire knoppen
- Belangrijkste headings

**Prioriteit 2: Thema kleur (Coral/Green/Yellow/Cyan)**
- Thema headers
- Sectie accenten
- Context-specifieke elements

**Prioriteit 3: Semantische kleuren**
- Badges (success/warning/error)
- Feedback messages
- States (hover, active, disabled)

**Prioriteit 4: Cream**
- Achtergronden
- Rust punten
- Whitespace replacement

---

# 3. TYPOGRAFIE

## 3.1 Font Stack

### Primary Font: Noto Sans
```css
font-family: 'Noto Sans', system-ui, -apple-system, 'Segoe UI', sans-serif;
```

**Gebruik:** Body tekst, knoppen, labels, UI components

**Waarom Noto Sans?**
- ✅ Excellent leesbaarheid op schermen
- ✅ Breed taalondersteuning (Nederlands + diakritische tekens)
- ✅ Modern en professioneel
- ✅ Goede x-height (leesbaar bij kleine formaten)
- ✅ Google Fonts (gratis, snelle CDN)

**Beschikbare gewichten:**
- 400 (Regular) - Body tekst, labels
- 600 (Semibold) - Emphasized text, subtitles
- 700 (Bold) - Knoppen, belangrijke info

### Secondary Font: Domine
```css
font-family: 'Domine', Georgia, 'Times New Roman', serif;
```

**Gebruik:** Headings (H1-H6), partijnamen, thema titels, emphasis

**Waarom Domine?**
- ✅ Serieus maar toegankelijk (niet te formeel)
- ✅ Goed contrast met Noto Sans (serif vs sans-serif)
- ✅ Leesbaar bij grote formaten
- ✅ Autoritair maar vriendelijk
- ✅ Google Fonts

**Beschikbare gewichten:**
- 400 (Regular) - H3-H6
- 700 (Bold) - H1-H2, belangrijke headings

## 3.2 Type Scale

Gebaseerd op TailwindCSS default scale met custom overrides:

```css
/* Display - Extra Large Headlines */
.text-6xl {
  font-size: 3.75rem;    /* 60px */
  line-height: 1;
  font-family: 'Domine', serif;
  font-weight: 700;
}
/* Gebruik: "Kieswijzer 2025" hoofdtitel welkomstscherm */

.text-5xl {
  font-size: 3rem;       /* 48px */
  line-height: 1.1;
  font-family: 'Domine', serif;
  font-weight: 700;
}
/* Gebruik: Thema titels (intro schermen) */

.text-4xl {
  font-size: 2.25rem;    /* 36px */
  line-height: 1.2;
  font-family: 'Domine', serif;
  font-weight: 700;
}
/* Gebruik: "Jouw resultaten" heading */

/* Headings */
.text-3xl {
  font-size: 1.875rem;   /* 30px */
  line-height: 1.3;
  font-family: 'Domine', serif;
  font-weight: 700;
}
/* Gebruik: Partij namen in resultaten */

.text-2xl {
  font-size: 1.5rem;     /* 24px */
  line-height: 1.4;
  font-family: 'Domine', serif;
  font-weight: 400;
}
/* Gebruik: Stellingtekst (hoofdvraag) */

/* Body & UI */
.text-xl {
  font-size: 1.25rem;    /* 20px */
  line-height: 1.6;
  font-family: 'Noto Sans', sans-serif;
  font-weight: 400;
}
/* Gebruik: Lead paragraph, intro tekst */

.text-lg {
  font-size: 1.125rem;   /* 18px */
  line-height: 1.6;
  font-family: 'Noto Sans', sans-serif;
  font-weight: 600;
}
/* Gebruik: Knop tekst, emphasized body */

.text-base {
  font-size: 1rem;       /* 16px */
  line-height: 1.6;
  font-family: 'Noto Sans', sans-serif;
  font-weight: 400;
}
/* Gebruik: Body tekst, toelichting */

.text-sm {
  font-size: 0.875rem;   /* 14px */
  line-height: 1.5;
  font-family: 'Noto Sans', sans-serif;
  font-weight: 400;
}
/* Gebruik: Secondary info, timestamps, progress indicator */

.text-xs {
  font-size: 0.75rem;    /* 12px */
  line-height: 1.4;
  font-family: 'Noto Sans', sans-serif;
  font-weight: 600;
}
/* Gebruik: Badges, labels, tags */
```

### Responsive Type Scale

```css
/* Mobile (< 640px): Kleinere headings */
@media (max-width: 640px) {
  .text-6xl { font-size: 2.5rem; }   /* 40px */
  .text-5xl { font-size: 2rem; }     /* 32px */
  .text-4xl { font-size: 1.75rem; }  /* 28px */
  .text-3xl { font-size: 1.5rem; }   /* 24px */
  .text-2xl { font-size: 1.25rem; }  /* 20px */
}

/* Tablet (640px - 1024px): Default scale */

/* Desktop (> 1024px): Grotere body text voor leesbaarheid */
@media (min-width: 1024px) {
  .text-base { font-size: 1.125rem; } /* 18px */
}
```

## 3.3 Font Weights

### Noto Sans Weights

```css
/* Regular - 400 */
.font-normal {
  font-weight: 400;
}
/* Gebruik: Body tekst, labels, normale UI text */

/* Semibold - 600 */
.font-semibold {
  font-weight: 600;
}
/* Gebruik: Emphasized text, subtitles, active states */

/* Bold - 700 */
.font-bold {
  font-weight: 700;
}
/* Gebruik: Knoppen, belangrijke info, badges */
```

### Domine Weights

```css
/* Regular - 400 */
.font-normal {
  font-weight: 400;
}
/* Gebruik: H3-H6, sub-headings */

/* Bold - 700 */
.font-bold {
  font-weight: 700;
}
/* Gebruik: H1-H2, belangrijkste headings, partijnamen */
```

## 3.4 Line Heights & Spacing

### Line Height Rules

```css
/* Tight - Headings */
.leading-none { line-height: 1; }       /* Display text */
.leading-tight { line-height: 1.1; }    /* H1-H2 */
.leading-snug { line-height: 1.3; }     /* H3-H4 */

/* Normal - Body */
.leading-normal { line-height: 1.5; }   /* Small text (xs, sm) */
.leading-relaxed { line-height: 1.6; }  /* Body text (base, lg, xl) */
.leading-loose { line-height: 1.8; }    /* Long-form content */
```

**Waarom deze waarden?**
- Headings: Tighter line-height (1.0-1.3) voor impact
- Body: Relaxed line-height (1.6) voor leesbaarheid
- Long-form: Loose line-height (1.8) voor comfort bij lange teksten

### Letter Spacing

```css
/* Headings: Slightly tighter */
h1, h2, h3 {
  letter-spacing: -0.02em;
}

/* Body: Normal */
p, span, li {
  letter-spacing: 0;
}

/* Uppercase labels: Wider */
.uppercase {
  letter-spacing: 0.05em;
}
```

### Paragraph Spacing

```css
/* Standaard paragraph spacing */
p + p {
  margin-top: 1rem; /* 16px */
}

/* Headings naar paragraph */
h1 + p, h2 + p, h3 + p {
  margin-top: 1.5rem; /* 24px */
}

/* List items */
li + li {
  margin-top: 0.5rem; /* 8px */
}
```

## 3.5 Typography Rules

### DO: Goede Praktijken

```css
/* Headings: Altijd serif, medium-bold */
h1, h2, h3, h4, h5, h6 {
  font-family: 'Domine', serif;
  font-weight: 700;
  color: #1E3A5F; /* Navy */
  line-height: 1.3;
}

/* Body: Altijd sans, regular */
p, span, li, div {
  font-family: 'Noto Sans', sans-serif;
  font-weight: 400;
  color: #1E3A5F;
  line-height: 1.6;
}

/* Knoppen: Sans, semibold, uppercase */
button {
  font-family: 'Noto Sans', sans-serif;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

/* Emphasized text: Semibold, niet italic */
strong, .emphasized {
  font-weight: 600;
  color: #1E3A5F;
}
```

### DON'T: Vermijd Deze Patronen

```css
/* ❌ Italic voor emphasis (slecht voor dyslexie) */
em {
  font-style: italic; /* Gebruik font-weight: 600 instead */
}

/* ❌ ALL CAPS voor lange teksten (moeilijk leesbaar) */
.bad-caps {
  text-transform: uppercase;
  font-size: 1rem; /* Max 2-3 woorden in uppercase */
}

/* ❌ Te veel font weights tegelijk */
.too-many-weights {
  font-weight: 300; /* We gebruiken alleen 400, 600, 700 */
}

/* ❌ Te kleine body text */
.too-small {
  font-size: 0.75rem; /* Min 0.875rem (14px) voor body */
}

/* ❌ Gekleurde body tekst (vermindert leesbaarheid) */
.colored-body {
  color: #FF6B6B; /* Body altijd Navy #1E3A5F */
}
```

### Hierarchy Checklist

Voor elk scherm, check deze hiërarchie:

1. **Hoofdtitel (H1)** - text-4xl of text-5xl, Domine Bold, Navy
2. **Subtitel (H2-H3)** - text-2xl of text-3xl, Domine Regular/Bold, Navy
3. **Body tekst** - text-base, Noto Sans Regular, Navy
4. **Secondary info** - text-sm, Noto Sans Regular, Navy met 70% opacity
5. **Labels/Badges** - text-xs, Noto Sans Semibold, Thema kleur

**Maximum 3 font sizes per scherm** (exclusief badges/labels)

---

# 4. SPACING & LAYOUT

## 4.1 Spacing System

Gebaseerd op TailwindCSS 8px base unit (0.25rem = 4px):

```css
/* Spacing Scale */
--spacing-0: 0px;
--spacing-1: 0.25rem;   /* 4px */
--spacing-2: 0.5rem;    /* 8px */
--spacing-3: 0.75rem;   /* 12px */
--spacing-4: 1rem;      /* 16px */
--spacing-5: 1.25rem;   /* 20px */
--spacing-6: 1.5rem;    /* 24px */
--spacing-8: 2rem;      /* 32px */
--spacing-10: 2.5rem;   /* 40px */
--spacing-12: 3rem;     /* 48px */
--spacing-16: 4rem;     /* 64px */
--spacing-20: 5rem;     /* 80px */
--spacing-24: 6rem;     /* 96px */
--spacing-32: 8rem;     /* 128px */
```

### Common Spacing Patterns

```css
/* Component Padding */
.card-padding {
  padding: 1.5rem; /* 24px - mobile */
}
@media (min-width: 768px) {
  .card-padding {
    padding: 2rem; /* 32px - desktop */
  }
}

/* Section Spacing */
.section-spacing {
  margin-bottom: 3rem; /* 48px - mobile */
}
@media (min-width: 768px) {
  .section-spacing {
    margin-bottom: 4rem; /* 64px - desktop */
  }
}

/* Button Padding */
.btn-padding {
  padding: 0.75rem 1.5rem; /* 12px 24px */
}
.btn-padding-large {
  padding: 1rem 2rem; /* 16px 32px */
}

/* Stack Spacing (vertical) */
.stack-tight {
  gap: 0.5rem; /* 8px */
}
.stack-normal {
  gap: 1rem; /* 16px */
}
.stack-loose {
  gap: 1.5rem; /* 24px */
}

/* Inline Spacing (horizontal) */
.inline-tight {
  gap: 0.5rem; /* 8px */
}
.inline-normal {
  gap: 1rem; /* 16px */
}
```

### Spacing Rules

**DO:**
- Gebruik veelvouden van 4px (0.25rem)
- Consistent spacing binnen component groepen
- Meer ruimte op desktop dan mobile

**DON'T:**
- Geen willekeurige px values (23px, 17px, etc.)
- Niet teveel verschillende spacing values per component
- Geen negatieve margins (behalve voor specifieke alignment)

## 4.2 Grid System

### Container

```css
.container {
  width: 100%;
  margin-left: auto;
  margin-right: auto;
  padding-left: 1rem;   /* 16px */
  padding-right: 1rem;  /* 16px */
}

/* Responsive container max-widths */
@media (min-width: 640px) {  /* sm */
  .container { max-width: 640px; padding-left: 1.5rem; padding-right: 1.5rem; }
}
@media (min-width: 768px) {  /* md */
  .container { max-width: 768px; }
}
@media (min-width: 1024px) { /* lg */
  .container { max-width: 1024px; }
}
@media (min-width: 1280px) { /* xl */
  .container { max-width: 1280px; padding-left: 2rem; padding-right: 2rem; }
}
```

### 12-Column Grid

```css
.grid {
  display: grid;
  grid-template-columns: repeat(12, minmax(0, 1fr));
  gap: 1.5rem; /* 24px */
}

/* Column Spans */
.col-span-1  { grid-column: span 1 / span 1; }
.col-span-2  { grid-column: span 2 / span 2; }
.col-span-3  { grid-column: span 3 / span 3; }
.col-span-4  { grid-column: span 4 / span 4; }
.col-span-6  { grid-column: span 6 / span 6; }
.col-span-8  { grid-column: span 8 / span 8; }
.col-span-12 { grid-column: span 12 / span 12; }

/* Responsive */
@media (max-width: 768px) {
  .grid { grid-template-columns: 1fr; } /* Single column op mobile */
}
```

### Flexbox Layouts

```css
/* Horizontal Stack */
.flex-row {
  display: flex;
  flex-direction: row;
  gap: 1rem;
}

/* Vertical Stack */
.flex-col {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

/* Center Content */
.flex-center {
  display: flex;
  justify-content: center;
  align-items: center;
}

/* Space Between */
.flex-between {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

## 4.3 Responsive Breakpoints

```css
/* Mobile First Approach */

/* Extra Small (default) */
/* 0px - 639px */
/* Single column, touch-optimized */

/* Small (sm) */
@media (min-width: 640px) {
  /* Tablets portrait */
}

/* Medium (md) */
@media (min-width: 768px) {
  /* Tablets landscape */
}

/* Large (lg) */
@media (min-width: 1024px) {
  /* Desktop */
}

/* Extra Large (xl) */
@media (min-width: 1280px) {
  /* Large desktop */
}
```

### Breakpoint Strategy

**Mobile (< 640px):**
- Single column layout
- Full-width buttons
- Stacked navigation
- Smaller headings (text-4xl → text-2xl)
- Touch-optimized (48×48px min touch target)

**Tablet (640px - 1024px):**
- 2-3 column grid (resultaten)
- Horizontal button groups
- Larger text (text-base → text-lg)
- Hover states enabled

**Desktop (> 1024px):**
- Full 12-column grid
- Side-by-side layouts (modal content)
- Max container width 1024px (leesbaarheid)
- Larger spacing (padding, margins)

## 4.4 Container Widths

### Max Widths per Component

```css
/* Welkomstscherm */
.welcome-container {
  max-width: 64rem; /* 1024px */
}

/* Stelling kaart */
.stelling-card {
  max-width: 48rem; /* 768px - optimal reading width */
}

/* Modal content */
.modal-content {
  max-width: 56rem; /* 896px */
}

/* Resultaten grid */
.results-container {
  max-width: 80rem; /* 1280px - allows 3 columns */
}

/* Full width (thema intro) */
.full-width {
  max-width: 100%;
}
```

**Waarom deze waarden?**
- 768px = optimal reading width (60-75 characters per line)
- 1024px = comfortable container voor meeste schermen
- 1280px = breed genoeg voor 3-column grid met spacing

---

# 5. UI COMPONENTS

## 5.1 Buttons

### Primary Button

```html
<button class="btn-primary">
  Eens
</button>
```

```css
.btn-primary {
  /* Layout */
  padding: 1rem 2rem; /* 16px 32px */
  min-height: 48px;
  min-width: 120px;

  /* Typography */
  font-family: 'Noto Sans', sans-serif;
  font-size: 1.125rem; /* 18px */
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.05em;

  /* Colors */
  background: #1E3A5F; /* Navy */
  color: #FEF6E4; /* Cream */
  border: 2px solid #1E3A5F;

  /* Effects */
  border-radius: 0.5rem; /* 8px */
  cursor: pointer;
  transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.btn-primary:hover {
  transform: scale(1.05);
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

.btn-primary:active {
  transform: scale(0.95);
}

.btn-primary:focus {
  outline: 2px solid #FF6B6B;
  outline-offset: 2px;
}
```

### Secondary Button

```css
.btn-secondary {
  /* Layout */
  padding: 1rem 2rem;
  min-height: 48px;

  /* Colors */
  background: #FEF6E4; /* Cream */
  color: #1E3A5F; /* Navy */
  border: 2px solid #1E3A5F;

  /* Rest same as primary */
}

.btn-secondary:hover {
  background: #F5E8D0; /* Cream-dark */
}
```

### Neutral Button (Weet ik niet / Neutraal)

```css
.btn-neutral {
  /* Colors */
  background: white;
  color: #6B7280; /* Gray-500 */
  border: 2px solid #D1D5DB; /* Gray-300 */
}

.btn-neutral:hover {
  background: #F9FAFB; /* Gray-50 */
  color: #1E3A5F; /* Navy */
  border-color: #1E3A5F;
}
```

### Icon Button

```css
.btn-icon {
  /* Layout */
  padding: 0.75rem;
  min-height: 48px;
  min-width: 48px;

  /* Round */
  border-radius: 9999px; /* fully rounded */

  /* Colors */
  background: transparent;
  color: #1E3A5F;
  border: none;
}

.btn-icon:hover {
  background: rgba(30, 58, 95, 0.1);
}
```

### Button States

```css
/* Disabled */
.btn:disabled {
  opacity: 0.5;
  cursor: not-allowed;
  pointer-events: none;
}

/* Loading */
.btn-loading {
  position: relative;
  color: transparent;
}
.btn-loading::after {
  content: '';
  position: absolute;
  width: 16px;
  height: 16px;
  border: 2px solid currentColor;
  border-radius: 50%;
  border-top-color: transparent;
  animation: spin 0.6s linear infinite;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}
```

### Button Groups

```html
<div class="btn-group">
  <button class="btn-primary">Eens</button>
  <button class="btn-primary">Oneens</button>
  <button class="btn-neutral">Neutraal</button>
  <button class="btn-neutral">Weet ik niet</button>
</div>
```

```css
.btn-group {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1rem;
}

@media (min-width: 768px) {
  .btn-group {
    grid-template-columns: repeat(4, 1fr);
  }
}
```

## 5.2 Cards

### Stelling Card

```html
<div class="card-stelling">
  <div class="card-header">
    <span class="card-badge">Klimaat & Energie</span>
    <button class="btn-icon"><i class="bi bi-info-circle"></i></button>
  </div>
  <div class="card-body">
    <h2 class="card-title">Nederland moet in 2040 volledig klimaatneutraal zijn</h2>
    <p class="card-description">Over versnelling klimaatdoelen en gevolgen voor industrie</p>
  </div>
  <div class="card-footer">
    <!-- Buttons -->
  </div>
</div>
```

```css
.card-stelling {
  /* Layout */
  background: white;
  border-radius: 1rem; /* 16px */
  padding: 2rem;
  max-width: 48rem;
  margin: 0 auto;

  /* Shadow */
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
              0 2px 4px -1px rgba(0, 0, 0, 0.06);

  /* Animation */
  animation: fadeIn 0.6s ease-out;
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1.5rem;
}

.card-badge {
  display: inline-block;
  padding: 0.5rem 1rem;
  background: rgba(255, 107, 107, 0.1);
  color: #FF6B6B;
  border-radius: 9999px;
  font-size: 0.875rem;
  font-weight: 600;
}

.card-title {
  font-family: 'Domine', serif;
  font-size: 1.5rem;
  font-weight: 400;
  color: #1E3A5F;
  line-height: 1.4;
  margin-bottom: 1rem;
}

.card-description {
  font-family: 'Noto Sans', sans-serif;
  font-size: 1rem;
  color: rgba(30, 58, 95, 0.7);
  line-height: 1.6;
}

.card-footer {
  margin-top: 2rem;
  padding-top: 2rem;
  border-top: 1px solid #F3F4F6;
}
```

### Partij Card (Resultaten)

```css
.card-partij {
  /* Layout */
  background: white;
  border-radius: 0.5rem;
  padding: 1.5rem;
  border-left: 4px solid var(--partij-kleur);

  /* Shadow */
  box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.card-partij:hover {
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  transform: translateY(-2px);
}

.card-partij-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 1rem;
}

.card-partij-naam {
  font-family: 'Domine', serif;
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--partij-kleur);
}

.card-partij-score {
  font-size: 2rem;
  font-weight: 700;
  color: #1E3A5F;
}

.card-partij-percentage {
  font-size: 0.875rem;
  color: rgba(30, 58, 95, 0.6);
  text-align: right;
}
```

## 5.3 Modals

### Modal Structure

```html
<div class="modal-backdrop">
  <div class="modal-content">
    <div class="modal-header">
      <h2 class="modal-title">Uitleg bij stelling</h2>
      <button class="modal-close" aria-label="Sluit modal">
        <i class="bi bi-x-lg"></i>
      </button>
    </div>
    <div class="modal-body scrollbar-custom">
      <!-- Content -->
    </div>
    <div class="modal-footer">
      <button class="btn-secondary">Sluiten</button>
    </div>
  </div>
</div>
```

```css
/* Backdrop */
.modal-backdrop {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 50;
  padding: 1rem;

  /* Animation */
  animation: backdropFadeIn 0.3s ease-out;
}

@keyframes backdropFadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

/* Content */
.modal-content {
  background: white;
  border-radius: 1rem;
  max-width: 56rem; /* 896px */
  width: 100%;
  max-height: 90vh;
  display: flex;
  flex-direction: column;

  /* Animation */
  animation: modalOpen 0.35s cubic-bezier(0.34, 1.56, 0.64, 1);
}

@keyframes modalOpen {
  from {
    opacity: 0;
    transform: scale(0.9) translateY(20px);
  }
  to {
    opacity: 1;
    transform: scale(1) translateY(0);
  }
}

/* Header */
.modal-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 2rem;
  border-bottom: 1px solid #F3F4F6;
}

.modal-title {
  font-family: 'Domine', serif;
  font-size: 1.875rem;
  font-weight: 700;
  color: #1E3A5F;
}

.modal-close {
  padding: 0.5rem;
  background: transparent;
  border: none;
  color: #6B7280;
  cursor: pointer;
  border-radius: 0.375rem;
  transition: all 0.2s;
}

.modal-close:hover {
  background: #F3F4F6;
  color: #1E3A5F;
}

/* Sticky close button (blijft zichtbaar bij scrollen) */
.modal-close-btn {
  position: sticky;
  top: 1rem;
  z-index: 100;
  /* Float boven scrollable content */
}

/* Gebruik in modal header */
.modal-header .modal-close {
  /* Sticky binnen header */
  position: sticky;
  top: 0;
}


/* Body */
.modal-body {
  padding: 2rem;
  overflow-y: auto;
  flex: 1;
}

/* Footer */
.modal-footer {
  padding: 1.5rem 2rem;
  border-top: 1px solid #F3F4F6;
  display: flex;
  justify-content: flex-end;
  gap: 1rem;
}
```

### Custom Scrollbar Variants

**Modal Body Scrollbar (breed, opvallend):**

```css
.scrollbar-custom::-webkit-scrollbar {
  width: 10px;
}

.scrollbar-custom::-webkit-scrollbar-track {
  background: #FEF6E4; /* Cream */
  border-radius: 10px;
}

.scrollbar-custom::-webkit-scrollbar-thumb {
  background: #FDB750; /* Yellow */
  border-radius: 10px;
}

.scrollbar-custom::-webkit-scrollbar-thumb:hover {
  background: #FF6B6B; /* Coral */
}
```

**Tooltip Scrollbar (dun, subtiel):**

```css
/* Voor tooltip thema lijst (minder opvallend) */
.scrollbar-thin::-webkit-scrollbar {
  width: 6px; /* Smaller width */
}

.scrollbar-thin::-webkit-scrollbar-track {
  background: #FEF6E4; /* Cream */
  border-radius: 3px;
}

.scrollbar-thin::-webkit-scrollbar-thumb {
  background: #1E3A5F; /* Navy (anders dan modal!) */
  border-radius: 3px;
}

.scrollbar-thin::-webkit-scrollbar-thumb:hover {
  background: #10B981; /* Green */
}
```

**Gebruik:**
- `.scrollbar-custom` → Modals (breed, yellow/coral)
- `.scrollbar-thin` → Tooltips, dropdowns (dun, navy/green)

**Browser support:**
- ✅ Chrome, Edge, Safari (webkit)
- ❌ Firefox (gebruikt eigen scrollbar styling)
- Fallback: Default browser scrollbar

## 5.4 Tooltips

### Coverage Tooltip

```html
<div class="coverage-indicator">
  <span class="badge-coverage-breed">Breed (92%)</span>
  <div class="coverage-tooltip">
    <!-- Content -->
  </div>
</div>
```

```css
.coverage-indicator {
  position: relative;
  display: inline-block;
}

.coverage-tooltip {
  /* Hidden by default */
  display: none;

  /* Positioning */
  position: absolute;
  bottom: calc(100% + 0.5rem);
  left: 50%;
  transform: translateX(-50%);
  z-index: 10;

  /* Styling */
  background: white;
  border: 1px solid #E5E7EB;
  border-radius: 0.5rem;
  padding: 1rem;
  min-width: 250px;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);

  /* Animation */
  animation: tooltipFadeIn 0.2s ease-out;
}

@keyframes tooltipFadeIn {
  from {
    opacity: 0;
    transform: translateX(-50%) translateY(-5px);
  }
  to {
    opacity: 1;
    transform: translateX(-50%) translateY(0);
  }
}

/* Show on hover (desktop) */
@media (min-width: 1024px) {
  .coverage-indicator:hover .coverage-tooltip {
    display: block;
  }
}

/* Show on click (mobile) */
.coverage-indicator.active .coverage-tooltip {
  display: block;
}

/* Tooltip arrow */
.coverage-tooltip::after {
  content: '';
  position: absolute;
  top: 100%;
  left: 50%;
  transform: translateX(-50%);
  border: 6px solid transparent;
  border-top-color: white;
}
```

### Partij Info Tooltip

```css
.party-info-tooltip {
  /* Same base as coverage-tooltip */
  /* ... */

  /* Custom width for party info */
  min-width: 300px;
  max-width: 400px;
}

.tooltip-section {
  margin-bottom: 1rem;
}

.tooltip-section:last-child {
  margin-bottom: 0;
}

.tooltip-label {
  font-weight: 600;
  font-size: 0.75rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: #6B7280;
  margin-bottom: 0.5rem;
}

.tooltip-value {
  font-size: 0.875rem;
  color: #1E3A5F;
  line-height: 1.5;
}
```

## 5.5 Badges

### Coverage Badges

```css
/* Breed (80%+) */
.badge-coverage-breed {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.5rem 1rem;
  background: rgba(16, 185, 129, 0.1);
  color: #10B981;
  border: 1px solid #10B981;
  border-radius: 9999px;
  font-size: 0.75rem;
  font-weight: 600;
  cursor: help;
}

/* Gemiddeld (50-79%) */
.badge-coverage-gemiddeld {
  background: rgba(253, 183, 80, 0.1);
  color: #FDB750;
  border-color: #FDB750;
  /* Rest same */
}

/* Beperkt (<50%) */
.badge-coverage-beperkt {
  background: rgba(255, 107, 107, 0.1);
  color: #FF6B6B;
  border-color: #FF6B6B;
  /* Rest same */
}
```

### Thema Badge

```css
.badge-thema {
  display: inline-block;
  padding: 0.5rem 1rem;
  background: rgba(255, 107, 107, 0.1);
  color: #FF6B6B;
  border-radius: 9999px;
  font-size: 0.875rem;
  font-weight: 600;
}

/* Dynamic theming */
.badge-thema[data-thema="klimaat"] {
  background: rgba(255, 107, 107, 0.1);
  color: #FF6B6B;
}

.badge-thema[data-thema="wonen"] {
  background: rgba(30, 58, 95, 0.1);
  color: #1E3A5F;
}

/* etc for all 13 themes */
```

## 5.6 Progress Indicators

### Progress Bar

```html
<div class="progress-container">
  <div class="progress-label">
    <span>Voortgang</span>
    <span>23 van 111</span>
  </div>
  <div class="progress-bar">
    <div class="progress-bar-fill" style="width: 21%"></div>
  </div>
</div>
```

```css
.progress-container {
  margin-bottom: 1.5rem;
}

.progress-label {
  display: flex;
  justify-content: space-between;
  margin-bottom: 0.5rem;
  font-size: 0.875rem;
  color: rgba(30, 58, 95, 0.7);
  font-weight: 600;
}

.progress-bar {
  height: 8px;
  background: #E5E7EB;
  border-radius: 9999px;
  overflow: hidden;
}

.progress-bar-fill {
  height: 100%;
  background: linear-gradient(90deg, #10B981 0%, #059669 100%);
  border-radius: 9999px;
  transition: width 0.7s ease-out;
}
```

### Circular Progress (Percentage)

```css
.progress-circle {
  position: relative;
  width: 120px;
  height: 120px;
}

.progress-circle-svg {
  transform: rotate(-90deg);
}

.progress-circle-bg {
  fill: none;
  stroke: #E5E7EB;
  stroke-width: 8;
}

.progress-circle-fill {
  fill: none;
  stroke: #10B981;
  stroke-width: 8;
  stroke-linecap: round;
  transition: stroke-dashoffset 1s ease-out;
}

.progress-circle-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 2rem;
  font-weight: 700;
  color: #1E3A5F;
}
```

## 5.7 Icons

### Icon Library: Bootstrap Icons 1.11.3

```html
<!-- CDN -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.css">

<!-- Usage -->
<i class="bi bi-tree"></i>          <!-- Thema icon -->
<i class="bi bi-info-circle"></i>   <!-- Info button -->
<i class="bi bi-check-lg"></i>      <!-- Success -->
<i class="bi bi-x-lg"></i>          <!-- Close -->
<i class="bi bi-chevron-down"></i>  <!-- Dropdown -->
<i class="bi bi-star-fill"></i>     <!-- Belangrijk -->
```

### Icon Sizes

```css
.icon-sm {
  font-size: 1rem; /* 16px */
}

.icon-md {
  font-size: 1.5rem; /* 24px */
}

.icon-lg {
  font-size: 2rem; /* 32px */
}

.icon-xl {
  font-size: 3rem; /* 48px */
}
```

### Thema Icons

| Thema | Icon Class | Visual |
|-------|------------|--------|
| Klimaat & Energie | `bi-tree` | 🌳 |
| Wonen | `bi-house-door` | 🏠 |
| Zorg | `bi-heart-pulse` | ❤️‍🩹 |
| Onderwijs | `bi-book` | 📚 |
| Economie | `bi-currency-euro` | € |
| Natuur | `bi-flower3` | 🌸 |
| Veiligheid | `bi-shield-check` | 🛡️ |
| Migratie | `bi-globe` | 🌍 |
| Democratie | `bi-bank` | 🏛️ |
| Ouderen | `bi-person-hearts` | 👥❤️ |
| Economie & Belastingen | `bi-calculator` | 🧮 |
| Defensie & Vrede | `bi-flag` | 🚩 |

---

# 6. ANIMATIONS & INTERACTIONS

## 6.1 Timing & Easing

### Duration Values

```css
/* Fast - Micro-interactions */
--duration-fast: 150ms;
/* Gebruik: Hover states, button ripples */

/* Normal - UI transitions */
--duration-normal: 300ms;
/* Gebruik: Modal open/close, tooltip fade */

/* Slow - Page transitions */
--duration-slow: 600ms;
/* Gebruik: Scherm transitions, fade-ins */

/* Extra Slow - Emphasis */
--duration-extra-slow: 1000ms;
/* Gebruik: Progress bar fills, confetti */
```

### Easing Functions

```css
/* Ease Out - Decelerate (most common) */
--ease-out: cubic-bezier(0.33, 1, 0.68, 1);
/* Gebruik: Fade-ins, slide-ins, modal opens */

/* Ease In - Accelerate */
--ease-in: cubic-bezier(0.32, 0, 0.67, 0);
/* Gebruik: Modal closes, fade-outs */

/* Ease In-Out - Smooth */
--ease-in-out: cubic-bezier(0.65, 0, 0.35, 1);
/* Gebruik: Hover states, toggle switches */

/* Bounce - Playful */
--ease-bounce: cubic-bezier(0.34, 1.56, 0.64, 1);
/* Gebruik: Button clicks, "belangrijk" markering */
```

**Regel:** Gebruik Ease Out als default (voelt sneller, responsiever)

## 6.2 Keyframe Animations

### Fade In

```css
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fadeIn 0.6s ease-out;
}
```

**Gebruik:** Nieuwe schermen (stelling, resultaten)

### Bounce

```css
@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

.animate-bounce {
  animation: bounce 0.5s ease-out;
}
```

**Gebruik:** Button click feedback

### Wiggle

```css
@keyframes wiggle {
  0%, 100% {
    transform: rotate(0deg);
  }
  25% {
    transform: rotate(-5deg);
  }
  75% {
    transform: rotate(5deg);
  }
}

.animate-wiggle {
  animation: wiggle 0.5s ease-in-out;
}
```

**Gebruik:** "Belangrijk" sterretje (⭐) bij markeren

### Pulse Ring

```css
@keyframes pulse-ring {
  0% {
    transform: scale(0.95);
    box-shadow: 0 0 0 0 rgba(255, 107, 107, 0.7);
  }
  70% {
    transform: scale(1);
    box-shadow: 0 0 0 10px rgba(255, 107, 107, 0);
  }
  100% {
    transform: scale(0.95);
    box-shadow: 0 0 0 0 rgba(255, 107, 107, 0);
  }
}

.animate-pulse-ring {
  animation: pulse-ring 2s cubic-bezier(0.455, 0.03, 0.515, 0.955) infinite;
}
```

**Gebruik:** Attention grabbers (nieuwe feature indicators)

### Slide Down (Accordion)

```css
@keyframes slideDown {
  from {
    opacity: 0;
    transform: translateY(-20px);
    max-height: 0;
  }
  to {
    opacity: 1;
    transform: translateY(0);
    max-height: 5000px;
  }
}

.animate-slide-down {
  animation: slideDown 0.5s cubic-bezier(0.34, 1.56, 0.64, 1);
}
```

**Gebruik:** Overeenkomsten/verschillen uitklappen

### Modal Open/Close

```css
@keyframes modalOpen {
  0% {
    opacity: 0;
    transform: scale(0.9) translateY(20px);
  }
  100% {
    opacity: 1;
    transform: scale(1) translateY(0);
  }
}

@keyframes modalClose {
  0% {
    opacity: 1;
    transform: scale(1) translateY(0);
  }
  100% {
    opacity: 0;
    transform: scale(0.95) translateY(10px);
  }
}

.modal-content {
  animation: modalOpen 0.35s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.modal-close {
  animation: modalClose 0.25s cubic-bezier(0.55, 0.055, 0.675, 0.19);
}
```

### Staggered Fade In (List Items)

```css
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.overeenkomst-item {
  animation: fadeInUp 0.5s ease-out backwards;
}

/* Stagger delays */
.overeenkomst-item:nth-child(1) { animation-delay: 0.1s; }
.overeenkomst-item:nth-child(2) { animation-delay: 0.2s; }
.overeenkomst-item:nth-child(3) { animation-delay: 0.3s; }
.overeenkomst-item:nth-child(4) { animation-delay: 0.4s; }
.overeenkomst-item:nth-child(5) { animation-delay: 0.5s; }
.overeenkomst-item:nth-child(n+6) { animation-delay: 0.6s; }
```

**Gebruik:** Resultatenlijst (partijen overeenkomsten)

## 6.3 Hover States

### Button Hover

```css
.btn-hover-grow {
  transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.btn-hover-grow:hover {
  transform: scale(1.05);
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

.btn-hover-grow:active {
  transform: scale(0.95);
}
```

### Card Hover

```css
.card-hover {
  transition: all 0.3s ease;
}

.card-hover:hover {
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
  transform: translateY(-2px);
}
```

### Link Hover

```css
.link-underline {
  position: relative;
  text-decoration: none;
  color: #1E3A5F;
}

.link-underline::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 0;
  height: 2px;
  background: #FF6B6B;
  transition: width 0.3s ease-out;
}

.link-underline:hover::after {
  width: 100%;
}
```

### Icon Button Hover

```css
.icon-btn-hover {
  transition: all 0.2s ease;
}

.icon-btn-hover:hover {
  background: rgba(30, 58, 95, 0.1);
  transform: rotate(15deg);
}
```

## 6.4 Focus States

### Keyboard Focus (Accessibility)

```css
/* All interactive elements */
button:focus,
a:focus,
input:focus,
select:focus {
  outline: 2px solid #FF6B6B; /* Coral */
  outline-offset: 2px;
  border-radius: 0.25rem;
}

/* Remove default outline */
*:focus {
  outline: none;
}

/* Focus-visible (only keyboard, not mouse) */
button:focus-visible {
  outline: 2px solid #FF6B6B;
  outline-offset: 2px;
}
```

### Focus Ring Animation

```css
@keyframes focusRing {
  0% {
    box-shadow: 0 0 0 0 rgba(255, 107, 107, 0.5);
  }
  100% {
    box-shadow: 0 0 0 4px rgba(255, 107, 107, 0);
  }
}

.btn:focus-visible {
  animation: focusRing 0.6s ease-out;
}
```

## 6.5 Transition Rules

### DO: Goede Praktijken

```css
/* Smooth transitions voor interactieve elementen */
button, a, .card {
  transition: all 0.3s ease;
}

/* Specifieke properties voor performance */
.optimized-transition {
  transition: transform 0.3s ease,
              opacity 0.3s ease;
  /* GPU-accelerated properties: transform, opacity */
}

/* Longer duration voor grotere bewegingen */
.modal {
  transition: transform 0.5s cubic-bezier(0.34, 1.56, 0.64, 1),
              opacity 0.5s ease-out;
}
```

### DON'T: Vermijd Deze Patronen

```css
/* ❌ Teveel animaties tegelijk */
.too-many-animations {
  animation: fadeIn 0.6s, bounce 0.5s, wiggle 0.5s;
  /* Max 1-2 animaties per element */
}

/* ❌ Te lange durations (frustratie) */
.too-slow {
  transition: all 2s ease; /* Max 1s, meestal 300-600ms */
}

/* ❌ Animaties op layout properties (laggy) */
.laggy {
  transition: width 0.3s, height 0.3s, margin 0.3s;
  /* Gebruik transform: scale() instead */
}

/* ❌ Animations op initial load (irritant) */
body {
  animation: fadeIn 2s; /* Don't animate on load */
}
```

### Performance Checklist

✅ **DO animate:** `transform`, `opacity`
⚠️ **AVOID animating:** `width`, `height`, `margin`, `padding`, `top`, `left`

**Waarom?**
- `transform` & `opacity` worden gehandled door GPU (60fps)
- Layout properties forceren browser reflow (laggy, <30fps)

---

# 7. RESPONSIVE DESIGN

## 7.1 Mobile First Approach

### Filosofie
Start met mobile design, voeg toe voor grotere schermen:

```css
/* Base styles (mobile) */
.container {
  padding: 1rem;
}

/* Add complexity for larger screens */
@media (min-width: 768px) {
  .container {
    padding: 2rem;
  }
}
```

**Waarom Mobile First?**
- 65%+ gebruikers op mobiel (verkiezingen = veel jonge kiezers)
- Forceert focus op essentials (clarity)
- Progressieve enhancement (werkt altijd, verbetert indien mogelijk)

## 7.2 Breakpoint Strategy

### Breakpoints

```css
/* xs - Mobile (default) */
/* 0px - 639px */
/* Design for: iPhone SE (375px), iPhone 12 (390px) */

/* sm - Large Mobile / Tablet Portrait */
@media (min-width: 640px) {
  /* Design for: iPad Mini portrait (768px) */
}

/* md - Tablet Landscape */
@media (min-width: 768px) {
  /* Design for: iPad portrait (768px), iPad landscape (1024px) */
}

/* lg - Desktop */
@media (min-width: 1024px) {
  /* Design for: Laptop (1280px), Desktop (1920px) */
}

/* xl - Large Desktop */
@media (min-width: 1280px) {
  /* Design for: Desktop (1920px+) */
}
```

### Responsive Patterns

**Stelling Interface:**

```css
/* Mobile: Stack alles verticaal */
.stelling-container {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.stelling-buttons {
  display: grid;
  grid-template-columns: repeat(2, 1fr); /* 2x2 grid */
  gap: 1rem;
}

/* Tablet: Grotere knoppen, meer ruimte */
@media (min-width: 768px) {
  .stelling-container {
    gap: 2rem;
  }

  .stelling-buttons {
    grid-template-columns: repeat(4, 1fr); /* 1x4 grid */
  }
}

/* Desktop: Centered met max-width */
@media (min-width: 1024px) {
  .stelling-container {
    max-width: 48rem;
    margin: 0 auto;
  }
}
```

**Resultaten Grid:**

```css
/* Mobile: 1 kolom */
.results-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}

/* Tablet: 2 kolommen */
@media (min-width: 768px) {
  .results-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
  }
}

/* Desktop: 3 kolommen */
@media (min-width: 1024px) {
  .results-grid {
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
  }
}
```

## 7.3 Touch Targets

### Minimum Sizes

```css
/* All interactive elements: 48x48px minimum */
button, a, input, select {
  min-height: 48px;
  min-width: 48px;
  padding: 0.75rem 1.5rem;
}

/* Small buttons: 44x44px (Apple HIG minimum) */
.btn-small {
  min-height: 44px;
  min-width: 44px;
}

/* Icon buttons: 48x48px met padding */
.icon-button {
  width: 48px;
  height: 48px;
  padding: 0.75rem;
}
```

**Waarom 48px?**
- Google Material Design guideline: 48dp
- Apple HIG: 44pt
- Average adult fingertip: 10mm (≈ 38px)
- 48px geeft margin of error

### Spacing Between Touch Targets

```css
/* Minimum 8px spacing tussen knoppen */
.button-group {
  display: flex;
  gap: 0.5rem; /* 8px */
}

/* Recommended: 16px spacing */
.button-group-comfortable {
  display: flex;
  gap: 1rem; /* 16px */
}
```

## 7.4 Responsive Typography

### Fluid Type Scale

```css
/* H1: 40px mobile → 60px desktop */
h1 {
  font-size: clamp(2.5rem, 5vw, 3.75rem);
}

/* H2: 32px mobile → 48px desktop */
h2 {
  font-size: clamp(2rem, 4vw, 3rem);
}

/* Body: 16px mobile → 18px desktop */
body {
  font-size: clamp(1rem, 1.5vw, 1.125rem);
}
```

**Alternatief: Breakpoint-based**

```css
/* Mobile */
h1 { font-size: 2.5rem; }
p { font-size: 1rem; }

/* Desktop */
@media (min-width: 1024px) {
  h1 { font-size: 3.75rem; }
  p { font-size: 1.125rem; }
}
```

### Responsive Line Length

```css
/* Optimal reading: 60-75 characters per line */
.text-content {
  max-width: 65ch; /* 65 characters */
}

/* Alternative: Fixed max-width */
.text-content {
  max-width: 48rem; /* 768px */
}
```

---

# 8. ACCESSIBILITY

## 8.1 WCAG Guidelines

### WCAG 2.1 AA Compliance

**Target:** WCAG 2.1 Level AA (wettelijk vereist in NL vanaf 2025)

#### 1. Perceivable

**1.1 Text Alternatives**
```html
<!-- Alt text voor images -->
<img src="logo.png" alt="Stemwijzer 2025 logo">

<!-- ARIA labels voor icon buttons -->
<button aria-label="Sluit modal">
  <i class="bi bi-x-lg"></i>
</button>
```

**1.3 Adaptable**
```html
<!-- Semantic HTML -->
<nav>...</nav>
<main>...</main>
<article>...</article>
<aside>...</aside>

<!-- Headings hierarchy -->
<h1>Kieswijzer 2025</h1>
  <h2>Resultaten</h2>
    <h3>Partijnaam</h3>
```

**1.4 Distinguishable**
```css
/* Contrast ratio minimum 4.5:1 */
color: #1E3A5F; /* Navy */
background: #FEF6E4; /* Cream */
/* Ratio: 8.2:1 ✅ */

/* Focus indicators */
:focus-visible {
  outline: 2px solid #FF6B6B;
  outline-offset: 2px;
}
```

#### 2. Operable

**2.1 Keyboard Accessible**
```javascript
// All functionality available via keyboard
// Tab, Enter, ESC, Arrow keys

// Example: Modal keyboard handling
document.addEventListener('keydown', (e) => {
  if (e.key === 'Escape') closeModal();
  if (e.key === 'Tab') trapFocus(e);
});
```

**2.4 Navigable**
```html
<!-- Skip link (eerste tab stop) -->
<a href="#main-content" class="skip-link">
  Spring naar hoofdinhoud
</a>

<!-- Page title -->
<title>Stelling 23 van 111 - Klimaat - Stemwijzer 2025</title>

<!-- Focus management -->
<div role="dialog" aria-labelledby="modal-title" aria-modal="true">
  <h2 id="modal-title">Uitleg bij stelling</h2>
</div>
```

#### 3. Understandable

**3.1 Readable**
```html
<!-- Language -->
<html lang="nl">

<!-- Clear labels -->
<button>Eens</button>  <!-- ✅ Clear -->
<button>👍</button>    <!-- ❌ Emoji only -->
```

**3.2 Predictable**
```html
<!-- Consistent navigation -->
<button class="btn-terug">← Terug</button>
<!-- Always bottom-left -->

<!-- Focus doesn't change context -->
<!-- NO auto-submit on select change -->
```

**3.3 Input Assistance**
```html
<!-- Error messages -->
<div role="alert" aria-live="polite">
  Vul alle verplichte velden in
</div>

<!-- Labels -->
<label for="leeftijd">Leeftijd</label>
<input id="leeftijd" type="number" required>
```

#### 4. Robust

**4.1 Compatible**
```html
<!-- Valid HTML5 -->
<!DOCTYPE html>
<html lang="nl">
  <head>
    <meta charset="UTF-8">
    ...
  </head>
</html>

<!-- ARIA roles -->
<div role="progressbar" aria-valuenow="23" aria-valuemin="0" aria-valuemax="111">
  Stelling 23 van 111
</div>
```

## 8.2 Keyboard Navigation

### Focus Order

```
1. Skip link (verborgen, visible on focus)
2. Main navigation
3. Primary content (stelling tekst, knoppen)
4. Secondary content (info button, terug button)
5. Footer links
```

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Tab` | Volgende element |
| `Shift + Tab` | Vorige element |
| `Enter` / `Space` | Activeer button/link |
| `Esc` | Sluit modal/tooltip |
| `Arrow Up/Down` | Navigeer in lijst |
| `Home` / `End` | Eerste/laatste item |

### Focus Trap (Modals)

```javascript
function trapFocus(e) {
  const modal = document.querySelector('[role="dialog"]');
  const focusableElements = modal.querySelectorAll(
    'button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])'
  );
  const firstElement = focusableElements[0];
  const lastElement = focusableElements[focusableElements.length - 1];

  if (e.key === 'Tab') {
    if (e.shiftKey && document.activeElement === firstElement) {
      e.preventDefault();
      lastElement.focus();
    } else if (!e.shiftKey && document.activeElement === lastElement) {
      e.preventDefault();
      firstElement.focus();
    }
  }
}
```

## 8.3 Screen Readers

### ARIA Labels

```html
<!-- Button zonder visible text -->
<button aria-label="Meer informatie over deze stelling">
  <i class="bi bi-info-circle"></i>
</button>

<!-- Link met context -->
<a href="/hoe-het-werkt" aria-label="Lees meer over hoe de Stemwijzer werkt">
  Meer info
</a>

<!-- Progress indicator -->
<div role="progressbar"
     aria-valuenow="23"
     aria-valuemin="0"
     aria-valuemax="111"
     aria-label="Voortgang: stelling 23 van 111">
  <div class="progress-bar-fill" style="width: 21%"></div>
</div>
```

### ARIA Live Regions

```html
<!-- Announcements (polite - wacht tot screen reader klaar is) -->
<div role="status" aria-live="polite" aria-atomic="true">
  Antwoord opgeslagen
</div>

<!-- Errors (assertive - interrupt direct) -->
<div role="alert" aria-live="assertive">
  Vul alle verplichte velden in
</div>
```

### Hidden Content

```css
/* Visually hidden maar screen reader accessible */
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border-width: 0;
}

/* Hidden for everyone */
.hidden {
  display: none;
}

/* ARIA hidden (visible maar ignored by screen readers) */
<span aria-hidden="true">🌳</span>
<span class="sr-only">Klimaat en Energie</span>
```

## 8.4 Color Contrast

### Contrast Ratio Testing

**Tool:** WebAIM Contrast Checker (https://webaim.org/resources/contrastchecker/)

**Onze kleuren:**

| Foreground | Background | Ratio | WCAG Level |
|------------|------------|-------|------------|
| Navy #1E3A5F | Cream #FEF6E4 | 8.2:1 | AAA ✅ |
| Navy #1E3A5F | White #FFFFFF | 9.4:1 | AAA ✅ |
| Coral #FF6B6B | Cream #FEF6E4 | 3.8:1 | AA Large ✅ |
| Green #10B981 | Cream #FEF6E4 | 4.1:1 | AA ✅ |
| Yellow #FDB750 | Navy #1E3A5F | 5.2:1 | AA ✅ |
| Yellow #FDB750 | Cream #FEF6E4 | 2.2:1 | Fail ❌ |

**Actie:** Yellow alleen gebruiken op Navy achtergrond of als decoratie (badges met border)

### Non-Color Indicators

```html
<!-- ❌ Alleen kleur -->
<span style="color: green;">Breed</span>

<!-- ✅ Kleur + Icon + Text -->
<span class="badge-coverage-breed">
  <i class="bi bi-check-circle"></i>
  Breed (92%)
</span>
```

## 8.5 Focus Management

### Skip Links

```html
<a href="#main-content" class="skip-link">
  Spring naar hoofdinhoud
</a>

<style>
.skip-link {
  position: absolute;
  top: -40px;
  left: 0;
  background: #1E3A5F;
  color: white;
  padding: 0.5rem 1rem;
  text-decoration: none;
  z-index: 100;
}

.skip-link:focus {
  top: 0;
}
</style>
```

### Focus Management na Navigatie

```javascript
// Na pagina navigatie: focus naar main heading
function navigateToStelling(index) {
  // ... update stelling

  // Focus naar nieuwe stelling heading
  const heading = document.querySelector('.stelling-title');
  heading.setAttribute('tabindex', '-1');
  heading.focus();
}
```

### Modal Focus Management

```javascript
// Bij modal open: focus naar modal
// Bij modal close: focus terug naar trigger button

let previousFocus;

function openModal() {
  previousFocus = document.activeElement;
  const modal = document.querySelector('[role="dialog"]');
  modal.classList.add('open');
  modal.querySelector('button').focus(); // Focus eerste button
}

function closeModal() {
  const modal = document.querySelector('[role="dialog"]');
  modal.classList.remove('open');
  previousFocus.focus(); // Restore focus
}
```

---

# 9. DESIGN PATTERNS

## 9.1 Welkomstscherm

### Layout

```
┌─────────────────────────────────────┐
│         [LOGO / HEADING]            │
│      Kieswijzer 2025                │
│                                     │
│   [Subtitle / Description]          │
│   Ontdek welke partij...            │
│                                     │
│   ┌───────┬───────┬───────┐         │
│   │ 🌳    │ 🏠    │ ❤️‍🩹   │         │
│   │Klimaat│ Wonen │ Zorg  │         │
│   ├───────┼───────┼───────┤         │
│   │ 📚    │ €     │ 🌸    │         │
│   │Onderw.│Econom.│Natuur │         │
│   └───────┴───────┴───────┘         │
│   ... (13 themas total)             │
│                                     │
│   [CTA Button]                      │
│   Start de kieswijzer →             │
│                                     │
│   [Secondary Links]                 │
│   Hoe werkt het? | Over ons         │
└─────────────────────────────────────┘
```

### Code Structure

```html
<div class="welcome-screen">
  <div class="container max-w-4xl mx-auto px-6 py-12">
    <!-- Header -->
    <header class="text-center mb-12">
      <h1 class="text-6xl font-bold font-serif text-navy mb-4">
        Kieswijzer 2025
      </h1>
      <p class="text-xl text-navy/70">
        Beantwoord 111 stellingen en ontdek welke partij het beste bij jou past
      </p>
    </header>

    <!-- Thema Grid -->
    <div class="thema-grid grid grid-cols-2 md:grid-cols-4 gap-4 mb-12">
      <!-- Thema Card -->
      <div class="thema-card bg-white rounded-lg p-6 text-center hover:shadow-lg transition-shadow">
        <i class="bi bi-tree text-4xl text-coral mb-2"></i>
        <h3 class="font-semibold text-navy">Klimaat & Energie</h3>
        <span class="text-sm text-navy/60">8 stellingen</span>
      </div>
      <!-- Repeat for all 13 themes -->
    </div>

    <!-- CTA Button -->
    <div class="text-center mb-8">
      <button class="btn-primary text-lg px-8 py-4">
        Start de kieswijzer
        <i class="bi bi-arrow-right ml-2"></i>
      </button>
    </div>

    <!-- Secondary Links -->
    <div class="text-center">
      <a href="/hoe-het-werkt" class="text-navy hover:text-coral mx-3">
        Hoe werkt het?
      </a>
      <a href="/over-ons" class="text-navy hover:text-coral mx-3">
        Over ons
      </a>
    </div>
  </div>
</div>
```

## 9.2 Thema Intro

### Layout

```
┌─────────────────────────────────────┐
│ [Full-screen colored background]   │
│                                     │
│          [Icon Large]               │
│             🌳                      │
│                                     │
│      [Thema Naam]                   │
│   Klimaat & Energie                 │
│                                     │
│   [Aantal stellingen]               │
│   8 stellingen                      │
│                                     │
│   [CTA Button]                      │
│   Start thema →                     │
│                                     │
│ [Progress indicator]                │
│ Thema 1 van 13                      │
└─────────────────────────────────────┘
```

### Code Structure

```html
<div class="thema-intro bg-coral min-h-screen flex items-center justify-center animate-fade-in">
  <div class="text-center text-white px-6">
    <!-- Icon -->
    <div class="mb-8">
      <i class="bi bi-tree text-8xl animate-bounce-in"></i>
    </div>

    <!-- Thema Naam -->
    <h1 class="text-5xl font-bold font-serif mb-4">
      Klimaat & Energie
    </h1>

    <!-- Aantal Stellingen -->
    <p class="text-xl mb-12 opacity-90">
      8 stellingen over klimaatdoelen, energie en verduurzaming
    </p>

    <!-- CTA Button -->
    <button class="btn-primary bg-navy text-white border-navy hover:bg-navy-dark text-lg px-8 py-4">
      Start thema
      <i class="bi bi-arrow-right ml-2"></i>
    </button>

    <!-- Progress -->
    <p class="mt-8 text-sm opacity-75">
      Thema 1 van 13
    </p>
  </div>
</div>
```

### Thema Kleuren Dynamisch

```javascript
// Thema kleuren array
const themaKleuren = {
  'klimaat': '#FF6B6B',
  'wonen': '#1E3A5F',
  'zorg': '#10B981',
  // ... etc
};

// Apply dynamisch
function showThemaIntro(themaNaam) {
  const kleur = themaKleuren[themaNaam];
  document.querySelector('.thema-intro').style.backgroundColor = kleur;
}
```

## 9.3 Stelling Interface

### Layout

```
┌─────────────────────────────────────┐
│ [Progress Bar]                      │
│ ████████░░░░░░░░░░ 23/111           │
│                                     │
│ [Badge]              [Info Button]  │
│ Klimaat & Energie         (i)       │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ [Stelling Card]                 │ │
│ │                                 │ │
│ │ Nederland moet in 2040          │ │
│ │ volledig klimaatneutraal zijn   │ │
│ │                                 │ │
│ │ [Toelichting]                   │ │
│ │ Over versnelling...             │ │
│ │                                 │ │
│ │ ┌─────┬─────┬─────┬─────┐       │ │
│ │ │Eens │Oneen│Neutr│Weet │       │ │
│ │ │     │s    │aal  │niet │       │ │
│ │ └─────┴─────┴─────┴─────┘       │ │
│ │                                 │ │
│ │ ☐ Belangrijk voor mij           │ │
│ └─────────────────────────────────┘ │
│                                     │
│ [← Terug]                           │
└─────────────────────────────────────┘
```

### Code Structure

```html
<div class="stelling-screen bg-cream min-h-screen py-8 px-4 animate-fade-in">
  <div class="container max-w-3xl mx-auto">

    <!-- Progress Bar -->
    <div class="progress-container mb-8">
      <div class="progress-label flex justify-between mb-2">
        <span class="text-sm font-semibold text-navy/70">Voortgang</span>
        <span class="text-sm font-semibold text-navy/70">Stelling 23 van 111</span>
      </div>
      <div class="progress-bar h-2 bg-gray-200 rounded-full overflow-hidden">
        <div class="progress-bar-fill bg-gradient-to-r from-green to-green-dark h-full"
             style="width: 21%"></div>
      </div>
    </div>

    <!-- Stelling Card -->
    <div class="card-stelling bg-white rounded-xl shadow-lg p-8">

      <!-- Header -->
      <div class="card-header flex justify-between items-center mb-6">
        <span class="badge-thema bg-coral/10 text-coral px-4 py-2 rounded-full text-sm font-semibold">
          Klimaat & Energie
        </span>
        <button class="btn-icon" aria-label="Meer informatie">
          <i class="bi bi-info-circle text-2xl text-navy"></i>
        </button>
      </div>

      <!-- Stelling Tekst -->
      <h2 class="card-title text-2xl font-serif text-navy mb-4">
        Nederland moet in 2040 volledig klimaatneutraal zijn
      </h2>

      <!-- Toelichting -->
      <p class="card-description text-base text-navy/70 mb-8">
        Over versnelling klimaatdoelen en gevolgen voor industrie
      </p>

      <!-- Answer Buttons -->
      <div class="btn-group grid grid-cols-2 md:grid-cols-4 gap-4 mb-6">
        <button class="btn-primary">Eens</button>
        <button class="btn-primary">Oneens</button>
        <button class="btn-neutral">Neutraal</button>
        <button class="btn-neutral">Weet ik niet</button>
      </div>

      <!-- Belangrijk Checkbox -->
      <label class="flex items-center cursor-pointer hover:bg-yellow/10 p-3 rounded-lg transition-colors">
        <input type="checkbox" class="mr-3 w-5 h-5">
        <span class="text-navy font-semibold">
          <i class="bi bi-star-fill text-yellow mr-2"></i>
          Belangrijk voor mij (telt dubbel)
        </span>
      </label>
    </div>

    <!-- Terug Button -->
    <div class="mt-8">
      <button class="btn-secondary">
        <i class="bi bi-arrow-left mr-2"></i>
        Terug
      </button>
    </div>

  </div>
</div>
```

## 9.4 Resultaten Scherm

### Layout

```
┌─────────────────────────────────────┐
│ [Confetti Animation 🎉]             │
│                                     │
│      Jouw Resultaten                │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ #1 GroenLinks-PvdA      78%     │ │
│ │ ─────────────────────────────   │ │
│ │ [Coverage: Breed 92%]  (i)      │ │
│ │                                 │ │
│ │ [Details uitklappen ⌄]          │ │
│ │                                 │ │
│ │ Overeenkomsten (67 punten):     │ │
│ │ ✓ Klimaatneutraal 2040          │ │
│ │ ✓ Meer windmolens               │ │
│ │ ... (uitklapbaar)               │ │
│ └─────────────────────────────────┘ │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ #2 D66                  72%     │ │
│ │ ... (same structure)            │ │
│ └─────────────────────────────────┘ │
│                                     │
│ [AI Advies Button]                  │
│ Krijg persoonlijk partijadvies →   │
└─────────────────────────────────────┘
```

### Code Structure

```html
<div class="results-screen bg-cream min-h-screen py-12 px-4">
  <div class="container max-w-6xl mx-auto">

    <!-- Header -->
    <header class="text-center mb-12">
      <h1 class="text-4xl font-bold font-serif text-navy mb-4">
        Jouw Resultaten
      </h1>
      <p class="text-lg text-navy/70">
        Op basis van jouw antwoorden op 111 stellingen
      </p>
    </header>

    <!-- Results Grid -->
    <div class="results-grid grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 mb-12">

      <!-- Partij Card #1 -->
      <div class="card-partij bg-white rounded-lg shadow-lg p-6 border-l-4 border-red-600">

        <!-- Header -->
        <div class="card-partij-header flex justify-between items-start mb-4">
          <div>
            <div class="text-sm font-semibold text-gray-500 mb-1">#1</div>
            <h3 class="card-partij-naam text-2xl font-bold font-serif text-red-600">
              GroenLinks-PvdA
            </h3>
          </div>
          <div class="text-right">
            <div class="card-partij-score text-3xl font-bold text-navy">78%</div>
            <div class="card-partij-percentage text-sm text-navy/60">67/86 punten</div>
          </div>
        </div>

        <!-- Coverage Badge + Info -->
        <div class="flex items-center gap-2 mb-4">
          <span class="badge-coverage-breed">
            <i class="bi bi-check-circle"></i>
            Breed (92%)
          </span>
          <button class="btn-icon text-sm" aria-label="Partij informatie">
            <i class="bi bi-info-circle"></i>
          </button>
        </div>

        <!-- Details Toggle -->
        <button class="details-toggle w-full text-left font-semibold text-navy flex justify-between items-center p-3 hover:bg-gray-50 rounded-lg">
          <span>Bekijk details</span>
          <i class="bi bi-chevron-down chevron-icon"></i>
        </button>

        <!-- Details (collapsible) -->
        <div class="overeenkomsten">

          <!-- Overeenkomsten -->
          <div class="mt-4 p-4 bg-green/10 rounded-lg">
            <h4 class="font-semibold text-green mb-3 flex items-center">
              <i class="bi bi-check-circle mr-2"></i>
              Overeenkomsten (67 punten)
            </h4>
            <ul class="space-y-2 text-sm">
              <li class="overeenkomst-item flex items-start">
                <i class="bi bi-check text-green mr-2 mt-1"></i>
                <span>Klimaatneutraal in 2040 <span class="text-gray-500">(2pt)</span></span>
              </li>
              <li class="overeenkomst-item flex items-start">
                <i class="bi bi-check text-green mr-2 mt-1"></i>
                <span>Meer windmolens <span class="text-gray-500">(4pt, dubbel)</span></span>
              </li>
              <!-- ... more -->
            </ul>
          </div>

          <!-- Verschillen -->
          <div class="mt-4 p-4 bg-coral/10 rounded-lg">
            <h4 class="font-semibold text-coral mb-3 flex items-center">
              <i class="bi bi-x-circle mr-2"></i>
              Verschillen (19 punten)
            </h4>
            <ul class="space-y-2 text-sm">
              <li class="verschil-item flex items-start">
                <i class="bi bi-x text-coral mr-2 mt-1"></i>
                <span>Kernenergie uitbreiden <span class="text-gray-500">(0pt)</span></span>
              </li>
              <!-- ... more -->
            </ul>
          </div>

        </div>
      </div>

      <!-- Repeat for all parties -->
    </div>

    <!-- AI Advies CTA -->
    <div class="text-center">
      <button class="btn-primary text-lg px-8 py-4">
        Krijg persoonlijk partijadvies met AI
        <i class="bi bi-arrow-right ml-2"></i>
      </button>
      <p class="text-sm text-navy/60 mt-3">
        Vul je profiel in voor een gepersonaliseerd advies op basis van jouw situatie
      </p>
    </div>

  </div>
</div>
```

## 9.5 Modal Pattern

Zie [5.3 Modals](#53-modals) voor complete code.

**Key Features:**
- Backdrop met 50% opacity zwart
- Centered met max-width 56rem
- Smooth open/close animatie (cubic-bezier bounce)
- Custom scrollbar (yellow thumb, cream track)
- Keyboard accessible (ESC to close, Tab trap)
- Focus management (terug naar trigger bij sluiten)

## 9.6 Tooltip Pattern

Zie [5.4 Tooltips](#54-tooltips) voor complete code.

**Key Features:**
- Hover op desktop, click op mobile
- Positioned boven element (bottom: 100% + 0.5rem)
- Arrow pointer (CSS ::after pseudo-element)
- Fade-in animatie (200ms ease-out)
- Max-width 300-400px (leesbaarheid)
- Z-index 10 (boven content, onder modals)

---

# 10. ASSETS & RESOURCES

## 10.1 Icon Library

### Bootstrap Icons 1.11.3

**CDN:**
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.css">
```

**Waarom Bootstrap Icons?**
- ✅ 2000+ icons (gratis, open-source)
- ✅ Consistent design language
- ✅ SVG + webfont (flexibel)
- ✅ Regelmatige updates
- ✅ Excellent documentatie

**Meest gebruikte icons:**

| Icon | Class | Gebruik |
|------|-------|---------|
| 🌳 | `bi-tree` | Klimaat thema |
| 🏠 | `bi-house-door` | Wonen thema |
| ❤️‍🩹 | `bi-heart-pulse` | Zorg thema |
| 📚 | `bi-book` | Onderwijs thema |
| ℹ️ | `bi-info-circle` | Info button |
| ✓ | `bi-check-lg` | Overeenkomsten |
| ✗ | `bi-x-lg` | Verschillen / Close |
| ⭐ | `bi-star-fill` | Belangrijk |
| ⌄ | `bi-chevron-down` | Dropdown |
| ← | `bi-arrow-left` | Terug button |
| → | `bi-arrow-right` | Verder button |

**Download voor offline:**
```bash
npm install bootstrap-icons
# Icons in: node_modules/bootstrap-icons/icons/*.svg
```

## 10.2 Custom Cursor

### Emoji Cursor: ✍ (Schrijvende Hand)

**Complete implementatie met hotspot positioning:**

```css
/* Global cursor (voor alle elementen) */
body, html, * {
  cursor: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="34" height="34"><text x="0" y="28" font-size="28">✍</text></svg>') 3 25, auto;
  /*
    3 25 = hotspot position (x y in pixels)
    3 = horizontal offset (tip van pen)
    25 = vertical offset (hand positie)
  */
}

/* Interactive elements cursor (pointer variant) */
button,
a,
input[type="submit"],
input[type="button"],
.btn-hover-grow,
select,
textarea,
input[type="text"] {
  cursor: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="34" height="34"><text x="0" y="28" font-size="28">✍</text></svg>') 3 25, pointer;
  /* Zelfde cursor maar met pointer fallback */
}
```

**Waarom deze specifieke waarden?**
- **Width/Height 34px**: Groot genoeg voor zichtbaarheid, niet te groot
- **Font-size 28px**: Emoji wordt goed leesbaar gerenderd
- **Hotspot (3, 25)**: Tip van de pen is het clickpunt (niet centrum)
- **Y-position 28**: Emoji netjes binnen viewBox

**Waarom custom cursor?**
- ✅ Engagement (leuk detail)
- ✅ Reinforces "keuze maken" thema (schrijven = stemmen)
- ✅ Lichtgewicht (SVG data URI, geen externe file)
- ✅ Consistent op alle interactieve elementen
- ⚠️ Fallback naar auto/pointer cursor (werkt niet op iOS Safari)

**Platform support:**
- Desktop browsers: ✅ Chrome, Firefox, Safari, Edge
- Mobile: ❌ (altijd auto cursor, mobiel heeft geen cursor)

**Testing:**
```html
<!-- Test hotspot positioning -->
<div style="padding: 50px; border: 1px solid red;">
  Hover over deze tekst - de tip van de pen moet klikbaar zijn
</div>
```

**DON'T:**
```css
/* ❌ WRONG: Centrum hotspot (minder precies) */
cursor: url('...') 16 16, auto; /* Centrum van 32x32 */

/* ❌ WRONG: Te kleine font (onleesbaar) */
<text font-size="14">✍</text>

/* ❌ WRONG: Verkeerde fallback */
cursor: url('...'), default; /* Gebruik 'auto' of 'pointer' */
```

## 10.3 Confetti Library

### Canvas Confetti 1.9.2

**CDN:**
```html
<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.9.2/dist/confetti.browser.min.js"></script>
```

**Gebruik:**
```javascript
// Basic confetti
confetti();

// Custom confetti (Stemwijzer style)
confetti({
  particleCount: 200,
  spread: 100,
  origin: { y: 0.6 },
  colors: ['#FF6B6B', '#1E3A5F', '#10B981', '#FDB750']
});

// Confetti burst from button
function celebrateResults(button) {
  const rect = button.getBoundingClientRect();
  const x = rect.left + rect.width / 2;
  const y = rect.top + rect.height / 2;

  confetti({
    particleCount: 100,
    startVelocity: 30,
    spread: 360,
    origin: {
      x: x / window.innerWidth,
      y: y / window.innerHeight
    },
    colors: ['#FF6B6B', '#10B981', '#FDB750']
  });
}
```

**Wanneer gebruiken:**
- ✅ Quiz voltooiing (resultaten scherm)
- ✅ Milestone (50 stellingen, 100 stellingen)
- ❌ Niet bij elke stelling (te veel)

## 10.4 External Dependencies

### TailwindCSS 3.4 (CDN)

```html
<script src="https://cdn.tailwindcss.com"></script>
<script>
  tailwind.config = {
    theme: {
      extend: {
        fontFamily: {
          'sans': ['Noto Sans', 'system-ui', 'sans-serif'],
          'serif': ['Domine', 'Georgia', 'serif']
        },
        colors: {
          'coral': '#FF6B6B',
          'navy': '#1E3A5F',
          'green': '#10B981',
          'yellow': '#FDB750',
          'cream': '#FEF6E4'
        }
      }
    }
  }
</script>
```

**Waarom TailwindCSS?**
- ✅ Utility-first (snelle development)
- ✅ Geen CSS purge nodig (JIT compiler)
- ✅ Responsive modifiers (sm:, md:, lg:)
- ✅ Dark mode support (toekomst)
- ✅ Goed documented

**CDN vs Build:**
- CDN: ✅ Eenvoudig, geen build step
- Build: ✅ Kleiner bundle, custom plugins, PurgeCSS

### ⚠️ CRITICAL: TailwindCSS Dynamische Classes DON'T

**❌ PROBLEEM: Dynamische class names werken NIET met TailwindCSS JIT compiler**

```php
<!-- ❌ WRONG: Dit werkt NIET! -->
<?php $color = 'coral'; ?>
<div class="bg-<?php echo $color; ?>">
  <!-- TailwindCSS genereert deze class niet omdat het pas runtime bekend is -->
</div>

<!-- ❌ WRONG: Ook dit werkt niet -->
<div class="bg-<?= $thema_colors[$index] ?> text-white">
  <!-- JIT compiler ziet alleen bg- en text-, niet de volledige class -->
</div>
```

**✅ OPLOSSING 1: Inline styles met CSS variabelen**

```php
<!-- ✅ CORRECT: Inline style -->
<?php $color = '#FF6B6B'; ?>
<div style="background-color: <?php echo $color; ?>">
  <!-- Werkt altijd -->
</div>

<!-- ✅ CORRECT: CSS custom property -->
<div style="--theme-color: <?php echo $color; ?>; background-color: var(--theme-color);">
  <!-- Flexibel en herbruikbaar -->
</div>
```

**✅ OPLOSSING 2: PHP if/else met volledige class names**

```php
<!-- ✅ CORRECT: Volledige class names -->
<?php
$bgClass = '';
switch ($thema_key) {
    case 'klimaat':
        $bgClass = 'bg-coral';
        break;
    case 'wonen':
        $bgClass = 'bg-navy';
        break;
    case 'zorg':
        $bgClass = 'bg-green';
        break;
    // etc...
}
?>
<div class="<?php echo $bgClass; ?> text-white p-6 rounded-2xl">
  <!-- TailwindCSS ziet volledige class name in source code -->
</div>
```

**✅ OPLOSSING 3: Safelist in Tailwind config (laatste optie)**

```javascript
// Als je ECHT dynamische classes nodig hebt
tailwind.config = {
  safelist: [
    'bg-coral',
    'bg-navy',
    'bg-green',
    'bg-yellow',
    'text-coral',
    'text-navy',
    // etc... (alle mogelijke dynamische classes)
  ],
  theme: {
    // ...
  }
}
```

**Waarom is dit belangrijk?**
- TailwindCSS JIT compiler scant je HTML/PHP files voor class names
- Het herkent alleen VOLLEDIGE class strings zoals `"bg-coral"`
- String concatenatie zoals `"bg-" + variable` wordt NIET herkend
- Resultaat: class wordt niet gegenereerd = geen styling

**Best Practice voor Stemwijzer:**
- ✅ Gebruik inline styles voor thema kleuren (dynamisch)
- ✅ Gebruik TailwindCSS classes voor statische layouts
- ✅ Gebruik CSS variabelen voor herbruikbare dynamische kleuren

### Google Fonts

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Domine:wght@400..700&family=Noto+Sans:wght@400;600;700&display=swap" rel="stylesheet">
```

**Performance optimalisatie:**
- `preconnect`: Snellere DNS lookup
- `display=swap`: Voorkomt invisible text (FOIT)
- Alleen benodigde gewichten laden (400, 600, 700)

### Complete Dependencies Lijst

| Library | Versie | CDN | Gebruik |
|---------|--------|-----|---------|
| TailwindCSS | 3.4 | ✅ | CSS framework |
| Bootstrap Icons | 1.11.3 | ✅ | Icon library |
| Canvas Confetti | 1.9.2 | ✅ | Celebration animation |
| Google Fonts (Noto Sans) | - | ✅ | Body typography |
| Google Fonts (Domine) | - | ✅ | Heading typography |

**Total CDN requests:** 5
**Total CDN size:** ~150KB (gzipped)
**Performance impact:** ⚡ Minimal (alle libraries goed geoptimaliseerd)

---

# APPENDIX: QUICK REFERENCE

## Color Palette Cheat Sheet

```css
/* Primary Colors */
--coral: #FF6B6B;
--navy: #1E3A5F;
--green: #10B981;
--yellow: #FDB750;
--cream: #FEF6E4;

/* Semantics */
--success: #10B981;
--warning: #FDB750;
--error: #FF6B6B;
--info: #1E3A5F;
```

## Typography Cheat Sheet

```css
/* Headings */
h1 { font: 700 3.75rem/1.1 'Domine', serif; color: #1E3A5F; }
h2 { font: 700 3rem/1.2 'Domine', serif; color: #1E3A5F; }
h3 { font: 700 1.875rem/1.3 'Domine', serif; color: #1E3A5F; }

/* Body */
p { font: 400 1rem/1.6 'Noto Sans', sans-serif; color: #1E3A5F; }
```

## Spacing Cheat Sheet

```css
/* Common Spacings */
--space-xs: 0.5rem;   /* 8px */
--space-sm: 1rem;     /* 16px */
--space-md: 1.5rem;   /* 24px */
--space-lg: 2rem;     /* 32px */
--space-xl: 3rem;     /* 48px */
--space-2xl: 4rem;    /* 64px */
```

## Component Sizing Cheat Sheet

```css
/* Touch Targets */
min-height: 48px;
min-width: 48px;

/* Container Widths */
--container-sm: 640px;
--container-md: 768px;
--container-lg: 1024px;
--container-xl: 1280px;

/* Content Max Widths */
--content-narrow: 48rem;   /* 768px - stellingen */
--content-medium: 56rem;   /* 896px - modals */
--content-wide: 64rem;     /* 1024px - welkomst */
--content-full: 80rem;     /* 1280px - resultaten grid */
```

---

**🎉 EINDE BRANDSTYLE.md**

Dit document bevat alle design regels, UI patterns en best practices voor de Stemwijzer 2025.

**Voor designers:**
- Gebruik dit als single source of truth voor alle design beslissingen
- Bij twijfel: check dit document
- Updates: commit changes naar Git

**Voor developers:**
- Implementeer volgens deze specs
- Gebruik exact deze kleuren, spacing, typography
- Bij afwijking: overleg met designer

**Versie:** 1.0
**Laatst bijgewerkt:** 4 Oktober 2025
**Feedback:** Via GitHub issues

Voor technische implementatie details, zie [TECHNICAL.md](TECHNICAL.md)
# BRANDSTYLE SUPPLEMENT - Advanced Patterns
## Aanvulling op BRANDSTYLE.md met alle details uit de codebase

**Dit document bevat ALLE ontbrekende details, advanced patterns en DON'Ts**

---

# 11. ADVANCED UI PATTERNS

## 11.1 Floating Navigation (hoehetwerkt.php)

### Glassmorphism Navigation met Hamburger Collapse

```css
.floating-nav {
  /* Positie: fixed rechts, verticaal gecentreerd */
  position: fixed;
  top: 50%;
  right: 30px;
  transform: translateY(-50%);
  z-index: 40;

  /* Glassmorphism effect */
  background: rgba(254, 246, 228, 0.58); /* Cream met 58% opacity */
  backdrop-filter: blur(20px) saturate(180%);
  -webkit-backdrop-filter: blur(20px) saturate(180%); /* Safari */

  /* Subtle border & shadow */
  border: 1px solid rgba(30, 58, 95, 0.1);
  box-shadow: 0 8px 32px rgba(30, 58, 95, 0.12);

  /* Layout */
  border-radius: 20px;
  padding: 10px;
  display: flex;
  flex-direction: column;
  gap: 8px;

  /* Smooth transitions */
  transition: all 0.4s cubic-bezier(0.25, 1, 0.5, 1);
  opacity: 1;
  max-height: 80vh;
  overflow-y: auto;
}

/* Custom scrollbar voor floating nav */
.floating-nav::-webkit-scrollbar {
  width: 6px;
}

.floating-nav::-webkit-scrollbar-track {
  background: rgba(30, 58, 95, 0.05);
  border-radius: 10px;
}

.floating-nav::-webkit-scrollbar-thumb {
  background: rgba(30, 58, 95, 0.2);
  border-radius: 10px;
}

.floating-nav::-webkit-scrollbar-thumb:hover {
  background: rgba(30, 58, 95, 0.3);
}
```

### Hamburger Collapse State (bij scroll naar top)

```css
/* Collapsed state: rond icoontje */
.floating-nav.is-at-top {
  width: 50px;
  height: 50px;
  padding: 0;
  border-radius: 50%; /* volledig rond */
  align-items: center;
  justify-content: center;
  opacity: 0.7;
  gap: 0;
  overflow: hidden;
}

/* Show hamburger icon */
.hamburger-icon {
  display: none; /* Hidden by default */
  width: 24px;
  height: 24px;
  color: #1E3A5F;
}

.floating-nav.is-at-top .hamburger-icon {
  display: block;
}

/* Hide nav items */
.floating-nav.is-at-top a {
  display: none;
}

/* Expand on hover */
.floating-nav.is-at-top:hover {
  width: auto;
  height: auto;
  max-height: 80vh;
  padding: 10px;
  border-radius: 20px;
  opacity: 1;
  align-items: stretch;
  gap: 8px;
  overflow-y: auto;
}

.floating-nav.is-at-top:hover .hamburger-icon {
  display: none; /* Hide hamburger when expanded */
}

.floating-nav.is-at-top:hover a {
  display: flex; /* Show nav items */
}
```

**JavaScript:**

```javascript
window.addEventListener('scroll', function() {
  const floatingNav = document.querySelector('.floating-nav');
  const scrollPosition = window.scrollY;

  if (scrollPosition < 100) {
    floatingNav.classList.add('is-at-top');
  } else {
    floatingNav.classList.remove('is-at-top');
  }
});
```

**Waarom dit pattern?**
- ✅ Altijd toegankelijk (fixed positioning)
- ✅ Niet opdringerig (collapsed bij top)
- ✅ Glassmorphism = modern & premium
- ✅ Smooth hover expand (delight)

## 11.2 Scroll-Away Header

### Header die verdwijnt bij scrollen

```css
.main-header {
  position: sticky;
  top: 0;
  z-index: 50;
  transition: transform 0.4s cubic-bezier(0.25, 1, 0.5, 1);
}

.main-header.header-hidden {
  transform: translateY(-100%);
}
```

**JavaScript met scroll direction detection:**

```javascript
let lastScrollY = 0;
let ticking = false;

window.addEventListener('scroll', function() {
  if (!ticking) {
    window.requestAnimationFrame(function() {
      const header = document.querySelector('.main-header');
      const currentScrollY = window.scrollY;

      if (currentScrollY > lastScrollY && currentScrollY > 100) {
        // Scrolling down & past threshold
        header.classList.add('header-hidden');
      } else {
        // Scrolling up
        header.classList.remove('header-hidden');
      }

      lastScrollY = currentScrollY;
      ticking = false;
    });

    ticking = true;
  }
});
```

**Waarom dit pattern?**
- ✅ Meer screen real estate bij scrollen
- ✅ Header beschikbaar bij scroll up (intuïtief)
- ✅ Smooth transition (niet abrupt)
- ✅ `requestAnimationFrame` voor 60fps performance

## 11.3 Compact Button Transformation

### Button die transformeert naar icon-only

```css
.back-button {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.75rem 1.5rem;
  transition: all 0.3s ease;
  overflow: hidden;
}

.back-button .button-text {
  transition: opacity 0.3s ease, width 0.3s ease;
  white-space: nowrap;
}

/* Compact state */
.back-button.compact {
  width: 48px;
  height: 48px;
  padding: 0;
  border-radius: 50%; /* van rounded naar volledig rond */
  justify-content: center;
  gap: 0;
}

.back-button.compact .button-text {
  opacity: 0;
  width: 0;
}
```

**HTML:**

```html
<button class="back-button bg-navy text-white rounded-full">
  <i class="bi bi-arrow-left flex-shrink-0"></i>
  <span class="button-text">Terug naar kieswijzer</span>
</button>
```

**JavaScript toggle:**

```javascript
const backButton = document.querySelector('.back-button');

window.addEventListener('scroll', function() {
  if (window.scrollY > 200) {
    backButton.classList.add('compact');
  } else {
    backButton.classList.remove('compact');
  }
});
```

## 11.4 Scroll Margin (Anchor Links)

### Smooth scroll met offset voor sticky headers

```css
/* All sections krijgen scroll margin */
.nav-section {
  scroll-margin-top: 80px; /* Height van sticky header */
}

/* Smooth scroll behavior */
html {
  scroll-behavior: smooth;
}
```

**HTML:**

```html
<section id="methodologie" class="nav-section">
  <h2>Methodologie</h2>
  <!-- Content -->
</section>

<a href="#methodologie">Naar methodologie</a>
<!-- Scrollt naar section met 80px offset -->
```

**DON'T:**

```css
/* ❌ WRONG: Scroll margin op verkeerd element */
body {
  scroll-margin-top: 80px; /* Werkt niet */
}

/* ✅ CORRECT: Op anchor target */
#methodologie {
  scroll-margin-top: 80px;
}
```

## 11.5 Section Icon Pattern

### Consistent icon styling voor secties

```css
.section-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 3rem; /* 48px */
  height: 3rem;
  border-radius: 50%;
  margin-right: 1rem;
}

/* Variant met achtergrondkleur */
.section-icon-coral {
  background: rgba(255, 107, 107, 0.1);
  color: #FF6B6B;
}

.section-icon-navy {
  background: rgba(30, 58, 95, 0.1);
  color: #1E3A5F;
}

.section-icon-green {
  background: rgba(16, 185, 129, 0.1);
  color: #10B981;
}
```

**HTML:**

```html
<h2 class="flex items-center">
  <span class="section-icon section-icon-coral">
    <i class="bi bi-check-circle text-xl"></i>
  </span>
  Methodologie
</h2>
```

---

# 12. JAVASCRIPT ADVANCED PATTERNS

## 12.1 Modal Functions (Complete Implementation)

### Open Modal met Animations

```javascript
function openModal() {
  const modal = document.getElementById('infoModal');
  const modalContent = modal.querySelector('.modal-content');
  const backdrop = modal.querySelector('.modal-backdrop');

  // Show modal (remove hidden class)
  modal.classList.remove('hidden');

  // Start animations (requestAnimationFrame voor smooth transition)
  requestAnimationFrame(() => {
    modalContent.classList.remove('modal-close');
    backdrop.classList.remove('backdrop-fade-out');
  });

  // Prevent body scroll
  document.body.style.overflow = 'hidden';

  // Focus trap: focus eerste focusable element
  const firstFocusable = modal.querySelector('button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])');
  if (firstFocusable) {
    firstFocusable.focus();
  }
}
```

### Close Modal met Cleanup

```javascript
function closeModal() {
  const modal = document.getElementById('infoModal');
  const modalContent = modal.querySelector('.modal-content');
  const backdrop = modal.querySelector('.modal-backdrop');

  // Start close animations
  modalContent.classList.add('modal-close');
  backdrop.classList.add('backdrop-fade-out');

  // Wait for animation duration (250ms), then cleanup
  setTimeout(() => {
    modal.classList.add('hidden');

    // Remove animation classes (reset voor volgende open)
    modalContent.classList.remove('modal-close');
    backdrop.classList.remove('backdrop-fade-out');

    // Restore body scroll
    document.body.style.overflow = 'auto';

    // Optional: Clear form data
    const form = modal.querySelector('form');
    if (form) {
      form.reset();
    }
  }, 250); // MOET matchen met CSS animation duration
}
```

### Keyboard Handlers (ESC + Tab Trap)

```javascript
// ESC to close
document.addEventListener('keydown', function(e) {
  if (e.key === 'Escape') {
    const modal = document.getElementById('infoModal');
    if (!modal.classList.contains('hidden')) {
      closeModal();
    }
  }
});

// Tab trap (houdt focus binnen modal)
function trapFocus(e) {
  const modal = document.querySelector('[role="dialog"]:not(.hidden)');
  if (!modal) return;

  const focusableElements = modal.querySelectorAll(
    'button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])'
  );

  const firstElement = focusableElements[0];
  const lastElement = focusableElements[focusableElements.length - 1];

  if (e.key === 'Tab') {
    if (e.shiftKey) { // Shift + Tab (backwards)
      if (document.activeElement === firstElement) {
        e.preventDefault();
        lastElement.focus();
      }
    } else { // Tab (forwards)
      if (document.activeElement === lastElement) {
        e.preventDefault();
        firstElement.focus();
      }
    }
  }
}

document.addEventListener('keydown', trapFocus);
```

### Click Outside to Close

```javascript
document.addEventListener('click', function(e) {
  // Check if click is on backdrop (niet op modal content)
  if (e.target.classList.contains('modal-backdrop')) {
    closeModal();
  }
});

// Alternative: check if click is outside modal-content
document.addEventListener('click', function(e) {
  const modal = document.getElementById('infoModal');
  const modalContent = modal.querySelector('.modal-content');

  if (!modal.classList.contains('hidden') && !modalContent.contains(e.target)) {
    closeModal();
  }
});
```

## 12.2 Progress Bar Animation (Orchestrated)

### Multi-stage Animation Sequence

```javascript
document.addEventListener('DOMContentLoaded', function() {
  const progressBar = document.querySelector('.progress-bar-fill');
  if (!progressBar) return;

  // Get target width from CSS variable or data-attribute
  const targetWidth = getComputedStyle(progressBar).getPropertyValue('--target-width') ||
                      progressBar.dataset.targetWidth;

  // STEP 1: Forceer reflow (browser moet initial state renderen)
  progressBar.offsetHeight;

  // STEP 2: Container fade-in (gebeurt via CSS animate-fade-in)
  // Dit duurt 500ms

  // STEP 3: Na container fade-in (500ms): start progress bar fill
  setTimeout(() => {
    progressBar.style.width = targetWidth;
    // CSS transition duurt 700ms
  }, 500);

  // STEP 4: Tekst fade-in tijdens progress bar fill
  const progressText = document.querySelector('.progress-text-animate');
  if (progressText) {
    // Start na 900ms (500ms container + 400ms progress bar partial)
    setTimeout(() => {
      progressText.style.opacity = '1';
      progressText.style.transform = 'translateY(0)';
    }, 900);
  }
});
```

**CSS (orchestrated animations):**

```css
/* Container fade-in: 0-500ms */
.progress-container {
  animation: fadeIn 0.5s ease-out;
}

/* Progress bar fill: 500-1200ms (start na 500ms, duurt 700ms) */
.progress-bar-fill {
  width: 0%;
  transition: width 0.7s ease-out 0.5s;
  /* delay = 0.5s (na container fade-in) */
}

/* Text fade-in: 900-1400ms (start tijdens progress bar) */
.progress-text-animate {
  opacity: 0;
  transform: translateY(10px);
  transition: opacity 0.5s ease-out 0.9s,
              transform 0.5s ease-out 0.9s;
}
```

**Timing diagram:**

```
0ms     500ms   900ms   1200ms  1400ms
|-------|-------|-------|-------|
Container fade-in
        Progress bar fill
                Text fade-in
```

## 12.3 Character Counter with Warning States

```javascript
document.addEventListener('DOMContentLoaded', function() {
  const textarea = document.getElementById('toekomstplannenInput');
  const counter = document.getElementById('toekomstplannenCounter');
  const maxLength = 500;

  if (textarea && counter) {
    textarea.addEventListener('input', function() {
      const currentLength = this.value.length;
      counter.textContent = currentLength;

      // Update counter styling based on usage
      if (currentLength >= maxLength) {
        // At max: error state
        counter.classList.add('text-coral');
        counter.classList.remove('text-yellow', 'text-navy');
      } else if (currentLength >= maxLength * 0.9) {
        // 90%+: warning state
        counter.classList.add('text-yellow');
        counter.classList.remove('text-coral', 'text-navy');
      } else {
        // Normal state
        counter.classList.add('text-navy');
        counter.classList.remove('text-coral', 'text-yellow');
      }
    });
  }
});
```

**HTML:**

```html
<textarea
  id="toekomstplannenInput"
  maxlength="500"
  class="w-full p-3 border rounded-lg"
  placeholder="Bijv. studeren, huis kopen, kinderen krijgen...">
</textarea>

<div class="flex justify-between text-sm mt-2">
  <span class="text-gray-500">Toekomstplannen (optioneel)</span>
  <span class="font-semibold">
    <span id="toekomstplannenCounter" class="text-navy">0</span>/500
  </span>
</div>
```

## 12.4 Tooltip Toggle (Responsive: Hover vs Click)

### Desktop: Hover | Mobile: Click Toggle

```javascript
const tooltipTriggers = document.querySelectorAll('.coverage-indicator');

tooltipTriggers.forEach(trigger => {
  const tooltip = trigger.querySelector('.coverage-tooltip');

  // Mobile: click toggle
  trigger.addEventListener('click', function(e) {
    if (window.innerWidth < 1024) { // Mobile breakpoint
      e.stopPropagation(); // Prevent bubbling

      // Toggle active class
      const isActive = this.classList.contains('active');

      // Close all other tooltips
      tooltipTriggers.forEach(other => {
        other.classList.remove('active');
      });

      // Toggle this tooltip
      if (!isActive) {
        this.classList.add('active');
      }
    }
  });

  // Desktop: hover handled by CSS
  // No JavaScript needed - gebruik :hover pseudo-class
});

// Close all tooltips when clicking outside
document.addEventListener('click', function(e) {
  if (!e.target.closest('.coverage-indicator')) {
    tooltipTriggers.forEach(trigger => {
      trigger.classList.remove('active');
    });
  }
});
```

**CSS:**

```css
/* Tooltip hidden by default */
.coverage-tooltip {
  display: none;
}

/* Desktop: show on hover */
@media (min-width: 1024px) {
  .coverage-indicator:hover .coverage-tooltip {
    display: block;
  }
}

/* Mobile: show on active class */
.coverage-indicator.active .coverage-tooltip {
  display: block;
}
```

## 12.5 Accordion (Chevron Rotation + Slide Toggle)

```javascript
function toggleDetails(button) {
  const chevron = button.querySelector('.chevron-icon');
  const card = button.closest('.card-partij');
  const details = card.querySelector('.overeenkomsten');

  // Toggle chevron rotation (180deg)
  chevron.classList.toggle('rotate');

  // Toggle details visibility (slide down/up)
  details.classList.toggle('show');
}
```

**CSS:**

```css
/* Chevron rotation */
.chevron-icon {
  transition: transform 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
  display: inline-block;
}

.chevron-icon.rotate {
  transform: rotate(180deg);
}

/* Accordion content */
.overeenkomsten {
  display: none;
  opacity: 0;
  max-height: 0;
  overflow: hidden;
  transform: translateY(-20px);
}

.overeenkomsten.show {
  display: block;
  opacity: 1;
  max-height: 5000px; /* Large enough for content */
  transform: translateY(0);
  animation: slideDown 0.5s cubic-bezier(0.34, 1.56, 0.64, 1);
}

@keyframes slideDown {
  from {
    opacity: 0;
    transform: translateY(-20px);
    max-height: 0;
  }
  to {
    opacity: 1;
    transform: translateY(0);
    max-height: 5000px;
  }
}
```

## 12.6 Form Validation with Visual Feedback

```javascript
document.getElementById('aiAnalyseForm').addEventListener('submit', async function(e) {
  e.preventDefault();

  // Clear previous errors
  clearErrors();

  // Validate required fields
  const leeftijd = document.getElementById('leeftijd').value;
  const postcode = document.getElementById('postcode').value;

  let hasErrors = false;

  // Leeftijd validatie
  if (!leeftijd || leeftijd < 18 || leeftijd > 120) {
    showFieldError('leeftijd', 'Vul een geldige leeftijd in (18-120)');
    hasErrors = true;
  }

  // Postcode validatie (Nederlands formaat: 1234AB)
  const postcodeRegex = /^\d{4}[A-Z]{2}$/i;
  if (!postcode || !postcodeRegex.test(postcode)) {
    showFieldError('postcode', 'Vul een geldige postcode in (bijv. 1234AB)');
    hasErrors = true;
  }

  if (hasErrors) {
    return; // Stop submission
  }

  // Submit form
  const formData = new FormData(this);
  await submitForm(formData);
});

function showFieldError(fieldId, message) {
  const field = document.getElementById(fieldId);
  const errorDiv = document.createElement('div');

  errorDiv.className = 'field-error text-coral text-sm mt-1';
  errorDiv.textContent = message;
  errorDiv.setAttribute('role', 'alert');

  // Add error styling to field
  field.classList.add('border-coral');

  // Insert error message after field
  field.parentNode.insertBefore(errorDiv, field.nextSibling);

  // Focus field
  field.focus();
}

function clearErrors() {
  // Remove all error messages
  document.querySelectorAll('.field-error').forEach(error => {
    error.remove();
  });

  // Remove error styling from fields
  document.querySelectorAll('.border-coral').forEach(field => {
    field.classList.remove('border-coral');
  });
}
```

**CSS:**

```css
/* Field error state */
input.border-coral,
textarea.border-coral {
  border-color: #FF6B6B;
  outline-color: #FF6B6B;
}

input.border-coral:focus,
textarea.border-coral:focus {
  ring-color: #FF6B6B;
}

/* Error message */
.field-error {
  animation: fadeIn 0.3s ease-out;
}
```

---

# 13. COMPLETE DON'Ts REFERENCE

## 13.1 TailwindCSS DON'Ts

### ❌ Dynamische Class Names

```php
<!-- ❌ WRONG: Runtime concatenation werkt NIET -->
<div class="bg-<?php echo $color; ?>">

<!-- ❌ WRONG: Array index werkt NIET -->
<div class="text-<?= $colors[$index] ?>">

<!-- ❌ WRONG: Ternary met delen van class werkt NIET -->
<div class="<?= $active ? 'bg-' : 'text-' ?>coral">

<!-- ✅ CORRECT: Volledige class names -->
<div class="<?php echo ($color === 'coral') ? 'bg-coral' : 'bg-navy'; ?>">

<!-- ✅ CORRECT: Inline styles -->
<div style="background-color: <?php echo $color_hex; ?>">

<!-- ✅ CORRECT: Safelist in config -->
<script>
tailwind.config = {
  safelist: ['bg-coral', 'bg-navy', 'bg-green', 'bg-yellow'],
  // ...
}
</script>
```

### ❌ Verkeerde Utility Classes

```html
<!-- ❌ WRONG: Teveel utilities (moeilijk leesbaar) -->
<div class="flex items-center justify-center w-full h-full bg-white rounded-lg shadow-md p-4 mb-4 mt-2 ml-auto mr-auto max-w-md">

<!-- ✅ CORRECT: Extract naar component class -->
<div class="card-centered">
<!-- CSS: .card-centered { @apply flex items-center justify-center ... } -->

<!-- ❌ WRONG: Conflicterende utilities -->
<div class="mt-4 mt-8"> <!-- Welke wint? -->

<!-- ✅ CORRECT: Eén utility -->
<div class="mt-8">

<!-- ❌ WRONG: Arbitrary values voor alles -->
<div class="w-[342px] h-[189px] p-[23px]">

<!-- ✅ CORRECT: Gebruik spacing scale -->
<div class="w-80 h-48 p-6">
```

## 13.2 Animation DON'Ts

### ❌ Performance Killers

```css
/* ❌ WRONG: Animeren van layout properties (laggy!) */
.bad-animation {
  transition: width 0.3s, height 0.3s, margin 0.3s, padding 0.3s;
  /* Forces browser reflow = <30fps */
}

/* ✅ CORRECT: Gebruik transform & opacity (GPU accelerated) */
.good-animation {
  transition: transform 0.3s, opacity 0.3s;
  /* 60fps smooth */
}

/* ❌ WRONG: Teveel animaties tegelijk */
.too-much {
  animation: fadeIn 0.5s, bounce 0.5s, wiggle 0.5s, pulse 2s;
  /* Overwhelming = bad UX */
}

/* ✅ CORRECT: Max 1-2 animaties */
.just-right {
  animation: fadeIn 0.5s ease-out;
}

/* ❌ WRONG: Te lange durations (frustrerend) */
.too-slow {
  transition: all 3s ease;
  /* User must wait 3 seconds = bad */
}

/* ✅ CORRECT: Snappy durations (300-600ms) */
.good-timing {
  transition: all 0.3s ease;
}
```

### ❌ Timing Mismatches

```javascript
// ❌ WRONG: JavaScript timeout ≠ CSS animation duration
function badCloseModal() {
  modal.classList.add('modal-close');
  setTimeout(() => {
    modal.classList.add('hidden');
  }, 100); // CSS animation is 250ms!
  // Result: animation cut off
}

// ✅ CORRECT: Match timings
function goodCloseModal() {
  modal.classList.add('modal-close');
  setTimeout(() => {
    modal.classList.add('hidden');
  }, 250); // Matches CSS animation-duration: 250ms
}
```

## 13.3 JavaScript DON'Ts

### ❌ Memory Leaks

```javascript
// ❌ WRONG: Event listener niet cleanup
function badAddModal() {
  const modal = document.createElement('div');
  modal.addEventListener('click', handleClick);
  document.body.appendChild(modal);
  // Later: modal.remove()
  // Problem: event listener blijft in memory!
}

// ✅ CORRECT: Remove listener voor removal
function goodRemoveModal(modal) {
  modal.removeEventListener('click', handleClick);
  modal.remove();
}

// ❌ WRONG: setInterval niet cleanup
function badStartTimer() {
  setInterval(() => {
    updateUI();
  }, 1000);
  // Blijft draaien zelfs na pagina navigatie!
}

// ✅ CORRECT: Clear interval
let timerInterval;
function goodStartTimer() {
  timerInterval = setInterval(() => {
    updateUI();
  }, 1000);
}
function cleanup() {
  clearInterval(timerInterval);
}
```

### ❌ Performance Anti-Patterns

```javascript
// ❌ WRONG: Geen event delegation (veel listeners)
document.querySelectorAll('.button').forEach(btn => {
  btn.addEventListener('click', handleClick);
});
// 100 buttons = 100 listeners = memory overhead

// ✅ CORRECT: Event delegation
document.addEventListener('click', function(e) {
  if (e.target.matches('.button')) {
    handleClick(e);
  }
});

// ❌ WRONG: Geen debounce bij input
input.addEventListener('input', function() {
  expensiveAPICall();
});
// Fires 100x per seconde tijdens typen = API overload

// ✅ CORRECT: Debounce
let timeout;
input.addEventListener('input', function() {
  clearTimeout(timeout);
  timeout = setTimeout(() => {
    expensiveAPICall();
  }, 300);
});

// ❌ WRONG: DOM manipulation in loop
for (let i = 0; i < 1000; i++) {
  const div = document.createElement('div');
  document.body.appendChild(div);
  // 1000 reflows = laggy!
}

// ✅ CORRECT: Batch DOM updates
const fragment = document.createDocumentFragment();
for (let i = 0; i < 1000; i++) {
  const div = document.createElement('div');
  fragment.appendChild(div);
}
document.body.appendChild(fragment);
// 1 reflow = fast!
```

## 13.4 Accessibility DON'Ts

### ❌ A11y Violations

```html
<!-- ❌ WRONG: Button zonder label -->
<button><i class="bi bi-x-lg"></i></button>
<!-- Screen reader: "button" (wat doet het?) -->

<!-- ✅ CORRECT: ARIA label -->
<button aria-label="Sluit modal">
  <i class="bi bi-x-lg"></i>
</button>

<!-- ❌ WRONG: div als button -->
<div onclick="submit()">Verzenden</div>
<!-- Niet keyboard accessible, geen role -->

<!-- ✅ CORRECT: Echte button -->
<button onclick="submit()">Verzenden</button>

<!-- ❌ WRONG: Alleen kleur voor betekenis -->
<span style="color: red;">Error</span>
<!-- Kleurenblind: ziet geen verschil -->

<!-- ✅ CORRECT: Icon + kleur + tekst -->
<span class="text-coral">
  <i class="bi bi-exclamation-circle"></i>
  Error
</span>

<!-- ❌ WRONG: Lage contrast ratio -->
<div style="background: #FDB750; color: #FEF6E4;">
  Tekst (contrast 2.2:1 = fail)
</div>

<!-- ✅ CORRECT: Hoog contrast -->
<div style="background: #1E3A5F; color: #FEF6E4;">
  Tekst (contrast 8.2:1 = AAA)
</div>
```

### ❌ Focus Management

```javascript
// ❌ WRONG: Geen focus management na modal close
function badCloseModal() {
  modal.classList.add('hidden');
  // User tabindex gaat naar body = verward
}

// ✅ CORRECT: Restore focus naar trigger
let previousFocus;
function goodOpenModal() {
  previousFocus = document.activeElement;
  modal.classList.remove('hidden');
  modal.querySelector('button').focus();
}
function goodCloseModal() {
  modal.classList.add('hidden');
  previousFocus.focus(); // Terug naar trigger button
}

// ❌ WRONG: Geen focus trap in modal
// User kan tab naar elementen achter modal

// ✅ CORRECT: Tab trap (zie sectie 12.1)
```

## 13.5 CSS DON'Ts

### ❌ Specificity Wars

```css
/* ❌ WRONG: Teveel specificity (moeilijk overschrijven) */
body div.container .card .header h2 {
  color: #1E3A5F;
}

/* ✅ CORRECT: Lage specificity (flexibel) */
.card-header h2 {
  color: #1E3A5F;
}

/* ❌ WRONG: !important overal */
.text {
  color: #1E3A5F !important;
}
.title {
  color: #FF6B6B !important;
}
/* Onmogelijk om te overschrijven */

/* ✅ CORRECT: Geen !important (tenzij echt nodig) */
.text {
  color: #1E3A5F;
}
.title {
  color: #FF6B6B;
}
```

### ❌ Magic Numbers

```css
/* ❌ WRONG: Willekeurige px values */
.spacing {
  margin-top: 23px;
  padding-left: 17px;
  gap: 13px;
}

/* ✅ CORRECT: Spacing system (veelvouden van 4px) */
.spacing {
  margin-top: 1.5rem; /* 24px */
  padding-left: 1rem;  /* 16px */
  gap: 0.75rem;        /* 12px */
}

/* ❌ WRONG: Hardcoded z-index */
.modal { z-index: 9999; }
.dropdown { z-index: 99999; }
.tooltip { z-index: 999999; }

/* ✅ CORRECT: Z-index scale */
.modal { z-index: 50; }
.dropdown { z-index: 40; }
.tooltip { z-index: 30; }
```

---

# 14. TESTING & VALIDATION CHECKLIST

## 14.1 Visual Testing

### Browser Compatibility

```
✅ Chrome (latest)
✅ Firefox (latest)
✅ Safari (latest)
✅ Edge (latest)
⚠️ Safari iOS (custom cursor werkt niet)
⚠️ Firefox (custom scrollbar werkt niet)
```

### Device Testing

```
✅ Desktop (1920×1080, 1280×720)
✅ Tablet (iPad portrait/landscape)
✅ Mobile (iPhone SE 375px, iPhone 12 390px)
```

### Color Contrast Checker

```
Tool: WebAIM Contrast Checker
https://webaim.org/resources/contrastchecker/

Test:
- Navy (#1E3A5F) op Cream (#FEF6E4) → 8.2:1 ✅
- Coral (#FF6B6B) op Cream → 3.8:1 ✅ (Large Text)
- Green (#10B981) op Cream → 4.1:1 ✅
- Yellow (#FDB750) op Navy → 5.2:1 ✅
```

## 14.2 Functional Testing

### Modal Checklist

```
☐ Opens with smooth animation
☐ Closes with ESC key
☐ Closes when clicking backdrop
☐ Body scroll locked when open
☐ Body scroll restored when closed
☐ Focus trapped inside modal (Tab/Shift+Tab)
☐ Focus restored to trigger on close
☐ Scrollbar visible in long content
☐ Responsive (mobile + desktop)
```

### Tooltip Checklist

```
☐ Desktop: Shows on hover
☐ Desktop: Hides on mouse leave
☐ Mobile: Shows on click
☐ Mobile: Hides on outside click
☐ Mobile: Only one tooltip open at a time
☐ Arrow points to trigger
☐ Position correct (boven element, geen overflow)
☐ Scrollable bij lange content
```

### Form Checklist

```
☐ Required fields valideren
☐ Email format valideren
☐ Postcode format valideren (1234AB)
☐ Leeftijd range valideren (18-120)
☐ Character counter real-time update
☐ Error messages tonen bij invalid input
☐ Focus op eerste error field
☐ Submit disabled tijdens loading
☐ Success message na submit
```

## 14.3 Performance Testing

### Lighthouse Audit Targets

```
Performance: 90+ 🎯
Accessibility: 100 ✅
Best Practices: 100 ✅
SEO: 100 ✅
```

### Animation Performance

```
Tool: Chrome DevTools Performance tab

Check:
- 60fps tijdens animaties (groene bars)
- Geen layout thrashing (rode bars)
- Gebruik transform/opacity (GPU accelerated)
- RequestAnimationFrame voor smooth updates
```

### Bundle Size

```
Total CDN dependencies: ~150KB (gzipped)

- TailwindCSS CDN: ~50KB
- Bootstrap Icons: ~20KB
- Google Fonts: ~40KB
- Canvas Confetti: ~15KB
- Custom CSS: ~25KB
```

---

**EINDE SUPPLEMENT**

Dit supplement bevat ALLE ontbrekende advanced patterns, complete DON'Ts en testing checklists.

Merge dit met BRANDSTYLE.md voor volledige documentatie.

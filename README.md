# 🏥 ClaimVision — Power BI Analytics Workspace

[**Live Dashboard Link**](https://app.powerbi.com/view?r=eyJrIjoiMWQxMzFjYTAtZjkxMi00YzViLTg2NTktMGI5Y2YzNWRkNDBkIiwidCI6IjNjYjM3ODQ0LTAxZGEtNGJlYS04MDEwLTBmYjFmNWExZWM0ZSJ9)

Welcome to the structured development workspace for **ClaimVision** (Enterprise Healthcare Claims Intelligence Dashboard). This directory is organized according to professional business intelligence project standards.

---

## 📁 Workspace Directory Structure

```
D:\BI\healthcare\
│
├── pbix/                      # Power BI Report Files (.pbix)
│   ├── final.pbix             # Master production-ready dashboard
│   └── health.pbix            # Developer testing report
│
├── raw/                       # Raw Datasets
│   └── [Source CSV/Excel]     # Flat claim datasets imported in Power Query
│
├── themes/                    # Power BI Custom Theme JSONs
│   ├── HealthPulse_IconMatched_Theme.json  # MATCHED: Brand blue (#0A5BA6) & Teal (#0F6CBD)
│   └── HealthcareDashboard_UltraTheme.json # Legacy dark navy theme
│
├── assets/                    # Visual Assets & Media
│   ├── backgrounds/           # Full-page canvas background images (16:9)
│   │   ├── bg_about.png                # About/Landing Page background (with art)
│   │   ├── bg_claims_overview.png      # Page 1 Claims canvas (Clean, active tab)
│   │   ├── bg_patient_demographics.png # Page 2 Demographics canvas (Clean, active tab)
│   │   ├── bg_financial_analysis.png   # Page 3 Financial canvas (Clean, active tab)
│   │   └── bg_provider_analysis.png    # Page 4 Provider canvas (Clean, active tab)
│   │
│   ├── branding/              # Logos, Text Titles, and Custom Graphics
│   │   ├── claimvision_logo_icon.png   # Eye + Medical Cross custom brand icon
│   │   ├── claimvision_text_title.png  # Header stacked title text (transparent)
│   │   └── about_title_*.png           # Centered title options for the About page
│   │
│   ├── buttons/               # Button shapes (Pill shapes with text + icon)
│   │   └── btn_*_active.png / btn_*_inactive.png   # Nav buttons (10 states)
│   │
│   ├── icons/                 # Utility & Page-specific circular icons (transparent)
│   │   ├── matched_blue/      # Colored set (#0A5BA6 & #0F6CBD) for light cards
│   │   ├── matched_white/     # High-contrast white set (#FFFFFF) for blue headers
│   │   └── nav_only/          # Individual circular button icons (no text labels)
│   │
│   └── mockups/               # Widescreen screenshots & design templates
│       ├── widescreen/        # 16:9 full page mockups for reference
│       ├── square/            # 1:1 legacy square mockups
│       └── tabs/              # Sub-navigation tab view mockups (Page 3 / Page 4)
│
└── docs/                      # Technical Build Guides & Specifications
    ├── MasterFixReport_AllPages.md       # Complete analysis & one-shot fixes
    ├── ColorTheme_AllPages.md            # Detailed color tokens & element styling
    ├── HealthcareDashboard_Full_Documentation.md # Star Schema and DAX dictionary
    └── Page3_FinancialAnalysis_Complete.md # Page 3 bookmarks and tab setup
```

---

## 🛠️ Developer Setup & Implementation Guide

### 1. Apply the Theme
To automatically match your colors, cards, and matrix visuals to the **ClaimVision** brand:
1. Open your report in **Power BI Desktop**.
2. Navigate to the **View** ribbon.
3. Click the dropdown arrow in the **Themes** gallery → select **Browse for themes...**
4. Load `D:\BI\healthcare\themes\HealthPulse_IconMatched_Theme.json`.

---

### 2. Configure canvas Backgrounds
To apply the responsive wave header backgrounds:
1. Navigate to the corresponding page in Power BI.
2. Click on the empty canvas background (deselect all visuals).
3. In the **Format Page** pane, expand **Canvas background**.
4. Click **Browse** and select the matching background image from `D:\BI\healthcare\assets\backgrounds\`.
5. Set **Image fit** to **`Fill`** and **Transparency** to **`0%`**.
6. *(Tip)* Apply the same settings under the **Wallpaper** section below to eliminate any white margins on wider screens.

---

### 3. Implement the bottom Navigation Bar
To make the bottom navigation bar interactive:
1. Place the full page background (`bg_claims_overview.png` etc.) which already has the navigation pills rendered at the bottom.
2. Insert a **Blank Button** over each of the inactive tabs:
   * Go to **Format Button → Style → State (Default)**: Turn off **Fill**, **Border**, and **Text**.
   * Expand **Action**: Turn on, set Type to **Page Navigation**, and select the corresponding target page.
   * This provides native, zero-lag navigation that aligns with the visual design.

---

### 4. Custom Icon Buttons
If you prefer to load individual buttons rather than baking them into the background:
* Use the images in `assets/buttons/` (which contain the text labels).
* Use the circular icons in `assets/icons/nav_only/` (which are icon-only).
* Map the `_inactive.png` version to the **Default** state and the `_active.png` version to the **On Hover** or **Pressed** state inside the Button Style format menu.

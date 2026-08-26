# CLIENT_DETAILS_UI_SPEC.md
# Egg Gym App — Client Details Screen (Detail Klien, Pro Trainer Side, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Trainer App > Klien > Client Details (Detail Klien)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Client Details.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Detail Klien (Pro Trainer) memakai sistem warna identik dengan Client List & Home PT Dashboard (Editorial Athletics): latar near-black dengan aksen kuning emas. Token tambahan ditambahkan untuk status online (hijau), premium badge + shield, vital stat tiles, fitness target watermark, progress program, dan riwayat sesi.

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0E0E0E               | App background (screen utama)                  |
| --color-bg-card           | #1A1A1A               | Card & panel background                        |
| --color-bg-card-alt       | #161616               | Vital tile / fitness target / inner block bg   |
| --color-bg-chip           | #1C1C1C               | Info tile & icon button background             |
| --color-bg-navbar         | #121212               | Bottom tab bar background                      |
| --color-accent-primary    | #F5C518               | CTA, link, progress fill, brand text, ring     |
| --color-accent-hover      | #E0B200               | Pressed state                                  |
| --color-status-online     | #34D058               | Status dot & "AKTIF SEKARANG" (hijau)          |
| --color-text-primary      | #FFFFFF               | Name, headings, primary values                 |
| --color-text-secondary    | #9A9A9A               | Labels, captions, meta text                    |
| --color-text-muted        | #6B6B6B               | Inactive tab, placeholder, vital label         |
| --color-text-on-accent    | #0E0E0E               | Text on yellow/accent elements                 |
| --color-vital-number      | #FFFFFF               | "180" / "24.1" vital number (putih)            |
| --color-vital-number-hl   | #F5C518               | "78" weight number (kuning — highlight utama)  |
| --color-badge-premium     | #F5C518               | Badge "PREMIUM" text                           |
| --color-badge-premium-bg  | rgba(245,197,24,0.12) | Background badge PREMIUM                        |
| --color-watermark         | rgba(245,197,24,0.06) | Watermark "HYPER" di fitness target card       |
| --color-target-icon-bg    | #F5C518               | Background ikon dumbbell di target card         |
| --color-progress-fill     | #F5C518               | Progress bar program fill                      |
| --color-progress-track    | #2A2A2A               | Progress bar track (unfilled)                  |
| --color-progress-number   | #F5C518               | Persentase "65%"                               |
| --color-kcal              | #F5C518               | Nilai kalori "480 kcal" / "520 kcal"           |
| --color-link              | #F5C518               | "LIHAT PROGRAM LENGKAP" link                   |
| --color-accent-rail       | #F5C518               | Left accent rail di fitness target card        |
| --color-border-card       | #262626               | Card & panel borders                           |
| --color-border-chip       | #2A2A2A               | Tile & outline border                          |
| --color-tab-active        | #F5C518               | Active bottom-tab icon & label (KLIEN)         |
| --color-tab-inactive      | #6B6B6B               | Inactive bottom-tab icon & label               |
| --color-glow-cta          | rgba(245,197,24,0.45) | Glow elemen kuning                             |
| --color-overlay-dark      | rgba(0,0,0,0.7)       | Modal backdrop                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (client name, vital number & watermark)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-screen-title      | 20px | 800    | 1.1    | 0.5px (uppercase)| "NAUFAL" header title              |
| --text-client-name       | 24px | 800    | 1.2    | -0.3px           | "Naufal Raharjo" profile name      |
| --text-member-since      | 14px | 400    | 1.4    | 0px              | "Member sejak Jan 2024"            |
| --text-status            | 12px | 700    | 1.2    | 0.5px (uppercase)| "AKTIF SEKARANG" status            |
| --text-premium-badge     | 10px | 800    | 1.0    | 0.8px (uppercase)| "PREMIUM" badge                    |
| --text-vital-label       | 10px | 600    | 1.3    | 0.8px (uppercase)| "WEIGHT" / "HEIGHT" / "BMI"        |
| --text-vital-number      | 28px | 800    | 1.0    | -0.5px           | "78" / "180" / "24.1" vital number |
| --text-vital-unit        | 12px | 600    | 1.2    | 0px              | "KG" / "CM" unit                   |
| --text-target-supra      | 11px | 600    | 1.3    | 1.5px (uppercase)| "FITNESS TARGET" supra-label       |
| --text-target-title      | 26px | 800    | 1.1    | -0.5px           | "Hypertrophy Focus" target title   |
| --text-target-desc       | 13px | 400    | 1.5    | 0px              | Deskripsi fokus target             |
| --text-watermark         | 80px | 900    | 1.0    | -2px (uppercase) | "HYPER" background watermark       |
| --text-section-title     | 20px | 800    | 1.2    | 0px              | "Program Berjalan" / "Riwayat..."  |
| --text-link              | 11px | 700    | 1.2    | 0.5px (uppercase)| "LIHAT PROGRAM LENGKAP" link       |
| --text-program-name      | 18px | 700    | 1.3    | 0px              | "6-Week Mass Builder" program      |
| --text-program-meta      | 13px | 500    | 1.3    | 0px              | "Minggu 4 dari 6 • Sesi 18/24"     |
| --text-progress-number   | 32px | 800    | 1.0    | -1px             | "65%" big percentage               |
| --text-progress-status   | 10px | 600    | 1.3    | 0.8px (uppercase)| "COMPLETED" progress status        |
| --text-tile-label        | 10px | 600    | 1.3    | 0.5px (uppercase)| "NEXT SESSION" / "SCHEDULE" tile   |
| --text-tile-value        | 14px | 700    | 1.3    | 0px              | "Chest & Triceps" / "Tomorrow, 08:00"|
| --text-history-name      | 16px | 700    | 1.3    | 0px              | "Back & Biceps Elite" session name |
| --text-history-meta      | 11px | 500    | 1.3    | 0.3px (uppercase)| "KEMARIN • 72 MENIT"               |
| --text-kcal              | 14px | 800    | 1.0    | 0px              | "480 kcal" calorie value           |
| --text-tab-label         | 9px  | 600    | 1.2    | 0.5px (uppercase)| Bottom tab labels                  |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Badge padding, tiny gaps                         |
| --space-sm     | 8px   | Icon-text gap, label-value gap                   |
| --space-md     | 12px  | Inter-element gap                                |
| --space-base   | 16px  | Screen horizontal padding, card padding          |
| --space-lg     | 20px  | Card-to-card vertical gap                        |
| --space-xl     | 24px  | Section separation                               |
| --space-2xl    | 32px  | Major block separation                           |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Badge, small elements                            |
| --radius-md    | 12px  | Vital tile, info tile, history thumb             |
| --radius-lg    | 16px  | Cards, fitness target, program panel             |
| --radius-pill  | 999px | Progress bar, premium badge                      |
| --radius-full  | 50%   | Avatar, avatar ring, target icon circle         |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards default               |
| --shadow-navbar  | 0 -2px 12px rgba(0,0,0,0.5)           | Bottom tab bar elevation    |

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Design Canvas:  430 × 932 px (mobile portrait)
Screen Padding: 16px horizontal
Safe Area Top:  ~44px (status bar device)
Bottom Tab Bar: 100% width × 72px (fixed bottom, + safe-area-inset-bottom)
Content Scroll: vertical, padding-bottom 88px (ruang untuk tab bar)
Card Gap:       12px (history item) / 24px (antar section)
Vital Tiles:    3 kolom equal-width, gap 12px
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ [←] NAUFAL                    [⋮]    │  ← Header
├──────────────────────────────────────┤
│ ╭────╮  Naufal Raharjo     [shield]  │
│ │ AV │  Member sejak Jan 2024 PREMIUM│  ← Profile Block
│ ╰────╯  ● AKTIF SEKARANG             │
│ ┌──────┐ ┌──────┐ ┌──────┐          │
│ │WEIGHT│ │HEIGHT│ │ BMI  │          │  ← Vital Tiles (3)
│ │78 KG │ │180CM │ │24.1  │          │
│ └──────┘ └──────┘ └──────┘          │
│ ┃┌─────────────────────────────────┐ │
│ ┃│ FITNESS TARGET     ░HYPER░      │ │  ← Fitness Target Card
│ ┃│ Hypertrophy Focus       (🏋)    │ │  (rail kuning + watermark)
│ ┃│ Fokus pada peningkatan massa…   │ │
│ ┃└─────────────────────────────────┘ │
│ Program Berjalan                     │  ← Section header
│ 6-Week Mass Builder           65%    │
│ Minggu 4 dari 6 • Sesi 18/24 COMPLETED│
│ ▓▓▓▓▓▓▓▓▓▓░░░░░                      │  ← Progress bar
│ ┌────────────┐ ┌────────────┐        │
│ │NEXT SESSION│ │ SCHEDULE   │        │  ← Info Tiles (2)
│ │Chest&Tricep│ │Tomorrow 08 │        │
│ └────────────┘ └────────────┘        │
│ Riwayat Sesi Terakhir                │  ← Section header
│ ┌──────────────────────────────────┐ │
│ │ [📅] Back & Biceps Elite 480 kcal│ │  ← History Card
│ │      KEMARIN • 72 MENIT       >  │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [📅] Leg Power Drive    520 kcal │ │  ← History Card
│ │      3 HARI LALU • 65 MENIT   >  │ │
│ └──────────────────────────────────┘ │
├──────────────────────────────────────┤
│ 🏠     📅     👥      ⚡      👤    │  ← Bottom Tab Bar (TRAINER)
│ HOME JADWAL KLIEN PROGRAM PROFIL     │  ← KLIEN active
└──────────────────────────────────────┘
```

---

## 5. KOMPONEN: HEADER

### 5.1 Container
```
Display:        flex, align-items center, justify-content space-between
Padding:        16px
Margin-top:     safe-area-inset-top
```

### 5.2 Kiri — Back + Title
```
Display:        flex, align-items center, gap 12px

Back Button:
  Icon:         ← arrow-left, 22px, color #F5C518
  Size:         40px × 40px touch target

Title:
  Text:         "NAUFAL"  (nama klien, uppercase)
  Font-size:    20px, weight 800, uppercase, letter-spacing 0.5px, color #F5C518
```

### 5.3 Kanan — Overflow Menu
```
Size:           40px × 40px (icon-only)
Icon:           ⋮ vertical-dots, 20px, color #F5C518
Display:        flex center
```

---

## 6. KOMPONEN: PROFILE BLOCK

### 6.1 Container
```
Display:        flex, align-items flex-start, gap 16px
Padding:        8px 16px 0
Margin-bottom:  24px
Position:       relative  (untuk shield premium di kanan)
```

### 6.2 Avatar + Ring
```
Avatar:
  Size:         80px × 80px, border-radius 50%, object-fit cover
Ring:
  Border:       2.5px solid #F5C518, padding 3px (gap ke foto)
```

### 6.3 Info (flex 1)
```
Name:
  Text:         "Naufal Raharjo"  (wrap 2 baris) → 24px, weight 800, color #FFFFFF, letter-spacing -0.3px

Member Since:
  Text:         "Member sejak Jan 2024" → 14px, weight 400, color #9A9A9A, margin-top 4px

Status Row (flex, align center, gap 6px, margin-top 6px):
  Dot:          8px circle, background #34D058 (hijau)
  Text:         "AKTIF SEKARANG" → 12px, weight 700, uppercase, letter-spacing 0.5px, color #34D058
```

### 6.4 Premium Badge + Shield (kanan atas)
```
Shield:
  Icon:         shield outline, ~64px, color rgba(245,197,24,0.20) (dekoratif, subtle)
  Position:     absolute, top-right

Badge "PREMIUM" (di atas/dalam shield):
  Font:         10px, weight 800, uppercase, letter-spacing 0.8px, color #F5C518
  Background:   rgba(245,197,24,0.12), padding 4px 10px, border-radius 8px
```

---

## 7. KOMPONEN: VITAL STATS TILES (3 kolom)

### 7.1 Container
```
Display:        flex, gap 12px
Padding:        0 16px
Margin-bottom:  24px
```

### 7.2 Vital Tile (×3, equal width)
```
Flex:           1
Background:     #161616
Border:         1px solid #262626
Border-radius:  12px
Padding:        16px 12px
Display:        flex, flex-direction column, align-items center, gap 8px

Label:          "WEIGHT" / "HEIGHT" / "BMI" → 10px, weight 600, uppercase, letter-spacing 0.8px, color #9A9A9A
Value Row (baseline):
  Number:       28px, weight 800
                - "78" → color #F5C518 (highlight kuning — metrik utama)
                - "180" / "24.1" → color #FFFFFF
  Unit:         "KG" / "CM" → 12px, weight 600, color #9A9A9A, margin-left 2px
                (BMI tanpa unit)
```

---

## 8. KOMPONEN: FITNESS TARGET CARD

### 8.1 Container
```
Background:     #161616  (subtle gradient ke #1E1A0A boleh)
Border:         1px solid #262626
Border-left:    3px solid #F5C518   (accent rail)
Border-radius:  16px
Padding:        20px
Margin:         0 16px 24px
Position:       relative
Overflow:       hidden  (untuk crop watermark)
```

### 8.2 Watermark Dekoratif
```
Text:           "HYPER"
Font-size:      80px, weight 900, color rgba(245,197,24,0.06)
Position:       absolute, bottom-right, melewati tepi
Text-transform: uppercase, z-index 0, pointer-events none
```

### 8.3 Konten
```
Supra-label:
  Text:         "FITNESS TARGET" → 11px, weight 600, uppercase, letter-spacing 1.5px, color #9A9A9A

Title Row (flex, justify-content space-between, align-items center):
  Title:        "Hypertrophy Focus" → 26px, weight 800, color #FFFFFF, letter-spacing -0.5px, margin-top 6px
  Icon Badge:   48px circle, background #F5C518, icon 🏋 dumbbell 22px color #0E0E0E

Description:
  Text:         "Fokus pada peningkatan massa otot dan kepadatan serat otot."
  Font-size:    13px, weight 400, color #9A9A9A, line-height 1.5, margin-top 8px
```

---

## 9. KOMPONEN: PROGRAM BERJALAN

### 9.1 Section Header
```
Display:        flex, justify-content space-between, align-items baseline
Padding:        0 16px
Margin-bottom:  16px

Judul:
  Text:         "Program Berjalan"  → 20px, weight 800, #FFFFFF

Link:
  Text:         "LIHAT PROGRAM LENGKAP"
  Font-size:    11px, weight 700, uppercase, letter-spacing 0.5px, color #F5C518
```

### 9.2 Program Info Row
```
Display:        flex, justify-content space-between, align-items flex-start
Padding:        0 16px

Kiri:
  Name:         "6-Week Mass Builder" → 18px, weight 700, color #FFFFFF
  Meta:         "Minggu 4 dari 6 • Sesi 18/24" → 13px, weight 500, color #9A9A9A, margin-top 4px

Kanan:
  Percentage:   "65%" → 32px, weight 800, color #F5C518, letter-spacing -1px
  Status:       "COMPLETED" → 10px, weight 600, uppercase, letter-spacing 0.8px, color #9A9A9A
```

### 9.3 Progress Bar
```
Margin:         12px 16px 24px
Height:         8px
Border-radius:  999px
Track:          background #2A2A2A (100% width)
Fill:           background #F5C518, width 65%, border-radius 999px
```

### 9.4 Info Tiles (2 kolom)
```
Display:        flex, gap 12px
Padding:        0 16px
Margin-bottom:  24px

Tile (×2, flex 1):
  Background:   #1C1C1C
  Border:       1px solid #262626
  Border-radius:12px
  Padding:      14px
  Display:      flex, align-items center, gap 10px

  Icon:         16px, color #F5C518 (📅 calendar / ⏱ clock)
  Text block:
    Label:      "NEXT SESSION" / "SCHEDULE" → 10px, weight 600, uppercase, color #9A9A9A
    Value:      "Chest & Triceps" / "Tomorrow, 08:00" → 14px, weight 700, color #FFFFFF
```

---

## 10. KOMPONEN: RIWAYAT SESI TERAKHIR

### 10.1 Section Header
```
Text:           "Riwayat Sesi Terakhir"
Font-size:      20px, weight 800, color #FFFFFF
Padding:        0 16px
Margin-bottom:  12px
```

### 10.2 History Card
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Padding:        16px
Margin:         0 16px 12px
Display:        flex, align-items center, gap 12px

Icon Thumbnail:
  Size:         44px × 44px, border-radius 12px
  Background:   #1C1C1C
  Icon:         📅 calendar, 20px, color #9A9A9A

Info (flex 1):
  Name:         "Back & Biceps Elite" / "Leg Power Drive" → 16px, weight 700, color #FFFFFF
  Meta:         "KEMARIN • 72 MENIT" / "3 HARI LALU • 65 MENIT" → 11px, weight 500, uppercase, color #9A9A9A

Kanan:
  Kalori:       "480 kcal" / "520 kcal" → 14px, weight 800, color #F5C518
  Chevron:      > chevron-right, 16px, color #6B6B6B, margin-top 4px
```

---

## 11. KOMPONEN: BOTTOM TAB BAR (TRAINER VARIANT)

### 11.1 Container
```
Position:       fixed, bottom 0, left 0, right 0
Height:         72px (+ safe-area-inset-bottom)
Background:     #121212
Border-top:     1px solid #1E1E1E
Box-shadow:     0 -2px 12px rgba(0,0,0,0.5)
Display:        flex, justify-content space-around, align-items center
Z-index:        100
```

### 11.2 Tab Item (Default / Inactive)
```
Display:        flex, flex-direction column, align-items center, gap 4px
Icon:           22px, color #6B6B6B
Label:          9px, weight 600, uppercase, letter-spacing 0.5px, color #6B6B6B
```

### 11.3 Tab Item (Active — KLIEN)
```
Icon:           22px, color #F5C518
Label-color:    #F5C518
Indicator:      highlight pill bg di belakang ikon KLIEN
                (bg rgba(245,197,24,0.12), border-radius 12px)
```

### 11.4 Daftar Tabs (5 item — VERSI TRAINER, berbeda dari Member)
```
1. 🏠  HOME
2. 📅  JADWAL
3. 👥  KLIEN       ← ACTIVE (kuning)
4. ⚡  PROGRAM
5. 👤  PROFIL
```

---

## 12. GRID RECAP — RINGKASAN ZONA LAYOUT (Mobile)

| Zone                    | X Offset | Y Offset  | Width            | Height    |
|-------------------------|----------|-----------|------------------|-----------|
| Header                  | 0        | safe-top  | 100%             | ~64px     |
| Profile Block           | 16px     | ~116px    | calc(100% - 32px)| ~120px    |
| Vital Stats Tiles (×3)  | 16px     | ~252px    | calc(100% - 32px)| ~88px     |
| Fitness Target Card     | 16px     | ~356px    | calc(100% - 32px)| ~160px    |
| Program Berjalan Header  | 16px     | ~532px    | calc(100% - 32px)| ~30px     |
| Program Info + Progress | 16px     | ~578px    | calc(100% - 32px)| ~90px     |
| Info Tiles (×2)         | 16px     | ~684px    | calc(100% - 32px)| ~70px     |
| Riwayat Header          | 16px     | ~778px    | calc(100% - 32px)| ~30px     |
| History Card ×2         | 16px     | ~824px    | calc(100% - 32px)| ~76px each|
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px      |

*Catatan: konten melebihi tinggi viewport (932px) → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 13. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Client Details Screen (Detail Klien, Pro Trainer, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Client Details.png
   Generated: 2026-06-27
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:        #0E0E0E;
  --color-bg-card:           #1A1A1A;
  --color-bg-card-alt:       #161616;
  --color-bg-chip:           #1C1C1C;
  --color-bg-navbar:         #121212;
  --color-accent-primary:    #F5C518;
  --color-accent-hover:      #E0B200;
  --color-status-online:     #34D058;
  --color-text-primary:      #FFFFFF;
  --color-text-secondary:    #9A9A9A;
  --color-text-muted:        #6B6B6B;
  --color-text-on-accent:    #0E0E0E;
  --color-vital-number:      #FFFFFF;
  --color-vital-number-hl:   #F5C518;
  --color-badge-premium:     #F5C518;
  --color-badge-premium-bg:  rgba(245,197,24,0.12);
  --color-watermark:         rgba(245,197,24,0.06);
  --color-target-icon-bg:    #F5C518;
  --color-progress-fill:     #F5C518;
  --color-progress-track:    #2A2A2A;
  --color-progress-number:   #F5C518;
  --color-kcal:              #F5C518;
  --color-link:              #F5C518;
  --color-accent-rail:       #F5C518;
  --color-border-card:       #262626;
  --color-border-chip:       #2A2A2A;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.45);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-screen-title:       20px;
  --text-client-name:        24px;
  --text-member-since:       14px;
  --text-status:             12px;
  --text-premium-badge:      10px;
  --text-vital-label:        10px;
  --text-vital-number:       28px;
  --text-vital-unit:         12px;
  --text-target-supra:       11px;
  --text-target-title:       26px;
  --text-target-desc:        13px;
  --text-watermark:          80px;
  --text-section-title:      20px;
  --text-link:               11px;
  --text-program-name:       18px;
  --text-program-meta:       13px;
  --text-progress-number:    32px;
  --text-progress-status:    10px;
  --text-tile-label:         10px;
  --text-tile-value:         14px;
  --text-history-name:       16px;
  --text-history-meta:       11px;
  --text-kcal:               14px;
  --text-tab-label:          9px;

  /* ── SPACING ── */
  --space-xs:                4px;
  --space-sm:                8px;
  --space-md:                12px;
  --space-base:              16px;
  --space-lg:                20px;
  --space-xl:                24px;
  --space-2xl:               32px;

  /* ── BORDER RADIUS ── */
  --radius-sm:               8px;
  --radius-md:               12px;
  --radius-lg:               16px;
  --radius-pill:             999px;
  --radius-full:             50%;

  /* ── SHADOWS ── */
  --shadow-card:             0 2px 8px rgba(0,0,0,0.4);
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --navbar-height:           72px;
  --card-gap:                12px;
  --card-radius:             16px;
  --vital-tile-count:        3;
  --tab-count:               5;
}
```

---

## 14. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Client Details.png`. Semua teks (NAUFAL, Naufal Raharjo, Member sejak Jan 2024, AKTIF SEKARANG, PREMIUM, WEIGHT 78 KG, HEIGHT 180 CM, BMI 24.1, FITNESS TARGET, Hypertrophy Focus, Fokus pada peningkatan massa otot dan kepadatan serat otot., Program Berjalan, LIHAT PROGRAM LENGKAP, 6-Week Mass Builder, Minggu 4 dari 6 • Sesi 18/24, 65% COMPLETED, NEXT SESSION Chest & Triceps, SCHEDULE Tomorrow 08:00, Riwayat Sesi Terakhir, Back & Biceps Elite, KEMARIN • 72 MENIT, 480 kcal, Leg Power Drive, 3 HARI LALU • 65 MENIT, 520 kcal) harus persis sama dengan gambar.

2. **TRAINER SIDE (Bukan Member)**: Bagian dari keluarga Trainer-side (lihat HOME_PT_DASHBOARD, TRAINER_SCHEDULE & CLIENT_LIST). Dibuka dari "Lihat Detail" pada Client List. Bottom tab bar trainer: **HOME / JADWAL / KLIEN / PROGRAM / PROFIL** dengan KLIEN aktif.

3. **Status Online (Hijau)**: Status dot hijau `#34D058` + "AKTIF SEKARANG" menandai klien sedang online/aktif. Ini aksen warna tambahan (selain cyan di Client List). Catat token `--color-status-online`; gunakan konsisten untuk indikator presence.

4. **Mobile-First Layout**: Detail klien, konten scrollable vertikal. Navigasi via header back (kembali ke Client List) + overflow menu untuk aksi lanjutan (edit/hapus/pesan). Gunakan `safe-area-inset-*`.

5. **Header Nama Klien**: Judul header memakai nama klien ("NAUFAL", uppercase) — pola screen-detail (seperti Session Detail Self yang memakai konteks di header). Back button kembali ke daftar.

6. **Profile Block + Premium Shield**: Avatar 80px ber-ring kuning, nama lengkap, member-since, status online. Badge "PREMIUM" disertai ikon shield dekoratif subtle di kanan — menandai tier keanggotaan. Shield bersifat ornamen (opacity rendah), badge teks yang utama.

7. **Vital Stats Highlight Selektif**: Tiga tile (Weight/Height/BMI). "78" (weight) di-highlight kuning sebagai metrik fokus; "180" & "24.1" putih netral. Pola highlight selektif konsisten dengan hierarki warna di layar lain (kuning = metrik utama).

8. **Fitness Target Card + Watermark**: Kartu target dengan accent rail kiri, supra-label, judul besar "Hypertrophy Focus", ikon dumbbell dalam circle kuning, deskripsi, dan watermark "HYPER" raksasa opacity rendah. Wajib `overflow:hidden` + `pointer-events:none` pada watermark. Konsisten dengan focus card di Session Detail.

9. **Program Berjalan**: Menampilkan program aktif klien dengan nama, meta (minggu/sesi), persentase besar "65%" + "COMPLETED", dan progress bar. Link "LIHAT PROGRAM LENGKAP" membuka detail program penuh. Gunakan `role="progressbar"` + `aria-valuenow="65"`.

10. **Info Tiles (Next Session/Schedule)**: Dua tile menampilkan sesi berikutnya (Chest & Triceps) dan jadwalnya (Tomorrow, 08:00) dengan ikon. Memberi trainer konteks cepat rencana terdekat klien.

11. **Riwayat Sesi + Kalori**: Daftar sesi terakhir dengan thumbnail, nama, meta (relatif: KEMARIN/3 HARI LALU + durasi), dan kalori terbakar (kuning). Chevron menandai bisa dibuka untuk detail sesi. Render meta waktu relatif dinamis.

12. **Relasi dengan Client List**: Layar ini detail dari kartu klien di Client List. Data (nama, tier, program, progress) harus sinkron. Catatan: di Client List nama klien lain (Sarah/Marcus/Elena); di sini contoh klien "Naufal" (selaras dengan klien di Home PT Dashboard).

13. **Scroll & Padding**: Konten lebih tinggi dari viewport → scroll vertikal. Beri `padding-bottom:88px` agar history card terbawah tidak tertutup tab bar. Header boleh sticky agar back button selalu terjangkau.

14. **Accessibility**: Beri `aria-current="page"` pada tab KLIEN. Status online sertakan teks ("Aktif sekarang"), jangan andalkan dot hijau saja. Progress bar gunakan `role="progressbar"` + `aria-valuenow`. Premium badge & vital stats sertakan label teks jelas. Pastikan kontras hijau `#34D058` & kuning di atas latar gelap memenuhi WCAG AA. Overflow menu beri `aria-haspopup="menu"`. History card & link beri `aria-label` jelas. Touch target minimum 44×44px.

---

*Spec ini generated dari analisis visual screen Client Details.png (visual-verified).*
*Design system reference: Egg Gym — Client List (CLIENT_LIST_UI_SPEC.md), Home PT Dashboard, Trainer Schedule & Member specs. CATATAN: sisi TRAINER, tab bar HOME/JADWAL/KLIEN/PROGRAM/PROFIL; status online hijau #34D058.*
*Total sections: 14 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

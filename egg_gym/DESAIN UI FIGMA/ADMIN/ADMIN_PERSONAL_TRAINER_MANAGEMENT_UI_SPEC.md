# ADMIN_PERSONAL_TRAINER_MANAGEMENT_UI_SPEC.md
# Egg Gym App — Admin Personal Trainer Management Screen
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Admin > Personal Trainer Management (Data Personal Trainer)
# Resolution: 1286 × 1024 px
# Last Updated: 2026-06-27
# Source of truth: Admin Personal Trainer Management.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar ini memakai latar NETRAL GELAP (near-black) dengan aksen kuning emas,
konsisten dengan Payments screen. Coach card memakai panel abu sangat gelap.

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0F0F0F               | Main content background                        |
| --color-bg-card           | #1A1A1A               | Coach card & panel background                  |
| --color-bg-card-inner     | #141414               | Inner stat box (Klien Aktif / Status)          |
| --color-bg-banner         | #161616               | Performance banner background                  |
| --color-bg-sidebar        | #0D0D0D               | Sidebar background                             |
| --color-bg-input          | #1C1C1C               | Search bar background                          |
| --color-bg-queue          | #161616               | "Other Trainers Queue" table background        |
| --color-bg-row-hover      | #1E1E1E               | Table row hover                                |
| --color-accent-primary    | #F5C518               | Active nav, CTA, ratings, active filter        |
| --color-accent-hover      | #E0B200               | Button hover state                             |
| --color-text-primary      | #FFFFFF               | Headings, coach names, primary values          |
| --color-text-secondary    | #9A9A9A               | Labels, captions, column headers               |
| --color-text-muted        | #6B6B6B               | Placeholder, sub-text, watermark hint          |
| --color-text-on-accent    | #0F0F0F               | Text on yellow/accent elements                 |
| --color-status-active     | #4CAF50               | "AKTIF" / "ACTIVE" status dot & text           |
| --color-status-leave      | #F5C518               | "ON LEAVE" status badge                        |
| --color-specialist-text   | #F5C518               | Specialist sub-label (kuning)                  |
| --color-watermark         | rgba(255,255,255,0.04)| Watermark "PERFORMANCE" di banner              |
| --color-border-card       | #262626               | Card & panel borders                           |
| --color-border-inner      | #2A2A2A               | Inner stat box border                          |
| --color-border-row        | #1E1E1E               | Table row separators                           |
| --color-avatar-bg         | #2A2A2A               | Queue avatar placeholder background            |
| --color-tier-elite        | #F5C518               | "ELITE" tier badge (kuning solid)              |
| --color-tier-pro          | #F5C518               | "PRO" tier badge (kuning solid)                |
| --color-overlay-dark      | rgba(0,0,0,0.7)       | Modal backdrop                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Monospace:  "JetBrains Mono", "Fira Code", monospace  (untuk angka stat)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-sidebar-brand     | 20px | 800    | 1.1    | 0px              | "Editorial Athletics" brand        |
| --text-sidebar-sub       | 10px | 600    | 1.2    | 2px (uppercase)  | "ELITE MANAGEMENT" sub-brand       |
| --text-breadcrumb        | 16px | 800    | 1.0    | 1.5px (uppercase)| "DATA PERSONAL TRAINER" header     |
| --text-banner-watermark  | 110px| 800    | 1.0    | 2px              | Watermark "PERFORMANCE" di banner  |
| --text-banner-label      | 11px | 600    | 1.3    | 1.5px (uppercase)| "TOTAL ACTIVE COACHES" label       |
| --text-banner-value      | 44px | 800    | 1.0    | -1px             | Angka besar banner (42, 4.85)      |
| --text-card-name         | 22px | 800    | 1.2    | 0px              | Nama coach di card                 |
| --text-card-specialist   | 11px | 700    | 1.2    | 1px (uppercase)  | "HYPERTROPHY SPECIALIST" sub-label |
| --text-card-rating       | 18px | 800    | 1.0    | 0px              | Rating global di card (4.9 ★)      |
| --text-rating-label      | 9px  | 600    | 1.2    | 1px (uppercase)  | "GLOBAL RATING" mini label         |
| --text-stat-label        | 9px  | 600    | 1.2    | 1px (uppercase)  | "KLIEN AKTIF" / "STATUS" label     |
| --text-stat-value        | 20px | 800    | 1.0    | 0px              | Angka klien aktif (24)             |
| --text-stat-max          | 11px | 400    | 1.2    | 0px              | "/ 30 Max" suffix                  |
| --text-filter-tab        | 11px | 700    | 1.0    | 1px (uppercase)  | Label filter tab specialist        |
| --text-button-detail     | 11px | 700    | 1.0    | 0.5px (uppercase)| "LIHAT DETAIL" / "EDIT PROFIL"     |
| --text-button-cta        | 13px | 700    | 1.0    | 0.5px (uppercase)| "REGISTER NEW COACH" button        |
| --text-tier-badge        | 10px | 800    | 1.0    | 1px (uppercase)  | "ELITE" / "PRO" tier badge         |
| --text-section-title     | 14px | 700    | 1.2    | 1px (uppercase)  | "OTHER TRAINERS QUEUE" heading     |
| --text-th                | 11px | 700    | 1.2    | 1px (uppercase)  | Table column headers               |
| --text-queue-name        | 14px | 700    | 1.3    | 0px              | Nama coach di queue table          |
| --text-queue-sub         | 11px | 400    | 1.3    | 0px              | "Joined June 2023" sub-text        |
| --text-cell              | 13px | 400    | 1.4    | 0px              | Isi sel umum (specialty)           |
| --text-badge             | 10px | 700    | 1.0    | 0.5px (uppercase)| Status badges di queue             |
| --text-nav-item          | 14px | 500    | 1.4    | 0px              | Sidebar navigation items           |
| --text-search            | 13px | 400    | 1.0    | 0px              | Search bar input                   |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Badge padding, tiny gaps                         |
| --space-sm     | 8px   | Inline label gaps, icon-text gap                 |
| --space-md     | 12px  | Inner stat box gap, button gap                   |
| --space-base   | 16px  | Standard component margin                        |
| --space-lg     | 20px  | Card gap, section spacing                        |
| --space-xl     | 24px  | Card padding, page horizontal padding            |
| --space-2xl    | 32px  | Major section separation                         |
| --space-3xl    | 40px  | Page top padding                                 |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-xs    | 4px   | Tier badges, small chips                         |
| --radius-sm    | 6px   | Buttons, inner stat boxes, icon buttons          |
| --radius-md    | 10px  | Coach cards, banner, queue table                 |
| --radius-lg    | 14px  | Avatar coach (rounded square)                    |
| --radius-pill  | 999px | Filter tabs, status badges                       |
| --radius-full  | 50%   | Sidebar/header avatar circles, status dot        |

### Box Shadows
| Token            | Value                              | Usage                        |
|------------------|------------------------------------|------------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)         | Coach cards default          |
| --shadow-button  | 0 2px 8px rgba(245,197,24,0.3)    | Register New Coach CTA       |
| --shadow-banner  | 0 1px 4px rgba(0,0,0,0.3)         | Performance banner           |
| --shadow-modal   | 0 8px 32px rgba(0,0,0,0.7)        | Modal overlays               |

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Total Canvas:   1286 × 1024 px
Sidebar:        240px wide × 100vh (fixed)
Header Bar:     calc(100vw - 240px) × 64px (sticky)
Main Content:   calc(100vw - 240px) width, padding: 32px
Page Padding:   32px
Content Gap:    24px
Coach Cards:    2 kolom (repeat(2, 1fr))
```

### ASCII Layout Diagram
```
┌─────────────────────┬────────────────────────────────────────────────────────┐
│  SIDEBAR (240px)    │  HEADER (64px)                                         │
│  Editorial          │  DATA PERSONAL TRAINER  [🔍 Search coach...]  🔔 ❓ 👤 │
│  Athletics          ├────────────────────────────────────────────────────────┤
│  ELITE MANAGEMENT   │  ┌──────────────────────────────────────────────────┐  │
│  ───────────────    │  │ (watermark "PERFORMANCE")                        │  │
│  ⊞ Dashboard        │  │ TOTAL ACTIVE COACHES  AVG.SATISFACTION  [REGISTER│  │
│  👥 Member          │  │      42                  4.85          NEW COACH]│  │
│  💳 Paket Membership│  └──────────────────────────────────────────────────┘  │
│  ⭐ Personal Trainer│  [ALL SPECIALISTS][HYPERTROPHY][POWERLIFT][MOBILITY]   │
│      ◄AKTIF         │                              ⌕ Advanced Filters       │
│  ☑ Booking & Sesi PT│  ┌─────────────────────┐ ┌─────────────────────┐       │
│  💳 Pembayaran      │  │ [foto] Coach Adrian │ │ [foto] Coach Marcus │       │
│  💠 Alat Gym        │  │  HYPERTROPHY  4.9★  │ │  POWERLIFTING  4.8★ │       │
│  🗂 Audit Trail     │  │  [KLIEN 24][STATUS] │ │  [KLIEN 18][STATUS] │       │
│  📊 Laporan         │  │  LIHAT|EDIT|📅|🚫   │ │  LIHAT|EDIT|📅|🚫   │       │
│  ⚙ Pengaturan       │  │  [ELITE]            │ │  [PRO]              │       │
│  ───────────────    │  └─────────────────────┘ └─────────────────────┘       │
│  [👤] Admin Panel   │  ┌──────────────────────────────────────────────────┐  │
│  SUPERUSER          │  │ OTHER TRAINERS QUEUE        VIEWING 2 OF 42 COACHES│  │
│                     │  │ COACH│SPECIALTY│RATING│CLIENTS│STATUS│ACTIONS     │  │
│                     │  │ Sarah│Yoga     │4.7★  │31     │ACTIVE│⋮           │  │
│                     │  │ David│Functional│4.5★ │12     │ONLEAVE│⋮          │  │
│                     │  └──────────────────────────────────────────────────┘  │
└─────────────────────┴────────────────────────────────────────────────────────┘
```

---

## 5. KOMPONEN: SIDEBAR

### 5.1 Container Sidebar
```
Width:          240px
Height:         100vh
Background:     #0D0D0D
Border-right:   1px solid #1E1E1E
Position:       fixed, left: 0, top: 0
Z-index:        200
Display:        flex flex-column
Padding:        24px 0
```

### 5.2 Area Brand
```
Padding:        0 24px 24px
Brand Name:
  Text:         "Editorial Athletics"
  Font-size:    20px
  Font-weight:  800
  Color:        #F5C518
Sub-brand:
  Text:         "ELITE MANAGEMENT"
  Font-size:    10px
  Font-weight:  600
  Color:        #9A9A9A
  Letter-spacing:2px
  Text-transform:uppercase
  Margin-top:   4px
```

### 5.3 Menu Item (Default State)
```
Display:        flex, align-items center
Padding:        12px 24px
Gap:            14px
Icon-color:     #9A9A9A
Text:
  Font-size:    14px
  Font-weight:  500
  Color:        #9A9A9A
Hover:
  Color:        #FFFFFF
  Icon-color:   #F5C518
```

### 5.4 Menu Item (Active State — Personal Trainer)
```
Icon-color:     #F5C518
Text-color:     #F5C518
Font-weight:    600
Indicator:      garis vertikal kuning #F5C518 (3px) di sisi kanan item aktif
```

### 5.5 Daftar Navigation Items (Urutan FINAL — sesuai gambar)
```
1.  ⊞  Dashboard
2.  👥  Member
3.  💳  Paket Membership
4.  ⭐  Personal Trainer    ← ACTIVE (screen ini)
5.  ☑  Booking & Sesi PT
6.  💳  Pembayaran
7.  💠  Alat Gym
8.  🗂  Audit Trail
9.  📊  Laporan
10. ⚙  Pengaturan
```

### 5.6 Profile Area (Bottom)
```
Position:       margin-top auto
Padding:        16px 24px
Border-top:     1px solid #1E1E1E
Display:        flex, align-items center, gap 12px

Avatar:
  Width/Height: 40px
  Border-radius:50%
  Content:      foto profil (real photo)

Name:
  Text:         "Admin Panel"
  Font-size:    14px
  Font-weight:  700
  Color:        #FFFFFF
Role:
  Text:         "SUPERUSER"
  Font-size:    10px
  Font-weight:  600
  Color:        #9A9A9A
  Letter-spacing:1px
```

---

## 6. KOMPONEN: TOP HEADER BAR

### 6.1 Container
```
Height:         64px
Background:     transparan (menyatu dengan #0F0F0F)
Padding:        0 32px
Display:        flex, align-items center, justify-content space-between
Position:       sticky, top 0
Z-index:        100
Width:          calc(100vw - 240px)
```

### 6.2 Kiri — Breadcrumb / Page Title
```
Text:           "DATA PERSONAL TRAINER"
Font-size:      16px
Font-weight:    800
Color:          #F5C518
Letter-spacing: 1.5px
Text-transform: uppercase
```

### 6.3 Tengah/Kanan — Search Bar
```
Container:
  Width:        ~250px
  Height:       40px
  Background:   #1C1C1C
  Border:       1px solid #262626
  Border-radius:6px
  Padding:      0 14px
  Gap:          10px
Search Icon:
  Color:        #6B6B6B
Input:
  Placeholder:  "Search coach..."
  Placeholder-color: #6B6B6B
  Color:        #FFFFFF
  Font-size:    13px
Focus:
  Border:       1px solid #F5C518
```

### 6.4 Kanan — Action Icons
```
Display:        flex, align-items center, gap 18px

Notification Bell:
  Icon-size:    20px
  Color:        #9A9A9A
  Hover-color:  #F5C518

Help Icon (?):
  Icon-size:    20px
  Shape:        lingkaran outline dengan tanda tanya
  Color:        #9A9A9A
  Hover-color:  #F5C518

Profile Avatar:
  Width/Height: 32px
  Border-radius:50%
  Border:       1px solid #F5C518 (ring tipis)
  Content:      foto profil (real photo)
```

---

## 7. KOMPONEN: PERFORMANCE BANNER (Hero Stats)

### 7.1 Container
```
Background:     #161616
Border:         1px solid #262626
Border-radius:  10px
Padding:        32px
Position:       relative
Overflow:       hidden
Display:        flex, align-items center, justify-content space-between
Margin-bottom:  24px
Min-height:     150px
```

### 7.2 Watermark (di belakang konten)
```
Text:           "PERFORMANCE"
Font-size:      110px
Font-weight:    800
Color:          rgba(255,255,255,0.04)
Text-transform: uppercase
Letter-spacing: 2px
Position:       absolute, center, di belakang stats
Z-index:        0
Pointer-events: none
White-space:    nowrap
```

### 7.3 Kiri — Stat Group (z-index 1)
```
Display:        flex, gap 64px

Stat Item:
  Label:
    Font-size:  11px
    Font-weight:600
    Color:      #9A9A9A
    Letter-spacing:1.5px
    Text-transform:uppercase
    Margin-bottom:8px
  Value:
    Font-size:  44px
    Font-weight:800
    Color:      #FFFFFF
    Line-height:1.0

Data:
  Stat 1: label "TOTAL ACTIVE COACHES", value "42"
  Stat 2: label "AVG. CLIENT SATISFACTION", value "4.85"
          (catatan: ada ikon bintang kecil kuning di samping 4.85)
```

### 7.4 Kanan — Tombol "REGISTER NEW COACH"
```
Text:           "REGISTER NEW COACH"
Leading-icon:   👤+ (add person), 16px
Font-size:      13px
Font-weight:    700
Color:          #0F0F0F
Background:     #F5C518
Border-radius:  6px
Padding:        14px 24px
Letter-spacing: 0.5px
Text-transform: uppercase
Box-shadow:     0 2px 8px rgba(245,197,24,0.3)
Display:        flex, align-items center, gap 8px
Hover:
  Background:   #E0B200
  Transform:    translateY(-1px)
```

---

## 8. KOMPONEN: FILTER TAB BAR

### 8.1 Container
```
Display:        flex, align-items center, justify-content space-between
Margin-bottom:  20px
```

### 8.2 Kiri — Filter Tabs (gap 10px)
```
Tab Default:
  Padding:      9px 18px
  Background:   #1C1C1C
  Border:       1px solid #262626
  Border-radius:999px (pill)
  Font-size:    11px
  Font-weight:  700
  Color:        #9A9A9A
  Letter-spacing:1px
  Text-transform:uppercase
  Hover:
    Color:      #FFFFFF
    Border-color:#3A3A3A

Tab Active (ALL SPECIALISTS):
  Background:   #F5C518
  Border:       1px solid #F5C518
  Color:        #0F0F0F
  Font-weight:  700

Daftar Tabs:
  1. "ALL SPECIALISTS"  ← Active (kuning)
  2. "HYPERTROPHY"
  3. "POWERLIFTING"
  4. "MOBILITY"
```

### 8.3 Kanan — Advanced Filters
```
Text:           "Advanced Filters"
Leading-icon:   ⌕ / filter-lines icon, 16px
Font-size:      13px
Font-weight:    500
Color:          #9A9A9A
Cursor:         pointer
Hover:          color #F5C518
```

---

## 9. KOMPONEN: COACH CARD (Featured, 2-kolom)

### 9.1 Grid Container
```
Display:              grid
Grid-template-columns:repeat(2, 1fr)
Gap:                  20px
Margin-bottom:        24px

Breakpoint < 900px:   repeat(1, 1fr)
```

### 9.2 Card Container
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  10px
Padding:        20px
Display:        flex, gap 18px
Position:       relative
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
Hover:
  Border-color: rgba(245,197,24,0.3)
```

### 9.3 Kiri — Foto Coach
```
Width:          150px
Height:         ~190px (potret)
Border-radius:  14px
Object-fit:     cover
Flex-shrink:    0
Position:       relative   (untuk tier badge overlay)
```

### 9.4 Tier Badge (overlay kiri-bawah foto / di bawah foto)
```
Position:       absolute, bottom 0, left 0 (atau di bawah foto)
Background:     #F5C518
Color:          #0F0F0F
Font-size:      10px
Font-weight:    800
Letter-spacing: 1px
Text-transform: uppercase
Padding:        4px 12px
Border-radius:  4px

Nilai:
  Coach Adrian → "ELITE"
  Coach Marcus → "PRO"
```

### 9.5 Kanan — Info Coach (flex column)
```
Header Row (nama + rating):
  Display:      flex, justify-content space-between, align-items flex-start

  Name:
    Text:       "Coach Adrian" / "Coach Marcus"
    Font-size:  22px
    Font-weight:800
    Color:      #FFFFFF
  Specialist sub-label:
    Text:       "HYPERTROPHY SPECIALIST" / "POWERLIFTING SPECIALIST"
    Font-size:  11px
    Font-weight:700
    Color:      #F5C518
    Letter-spacing:1px
    Text-transform:uppercase
    Margin-top: 4px

  Rating (kanan):
    Value:      "4.9 ★" / "4.8 ★"  → angka #FFFFFF, bintang #F5C518
    Font-size:  18px
    Font-weight:800
    Sub-label:  "GLOBAL RATING"
      Font-size:9px
      Color:    #9A9A9A
      Letter-spacing:1px
      Text-transform:uppercase
```

### 9.6 Inner Stat Boxes (Klien Aktif + Status)
```
Display:        flex, gap 12px, margin 16px 0

Box (masing-masing):
  Flex:         1
  Background:   #141414
  Border:       1px solid #2A2A2A
  Border-radius:6px
  Padding:      12px 14px

  Box 1 — Klien Aktif:
    Label:      "KLIEN AKTIF" (9px, #9A9A9A, uppercase)
    Value:      "24" (20px, 800, #FFFFFF) + suffix "/ 30 Max" (11px, #9A9A9A)
    Marcus:     "18" + "/ 25 Max"

  Box 2 — Status:
    Label:      "STATUS" (9px, #9A9A9A, uppercase)
    Value:      ● "AKTIF"  (dot 8px #4CAF50 + text #4CAF50, 13px, 700)
```

### 9.7 Footer — Action Buttons
```
Display:        flex, align-items center, gap 8px

LIHAT DETAIL (button):
  Font-size:    11px
  Font-weight:  700
  Color:        #FFFFFF
  Background:   #1C1C1C
  Border:       1px solid #2A2A2A
  Border-radius:6px
  Padding:      9px 14px
  Letter-spacing:0.5px
  Text-transform:uppercase

EDIT PROFIL (button):
  Style sama dengan LIHAT DETAIL

Icon Button — Kalender (📅):
  Size:         36px × 36px
  Background:   #1C1C1C
  Border:       1px solid #2A2A2A
  Border-radius:6px
  Icon:         16px, #9A9A9A
  Tooltip:      "Atur Jadwal"

Icon Button — Nonaktifkan (🚫):
  Size:         36px × 36px
  Background:   #1C1C1C
  Border:       1px solid #2A2A2A
  Border-radius:6px
  Icon:         16px, #9A9A9A
  Tooltip:      "Nonaktifkan Coach"
```

### 9.8 Data Contoh — Coach Cards (FINAL — sesuai gambar)
```
CARD 1 — Coach Adrian
  Specialist:   "HYPERTROPHY SPECIALIST"
  Rating:       "4.9 ★"  (GLOBAL RATING)
  Klien Aktif:  "24 / 30 Max"
  Status:       ● AKTIF
  Tier badge:   "ELITE"

CARD 2 — Coach Marcus
  Specialist:   "POWERLIFTING SPECIALIST"
  Rating:       "4.8 ★"  (GLOBAL RATING)
  Klien Aktif:  "18 / 25 Max"
  Status:       ● AKTIF
  Tier badge:   "PRO"
```

---

## 10. KOMPONEN: OTHER TRAINERS QUEUE (Table)

### 10.1 Container
```
Background:     #161616
Border:         1px solid #262626
Border-radius:  10px
Overflow:       hidden
```

### 10.2 Header Panel
```
Display:        flex, justify-content space-between, align-items center
Padding:        20px 24px
Border-bottom:  1px solid #262626

Judul (kiri):
  Text:         "OTHER TRAINERS QUEUE"
  Font-size:    14px
  Font-weight:  700
  Color:        #FFFFFF
  Letter-spacing:1px
  Text-transform:uppercase

Sub-label (kanan):
  Text:         "VIEWING 2 OF 42 COACHES"
  Font-size:    10px
  Font-weight:  600
  Color:        #9A9A9A
  Letter-spacing:1px
  Text-transform:uppercase
```

### 10.3 Table Header Row (THEAD)
```
Padding:        12px 24px
Border-bottom:  1px solid #1E1E1E

Header Cell (TH):
  Font-size:    11px
  Font-weight:  700
  Color:        #9A9A9A
  Letter-spacing:1px
  Text-transform:uppercase

Daftar Kolom (6):
  1. COACH NAME
  2. SPECIALTY
  3. RATING
  4. CLIENTS
  5. STATUS
  6. QUICK ACTIONS
```

### 10.4 Table Body Row (TR)
```
Padding:        16px 24px
Border-bottom:  1px solid #1E1E1E
Hover:          background #1E1E1E
Last row:       border-bottom none
```

### 10.5 Cell — Coach Name (Avatar + Nama + Sub)
```
Display:        flex, align-items center, gap 12px

Avatar:
  Width/Height: 36px
  Border-radius:50%
  Background:   #2A2A2A  (placeholder kosong / foto coach)

Teks:
  Nama:
    Font-size:  14px
    Font-weight:700
    Color:      #FFFFFF
  Sub:
    Text:       "Joined June 2023" / "Joined Feb 2024"
    Font-size:  11px
    Color:      #9A9A9A
```

### 10.6 Cell — Specialty / Rating / Clients
```
Specialty:
  Font-size:    13px
  Color:        #FFFFFF
  Contoh:       "Yoga & Mobility", "Functional Fitness"

Rating:
  Value + bintang: "4.7 ★" → angka #FFFFFF, bintang #F5C518
  Font-size:    13px

Clients:
  Font-size:    13px
  Color:        #FFFFFF
  Contoh:       "31", "12"
```

### 10.7 Cell — Status Badge
```
Display:        inline-flex, align-items center
Padding:        4px 12px
Border-radius:  4px
Font-size:      10px
Font-weight:    700
Letter-spacing: 0.5px
Text-transform: uppercase

Status → Style:
  ACTIVE:   bg rgba(76,175,80,0.15), text #4CAF50
  ON LEAVE: bg rgba(245,197,24,0.15), text #F5C518
```

### 10.8 Cell — Quick Actions (Kebab)
```
Icon:           ⋮ (three-dot vertical)
Size:           20px hitbox
Color:          #9A9A9A
Hover:          color #FFFFFF
Action:         context menu (Lihat Profil / Edit / Atur Jadwal / Nonaktifkan)
```

### 10.9 Data Contoh — Queue Rows (FINAL — sesuai gambar)
```
ROW 1:
  Coach: Coach Sarah (Joined June 2023)
  Specialty: Yoga & Mobility | Rating: 4.7 ★ | Clients: 31 | Status: ACTIVE

ROW 2:
  Coach: Coach David (Joined Feb 2024)
  Specialty: Functional Fitness | Rating: 4.5 ★ | Clients: 12 | Status: ON LEAVE
```

---

## 11. GRID RECAP — RINGKASAN ZONA LAYOUT

| Zone               | X Offset | Y Offset | Width                | Height    |
|--------------------|----------|----------|----------------------|-----------|
| Sidebar            | 0        | 0        | 240px                | 100vh     |
| Header Bar         | 240px    | 0        | calc(100vw - 240px)  | 64px      |
| Performance Banner | 272px    | 96px     | calc(100vw - 304px)  | ~150px    |
| Filter Tab Bar     | 272px    | 280px    | calc(100vw - 304px)  | ~42px     |
| Coach Cards (2-col)| 272px    | 350px    | calc(100vw - 304px)  | ~250px    |
| Trainers Queue     | 272px    | 630px    | calc(100vw - 304px)  | ~230px    |

---

## 12. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Admin Personal Trainer Management (Data Personal Trainer)
   CSS Custom Properties — Design Tokens
   Visual-verified: Admin Personal Trainer Management.png
   Generated: 2026-06-27
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:        #0F0F0F;
  --color-bg-card:           #1A1A1A;
  --color-bg-card-inner:     #141414;
  --color-bg-banner:         #161616;
  --color-bg-sidebar:        #0D0D0D;
  --color-bg-input:          #1C1C1C;
  --color-bg-queue:          #161616;
  --color-bg-row-hover:      #1E1E1E;
  --color-accent-primary:    #F5C518;
  --color-accent-hover:      #E0B200;
  --color-text-primary:      #FFFFFF;
  --color-text-secondary:    #9A9A9A;
  --color-text-muted:        #6B6B6B;
  --color-text-on-accent:    #0F0F0F;
  --color-status-active:     #4CAF50;
  --color-status-leave:      #F5C518;
  --color-specialist-text:   #F5C518;
  --color-watermark:         rgba(255,255,255,0.04);
  --color-border-card:       #262626;
  --color-border-inner:      #2A2A2A;
  --color-border-row:        #1E1E1E;
  --color-avatar-bg:         #2A2A2A;
  --color-tier-elite:        #F5C518;
  --color-tier-pro:          #F5C518;
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --font-family-mono:        "JetBrains Mono", "Fira Code", monospace;
  --text-sidebar-brand:      20px;
  --text-breadcrumb:         16px;
  --text-banner-watermark:   110px;
  --text-banner-label:       11px;
  --text-banner-value:       44px;
  --text-card-name:          22px;
  --text-card-specialist:    11px;
  --text-card-rating:        18px;
  --text-stat-label:         9px;
  --text-stat-value:         20px;
  --text-filter-tab:         11px;
  --text-button-detail:      11px;
  --text-button-cta:         13px;
  --text-tier-badge:         10px;
  --text-section-title:      14px;
  --text-th:                 11px;
  --text-queue-name:         14px;
  --text-badge:              10px;
  --text-nav-item:           14px;

  /* ── SPACING ── */
  --space-xs:                4px;
  --space-sm:                8px;
  --space-md:                12px;
  --space-base:              16px;
  --space-lg:                20px;
  --space-xl:                24px;
  --space-2xl:               32px;
  --space-3xl:               40px;

  /* ── BORDER RADIUS ── */
  --radius-xs:               4px;
  --radius-sm:               6px;
  --radius-md:               10px;
  --radius-lg:               14px;
  --radius-pill:             999px;
  --radius-full:             50%;

  /* ── SHADOWS ── */
  --shadow-card:             0 2px 8px rgba(0,0,0,0.4);
  --shadow-button:           0 2px 8px rgba(245,197,24,0.3);
  --shadow-banner:           0 1px 4px rgba(0,0,0,0.3);
  --shadow-modal:            0 8px 32px rgba(0,0,0,0.7);

  /* ── LAYOUT ── */
  --sidebar-width:           240px;
  --header-height:           64px;
  --page-padding:            32px;
  --coach-card-cols:         2;
  --coach-card-gap:          20px;
  --content-gap:             24px;
  --coach-photo-width:       150px;
}
```

---

## 13. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Admin Personal Trainer Management.png`. Semua nama coach (Adrian, Marcus, Sarah, David), rating, jumlah klien, status, dan tier badge harus persis sama dengan gambar.

2. **Watermark "PERFORMANCE"​**: Render teks raksasa semi-transparan (`rgba(255,255,255,0.04)`, ~110px) di dalam banner, di belakang stat group. Gunakan `z-index: 0`, `pointer-events: none`, dan `overflow: hidden` pada container banner agar teks terpotong rapi di tepi.

3. **Banner Stats**: Dua KPI besar — "TOTAL ACTIVE COACHES = 42" dan "AVG. CLIENT SATISFACTION = 4.85" (dengan ikon bintang kuning kecil). Angka putih 44px, label abu uppercase di atasnya.

4. **Tier Badge**: "ELITE" (Adrian) dan "PRO" (Marcus) sama-sama kuning solid `#F5C518` dengan teks gelap. Posisinya overlay di area foto coach (kiri-bawah). Bedakan tier lewat teks, bukan warna.

5. **Specialist Color**: Sub-label spesialisasi ("HYPERTROPHY SPECIALIST", dst) selalu kuning `#F5C518` uppercase, langsung di bawah nama coach.

6. **Inner Stat Box Pattern**: Tiap coach card punya 2 kotak inner (Klien Aktif & Status) dengan bg lebih gelap `#141414`. Nilai klien pakai format "X / Y Max" — angka utama bold putih, suffix "/ Y Max" abu kecil.

7. **Status Dot**: Status "AKTIF" memakai dot hijau 8px (`#4CAF50`) + teks hijau. Animasi pulse opsional untuk menandakan real-time online.

8. **Coach Card Actions**: 4 elemen footer — 2 text button (LIHAT DETAIL, EDIT PROFIL) + 2 icon button (📅 atur jadwal, 🚫 nonaktifkan). Semua pakai bg `#1C1C1C` + border `#2A2A2A`.

9. **Filter Tabs Pill**: Tab specialist fully-rounded. "ALL SPECIALISTS" aktif solid kuning. "Advanced Filters" di kanan adalah link/teks dengan ikon filter, bukan pill.

10. **Register New Coach**: CTA kuning solid di kanan banner dengan ikon add-person. Klik → buka modal/form registrasi coach baru (nama, spesialisasi, tier, kapasitas klien, foto, dll).

11. **Queue Table vs Featured Card**: Dua coach unggulan tampil sebagai card besar; sisanya (40 coach) di tabel "OTHER TRAINERS QUEUE". Sub-label "VIEWING 2 OF 42 COACHES" harus dinamis mengikuti jumlah card yang ditampilkan.

12. **Queue Status Badge**: "ACTIVE" (hijau) dan "ON LEAVE" (kuning) memakai badge rounded-sm dengan bg transparan 15%. Konsisten dengan sistem status di seluruh admin.

13. **Responsive**: Coach cards turun ke 1 kolom < 900px. Queue table beralih ke horizontal scroll atau card-list di mobile. Foto coach pertahankan rasio potret dengan `object-fit: cover`.

14. **Accessibility**: Rating jangan hanya bintang visual — sertakan nilai numerik (mis. `aria-label="Rating 4.9 dari 5"`). Icon button beri `aria-label` deskriptif ("Atur jadwal Coach Adrian"). Status badge selalu menyertakan teks, tidak hanya warna.

---

*Spec ini generated dari analisis visual screen Admin Personal Trainer Management.png (visual-verified).*
*Design system reference: ADMIN_PAYMENTS_TRANSACTIONS_UI_SPEC.md, ADMIN_EQUIPMENT_MANAGEMENT_UI_SPEC.md*
*Total sections: 13 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

# ADMIN_REPORTS_UI_SPEC.md
# Egg Gym App — Admin Reports Screen
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Admin > Laporan Operasional (Operational Reports)
# Resolution: 1280 × 1024 px
# Last Updated: 2026-06-24

---

## 1. DESIGN TOKENS — COLOR PALETTE

| Token Name                  | HEX Value                      | Usage                                               |
|-----------------------------|--------------------------------|-----------------------------------------------------|
| --color-bg-primary          | #1A1500                        | Main content background                             |
| --color-bg-card             | #252000                        | KPI cards, chart panels, ranking table background   |
| --color-bg-sidebar          | #141000                        | Sidebar background                                  |
| --color-bg-header           | #1E1900                        | Top header bar background                           |
| --color-bg-table-header     | #1A1500                        | Ranking table header row background                 |
| --color-accent-primary      | #F5C300                        | Header title, bar MAY, rank #01, revenue gain text  |
| --color-accent-hover        | #E0B000                        | AI button hover, export btn hover                   |
| --color-text-primary        | #FFFFFF                        | Trainer names, values, primary content              |
| --color-text-secondary      | #8A8070                        | Labels, sub-values, grid lines, chart legends       |
| --color-text-muted          | #5A5040                        | Disabled, placeholders, faint text                  |
| --color-text-on-accent      | #1A1500                        | AI button text, active toggle text                  |
| --color-bar-active          | #F5C300                        | Bar chart MAY column — only this bar is kuning!     |
| --color-bar-inactive        | #3A3200                        | Bar chart Jan/Feb/Mar/Apr/Jun — gelap cokelat        |
| --color-bar-hover           | #4A3F00                        | Inactive bar hover state                            |
| --color-gridline            | rgba(90,80,64,0.3)             | Bar chart horizontal gridlines (dashed)             |
| --color-donut-elite         | #F5C300                        | Donut segment 1 — Elite Yearly (45%)                |
| --color-donut-monthly       | #3B82F6                        | Donut segment 2 — Monthly Pro (30%)                 |
| --color-donut-intro         | #4CAF50                        | Donut segment 3 — Personal Intro (25%)              |
| --color-rank-1              | #F5C300                        | Rank #01 number text — 18px bold kuning             |
| --color-rank-other          | #8A8070                        | Rank #02, #03 number text — abu                     |
| --color-revenue-gain        | #F5C300                        | Revenue Gain column in ranking table — kuning       |
| --color-badge-elite-bg      | rgba(245,195,0,0.15)           | "Elite" badge in KPI card 3                         |
| --color-badge-elite-text    | #F5C300                        | "Elite" badge text                                  |
| --color-export-btn-border   | #2E2800                        | Export buttons default border                       |
| --color-export-btn-text     | #8A8070                        | Export buttons default text                         |
| --color-export-btn-hover    | #F5C300                        | Export buttons hover text + border                  |
| --color-ai-btn-bg           | #F5C300                        | Floating "Generate AI Insights" button background   |
| --color-ai-btn-shadow       | rgba(245,195,0,0.3)            | AI button box-shadow                                |
| --color-star-filled         | #F5C300                        | Rating star filled state                            |
| --color-star-empty          | #2E2800                        | Rating star empty/unfilled state                    |
| --color-toggle-active-bg    | #F5C300                        | "6 Months" active toggle background                 |
| --color-toggle-active-text  | #1A1500                        | "6 Months" active toggle text                       |
| --color-toggle-inactive     | #8A8070                        | "Yearly" inactive toggle text                       |
| --color-border-card         | #2E2800                        | Card borders, panel borders, table rows             |
| --color-border-sidebar      | #2A2400                        | Sidebar dividers                                    |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Monospace:  "JetBrains Mono", "Fira Code", monospace
```

### Skala Tipografi Lengkap
| Token                     | Size | Weight | Line-H | Letter-Sp        | Usage                                       |
|---------------------------|------|--------|--------|------------------|---------------------------------------------|
| --text-breadcrumb-title   | 18px | 700    | 1.2    | 0.08em           | "LAPORAN OPERASIONAL" header — KUNING!      |
| --text-kpi-value          | 32px | 800    | 1.0    | 0px              | KPI card angka utama                        |
| --text-kpi-label          | 11px | 700    | 1.2    | 2px (uppercase)  | KPI card label                              |
| --text-kpi-sub            | 12px | 400    | 1.3    | 0px              | KPI sub-value (+12.6% dll)                  |
| --text-kpi-badge          | 10px | 700    | 1.0    | 1px (uppercase)  | Badge "Elite" di KPI card 3                 |
| --text-search             | 13px | 400    | 1.0    | 0px              | Search bar input                            |
| --text-export-btn         | 12px | 700    | 1.0    | 0.5px            | Export button text (uppercase)              |
| --text-panel-title        | 14px | 700    | 1.3    | 0px              | Chart panel titles                          |
| --text-panel-sub          | 10px | 400    | 1.2    | 0.1em (uppercase)| "MONTHLY PERFORMANCE PROJECTION" subtitle   |
| --text-chart-toggle       | 12px | 700    | 1.0    | 0px              | "6 Months" / "Yearly" toggle text           |
| --text-bar-label          | 11px | 400    | 1.0    | 0px              | Bar chart X-axis labels (Jan, Feb, etc.)    |
| --text-bar-value          | 11px | 600    | 1.0    | 0px              | Value label di atas bar aktif               |
| --text-donut-center-value | 24px | 700    | 1.0    | 0px              | "462" di tengah donut chart                 |
| --text-donut-center-label | 11px | 400    | 1.2    | 0px              | "total sold" di tengah donut                |
| --text-legend-name        | 12px | 400    | 1.3    | 0px              | Legend item nama paket                      |
| --text-legend-pct         | 12px | 400    | 1.3    | 0px              | Legend item persentase (abu)                |
| --text-ranking-header     | 10px | 700    | 1.0    | 0.1em (uppercase)| PT Ranking table column headers             |
| --text-rank-1             | 18px | 700    | 1.0    | 0px              | Rank #01 — KUNING, larger                   |
| --text-rank-other         | 16px | 600    | 1.0    | 0px              | Rank #02, #03 — abu, medium                 |
| --text-trainer-name       | 13px | 700    | 1.3    | 0px              | PT name in ranking                          |
| --text-sessions           | 13px | 400    | 1.3    | 0px              | Sessions count                              |
| --text-revenue-gain       | 13px | 700    | 1.3    | 0px              | Revenue gain — KUNING (#F5C300)             |
| --text-ai-button          | 13px | 700    | 1.0    | 0px              | Floating AI Insights button text            |
| --text-view-all           | 12px | 700    | 1.0    | 0px              | "View Full Leaderboard →" link              |

---

## 3. SPACING & LAYOUT

### Spacing Scale
| Token          | Value | Usage                                                    |
|----------------|-------|----------------------------------------------------------|
| --space-xs     | 4px   | Badge padding, star gap                                  |
| --space-sm     | 8px   | Legend dot-to-text gap, toggle inner                     |
| --space-md     | 12px  | Chart header margin, legend item gap                     |
| --space-base   | 16px  | KPI gap, action row gap                                  |
| --space-lg     | 20px  | Sections gap, chart padding                              |
| --space-xl     | 24px  | Page padding, chart panel padding                        |

### Border Radius
| Token        | Value | Usage                                                    |
|--------------|-------|----------------------------------------------------------|
| --radius-xs  | 4px   | Bar chart top radius, toggle, export buttons, badges     |
| --radius-sm  | 6px   | Export buttons, search bar                               |
| --radius-md  | 8px   | Toggle container, search input                           |
| --radius-lg  | 10px  | KPI cards, chart panels, ranking table                   |
| --radius-xl  | 12px  | Floating AI button                                       |
| --radius-full| 50%   | Donut chart legend dots, avatar circles                  |

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Total Canvas:   1280 × 1024 px
Sidebar:        220px wide × 100vh (fixed)
Header Bar:     calc(100vw - 220px) × 56px (sticky)
Main Content:   calc(100vw - 220px), padding: 24px
Charts Row:     1.5fr (Revenue) | 1fr (Packages), gap: 20px
```

### ASCII Layout Diagram
```
┌─────────────────────┬────────────────────────────────────────────────────────┐
│  SIDEBAR (220px)    │  HEADER BAR (56px)                                     │
│  ───────────────    │  ────────────────────────────────────────────────────  │
│  ◈ Editorial        │  LAPORAN OPERASIONAL [KUNING #F5C300]   🔍  🔔  ⚙  👤 │
│    Athletics        ├────────────────────────────────────────────────────────┤
│  ───────────────    │  MAIN CONTENT (padding: 24px)                           │
│  ⊞ Dashboard        │                                                        │
│  👥 Member          │  ACTION ROW (flex, justify-between, mb:16px)            │
│  📅 Slot Mgmt       │  [🔍 Search metrics...]  [EXPORT CENTER][PDF][EXCEL]   │
│  ⭐ Personal Trainer │                                                        │
│  📋 Booking & Sesi  │  KPI CARDS ROW (3 kolom, gap:16px, mb:20px)             │
│  🏋 Equipment       │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐ │
│  📃 Audit Log       │  │ Rp 2.48M     │  │ 1,240 active │  │ 94.2%        │ │
│  🎫 Paket Member    │  │ PENDAPATAN   │  │ PERTUMBUHAN  │  │ EFISIENSI PT │ │
│  💳 Pembayaran      │  │ TAHUNAN      │  │ MEMBER       │  │ [Elite badge]│ │
│  📊 Laporan ◄AKTIF  │  └──────────────┘  └──────────────┘  └──────────────┘ │
│  ───────────────    │                                                        │
│  [A] Admin Elite    │  CHARTS ROW (1.5fr | 1fr, gap:20px, mb:20px)           │
│  admin@egggym.id    │  ┌──────────────────────────┐  ┌──────────────────┐   │
│                     │  │  REVENUE ANALYTICS       │  │  PACKAGES DISTR  │   │
│                     │  │  [6 Months★][Yearly]     │  │  [Donut 160px]   │   │
│                     │  │                          │  │  ┌────────────┐  │   │
│                     │  │  ████ ████ ████ ██── ██  │  │  │ ●   462    │  │   │
│                     │  │  ████ ████ ████ ████ ██  │  │  │  total     │  │   │
│                     │  │   J    F    M    A    M  │  │  └────────────┘  │   │
│                     │  │        ↑ MAY = kuning    │  │  ● Elite 45%    │   │
│                     │  └──────────────────────────┘  │  ● Monthly 30%  │   │
│                     │                                │  ● Intro 25%    │   │
│                     │                                └──────────────────┘   │
│                     │  PT PERFORMANCE RANKING (full width, mb:20px)          │
│                     │  ┌──────────────────────────────────────────────────┐  │
│                     │  │RANK│TRAINER NAME│SPEC│SESSIONS│REVENUE│RATING   │  │
│                     │  │ 01 │Marcus V    │Str │  142   │ Rp42M │★★★★★   │  │
│                     │  │ 02 │Elena R     │Yor │  128   │ Rp38M │★★★★☆   │  │
│                     │  │ 03 │David C     │FW  │  115   │ Rp34M │★★★★★   │  │
│                     │  └──────────────────────────────────────────────────┘  │
│                     │                                 🤖 [Generate AI Insights│
│                     │  ═══════════════════════════════════════════════════   │
│                     │  🟢 SISTEM AKTIF │ AI message...                       │
└─────────────────────┴────────────────────────────────────────────────────────┘
```

---

## 5. KOMPONEN: SIDEBAR

### 5.1 Container
```
Width: 220px, Height: 100vh
Background: #141000, Border-right: 1px solid #2A2400
Box-shadow: 2px 0 8px rgba(0,0,0,0.5)
Position: fixed left 0, z-index 200
```

### 5.2 Logo / Brand
```
Padding: 16px 16px 14px, Border-bottom: 1px solid #2A2400
Logo: 32px hex icon, fill #F5C300
Brand: "Editorial Athletics", 14px/700, #FFFFFF
```

### 5.3 Navigation Items
```
Default: height 40px, padding 10px 16px, icon+text 13px/500 #8A8070
Active (Laporan):
  Background: #252000
  Border-left: 3px solid #F5C300, Padding-left: 13px
  Icon+Text: #F5C300, weight 600
Hover: bg #1E1900, icon+text → #D4AA00
```

### 5.4 Menu Order
```
1. ⊞  Dashboard
2. 👥  Member
3. 📅  Slot Management
4. ⭐  Personal Trainer
5. 📋  Booking & Sesi
6. 🏋  Equipment
7. 📃  Audit Log
8. 🎫  Paket Membership
9. 💳  Pembayaran
10. 📊  Laporan            ← ACTIVE
```

### 5.5 Profile Area
```
Avatar 36px circle bg #F5C300 "A" color #1A1500
Name 13px/600 #FFFFFF, Email 11px/400 #8A8070
```

---

## 6. KOMPONEN: TOP HEADER BAR

### 6.1 Container
```
Height: 56px, Background: #1E1900, Border-bottom: 1px solid #2E2800
Padding: 0 20px, Position: sticky top 0, z-index 100
Width: calc(100vw - 220px)
```

### 6.2 Kiri — Breadcrumb ⚠️ KUNING!
```
⚠️ Header title KUNING (#F5C300) — sama seperti Booking dan Payments.
Pattern: semua halaman monitoring/reporting = header kuning.

Text:           "LAPORAN OPERASIONAL"
Font-size:      18px / 700
Color:          #F5C300   ← KUNING
Letter-spacing: 0.08em
Text-transform: uppercase
```

### 6.3 Search Bar + Icon Area
```
Search: 280px, h:32px, bg #2A2400, border #2E2800, radius 6px
  Placeholder: "Cari laporan, metrics..."
  Focus: border #F5C300
Icons: Bell 20px + Settings 20px + Avatar 28px circle
```

---

## 7. KOMPONEN: ACTION ROW

### 7.1 Container
```
Display:        flex, justify-content space-between, align-items center
Margin-bottom:  16px
Height:         ~48px
```

### 7.2 Kiri — Search Bar
```
Width:          260px
Height:         36px
Background:     #252000
Border:         1px solid #2E2800
Border-radius:  8px
Padding:        0 12px, Gap: 8px

Icon: 🔍 14px #8A8070
Input: 13px #FFFFFF, placeholder "Search metrics..." color #5A5040
Focus: border-color → #F5C300
```

### 7.3 Kanan — Export Buttons (3 tombol)
```
Display:        flex, gap 8px

Semua export buttons share style:
  Height:       36px
  Background:   transparent
  Border:       1px solid #2E2800   ← ABU default
  Border-radius:8px
  Padding:      7px 14px
  Font-size:    12px / 700
  Color:        #8A8070             ← ABU default
  Text-transform:uppercase
  Cursor:       pointer

  Hover:
    Border-color: #F5C300           ← KUNING on hover
    Color:        #F5C300           ← KUNING on hover
    Background:   rgba(245,195,0,0.05)

Button 1: "EXPORT CENTER"
Button 2: "PDF"
Button 3: "EXCEL"
```

---

## 8. KOMPONEN: KPI CARDS (3 Kolom)

### 8.1 Grid
```
Display: grid, Grid-template-columns: 1fr 1fr 1fr
Gap: 16px, Margin-bottom: 20px
```

### 8.2 Card Default (semua 3 card = bg gelap, tidak ada kuning solid)
```
Background:     #252000
Border:         1px solid #2E2800
Border-radius:  10px
Padding:        18px 20px
Display:        flex flex-column gap 6px
```

### 8.3 KPI Data

#### Card 1 — PENDAPATAN TAHUNAN
```
Value:    "Rp 2.48M"
  Font-size:  32px / 800, Color: #FFFFFF

Sub:      "+12.6% vs last period"
  Font-size:  12px / 400, Color: #4CAF50   ← HIJAU positif

Label:    "PENDAPATAN TAHUNAN"
  Font-size:  11px / 700, Color: #8A8070
  Letter-spacing: 2px, Text-transform: uppercase
```

#### Card 2 — PERTUMBUHAN MEMBER
```
Value:    "1,240 active"
  Font-size:  32px / 800, Color: #FFFFFF

Sub:      "+95 new this month"
  Font-size:  12px / 400, Color: #4CAF50

Label:    "PERTUMBUHAN MEMBER"
  Font-size:  11px / 700, Color: #8A8070
```

#### Card 3 — EFISIENSI SESI PT (dengan badge)
```
Value:    "94.2%"
  Font-size:  32px / 800, Color: #FFFFFF

Badge "Elite":
  Background: rgba(245,195,0,0.15)
  Color:      #F5C300
  Font-size:  10px / 700, uppercase, letter-spacing 1px
  Padding:    2px 10px, Border-radius: 4px
  Display:    inline-flex (di samping atau bawah value)

Label:    "EFISIENSI SESI PT"
  Font-size:  11px / 700, Color: #8A8070
```

---

## 9. KOMPONEN: REVENUE ANALYTICS CHART

### 9.1 Panel Container
```
Background:     #252000
Border:         1px solid #2E2800
Border-radius:  10px
Padding:        20px 24px
Flex:           1.5 (dalam charts row)
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
```

### 9.2 Panel Header
```
Display:        flex, justify-content space-between, align-items flex-start

Kiri:
  Title:  "REVENUE ANALYTICS", 14px/700, #FFFFFF
  Sub:    "MONTHLY PERFORMANCE PROJECTION", 10px/400, #8A8070, uppercase, letter-spacing 0.1em

Kanan — Toggle:
  Container:
    Display:    flex, background transparent, border 1px solid #2E2800, radius 4px
    Overflow:   hidden

  "6 Months" (active):
    Background: #F5C300
    Color:      #1A1500
    Padding:    4px 12px
    Font-size:  12px / 700

  "Yearly" (inactive):
    Background: transparent
    Color:      #8A8070
    Padding:    4px 12px
    Font-size:  12px / 700
    Hover:      color #FFFFFF, bg rgba(255,255,255,0.05)
```

### 9.3 Bar Chart
```
Height:         200px
Margin-top:     16px
Display:        flex, align-items flex-end, gap ~20px
Padding-bottom: 24px (space for X-axis labels)
Position:       relative

Gridlines (horizontal, dashed):
  Count:        4–5 lines
  Color:        rgba(90,80,64,0.3)
  Style:        dashed
  Position:     absolute, full width, z-index 0

Bars Container:
  Display:      flex, align-items flex-end, gap ~20px
  Width:        100%
  Height:       100%
  Z-index:      1
```

### 9.4 Individual Bar
```
Width:          ~40px
Border-radius:  4px 4px 0 0
Transition:     height 0.5s ease, background 0.2s

INACTIVE bars (Jan, Feb, Mar, Apr, Jun):
  Background:   #3A3200
  Hover:        background #4A3F00

ACTIVE bar (MAY — hanya satu!):
  Background:   #F5C300   ← KUNING, HANYA BAR INI!
  Hover:        background #E0B000
  Box-shadow:   0 0 8px rgba(245,195,0,0.2)
  
  Value label di atas bar:
    Font-size:  11px / 600, Color: #F5C300, Margin-bottom: 4px
```

### 9.5 Bar Data (6 bars, tinggi relatif)
```
Bar 1 (Jan): bg #3A3200, height ~55%
Bar 2 (Feb): bg #3A3200, height ~48%
Bar 3 (Mar): bg #3A3200, height ~65%
Bar 4 (Apr): bg #3A3200, height ~60%
Bar 5 (MAY): bg #F5C300, height ~100% ← tallest, kuning!
Bar 6 (Jun): bg #3A3200, height ~70%

X-axis labels (bawah, 11px #8A8070): Jan Feb Mar Apr May Jun
```

---

## 10. KOMPONEN: PACKAGES DISTRIBUTION (DONUT CHART)

### 10.1 Panel Container
```
Background:     #252000
Border:         1px solid #2E2800
Border-radius:  10px
Padding:        20px
Flex:           1 (dalam charts row)
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
Display:        flex flex-column
```

### 10.2 Panel Title
```
Text:           "PACKAGES DISTRIBUTION"
Font-size:      14px / 700
Color:          #FFFFFF
Margin-bottom:  16px
```

### 10.3 Donut Chart SVG
```
Width/Height:   ~160px × ~160px
ViewBox:        0 0 160 160
Margin:         0 auto

Center circle background:
  Fill:         #252000
  Radius:       ~40px (inner radius)

Segments (SVG stroke-dasharray / pie arcs):
  Total: 3 segments, starting from top (270°)

  Segment 1 — Elite Yearly (45%):
    Stroke:     #F5C300
    Stroke-width: ~28px
    Arc:        162° (45% of 360°)

  Segment 2 — Monthly Pro (30%):
    Stroke:     #3B82F6
    Stroke-width: ~28px
    Arc:        108° (30% of 360°)

  Segment 3 — Personal Intro (25%):
    Stroke:     #4CAF50
    Stroke-width: ~28px
    Arc:        90° (25% of 360°)

Center Text:
  Value: "462"
    Font-size:  24px / 700, Color: #FFFFFF, Text-anchor: middle
    Y:          ~75px (center - slight up)

  Label: "total sold"
    Font-size:  11px / 400, Color: #8A8070, Text-anchor: middle
    Y:          ~92px (center + slight down)
```

### 10.4 Legend
```
Display:        flex, flex-direction column, gap 8px
Margin-top:     16px

Legend Item (per item):
  Display:      flex, align-items center, justify-content space-between

  Left:
    Display:    flex, align-items center, gap 8px
    Dot: 8px × 8px, border-radius 50%, flex-shrink 0
    Name: 12px/400, #FFFFFF

  Right:
    Percentage: 12px/400, #8A8070

Data:
  [● #F5C300]  "Elite Yearly"    45%
  [● #3B82F6]  "Monthly Pro"     30%
  [● #4CAF50]  "Personal Intro"  25%
```

---

## 11. KOMPONEN: PT PERFORMANCE RANKING

### 11.1 Panel Container
```
Background:     #252000
Border:         1px solid #2E2800
Border-radius:  10px
Padding:        20px
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
Margin-bottom:  20px
```

### 11.2 Panel Header
```
Display:        flex, justify-content space-between, align-items flex-start
Margin-bottom:  16px

Left:
  Title: "PT PERFORMANCE RANKING", 14px/700, #FFFFFF
  Sub:   "BASED ON SESSION COMPLETION & RATINGS", 10px/400, #8A8070, uppercase

Right:
  "View Full Leaderboard →"
  Font-size: 12px/700, Color: #F5C300, cursor pointer
  Hover: text-decoration underline
```

### 11.3 Table Header Row
```
Height:         36px
Background:     #1A1500
Padding:        0 16px
Display:        grid
Grid-template:  0.5fr 2fr 1.8fr 1fr 1.2fr 1fr

Column headers (all):
  Font-size:    10px/700, Color: #8A8070, uppercase, letter-spacing 0.1em

Columns:
  Col 1: "RANK"
  Col 2: "TRAINER NAME"
  Col 3: "SPECIALTY"
  Col 4: "SESSIONS"
  Col 5: "REVENUE GAIN"
  Col 6: "RATING"
```

### 11.4 Table Row
```
Min-height:     56px
Padding:        12px 16px
Display:        grid
Grid-template:  0.5fr 2fr 1.8fr 1fr 1.2fr 1fr
Border-bottom:  1px solid #2E2800
Align-items:    center
Hover:          bg rgba(245,195,0,0.03)
```

### 11.5 Kolom RANK (berbeda tiap rank)
```
Rank #01:
  Text:         "#01"
  Font-size:    18px / 700
  Color:        #F5C300   ← KUNING, lebih besar!

Rank #02, #03:
  Text:         "#02", "#03"
  Font-size:    16px / 600
  Color:        #8A8070   ← ABU, lebih kecil
```

### 11.6 Kolom TRAINER NAME
```
Display:        flex, align-items center, gap 10px

Avatar:
  Width:        32px, Height: 32px, Border-radius: 50%
  Border:       1px solid #2E2800
  Object-fit:   cover

Name:
  Font-size:    13px / 700, Color: #FFFFFF
```

### 11.7 Kolom SPECIALTY
```
Font-size:      13px / 400
Color:          #8A8070
```

### 11.8 Kolom SESSIONS
```
Font-size:      13px / 400
Color:          #FFFFFF
```

### 11.9 Kolom REVENUE GAIN ⚠️ KUNING!
```
Font-size:      13px / 700
Color:          #F5C300   ← KUNING semua revenue gain
Format:         "Rp XX.XM" (abbreviated)
```

### 11.10 Kolom RATING (Star Rating)
```
Display:        flex, gap 2px, align-items center

Star icon (filled):
  Color:        #F5C300   ← KUNING
  Size:         14px

Star icon (empty):
  Color:        #2E2800   ← GELAP
  Size:         14px

5 stars total per row
```

### 11.11 Data Contoh (3 rows)
```
Row 1 (Rank #01):
  Rank:         "#01" → 18px/700 #F5C300
  Avatar+Name:  Coach Marcus V
  Specialty:    "Strength Training"
  Sessions:     "142"
  Revenue:      "Rp 42.6M" → #F5C300
  Rating:       ★★★★★ (5 filled)

Row 2 (Rank #02):
  Rank:         "#02" → 16px/600 #8A8070
  Avatar+Name:  Elena Rodriguez
  Specialty:    "Yoga & Recovery"
  Sessions:     "128"
  Revenue:      "Rp 38.4M" → #F5C300
  Rating:       ★★★★☆ (4 filled, 1 empty)

Row 3 (Rank #03):
  Rank:         "#03" → 16px/600 #8A8070
  Avatar+Name:  David Chen
  Specialty:    "Free Weights"
  Sessions:     "115"
  Revenue:      "Rp 34.5M" → #F5C300
  Rating:       ★★★★★ (5 filled)
```

---

## 12. KOMPONEN: FLOATING AI BUTTON

### 12.1 Positioning
```
Position:       fixed
Bottom:         24px
Right:          24px
Z-index:        500   ← di atas semua konten, termasuk AI Bar
```

### 12.2 Button Styling
```
Background:     #F5C300   ← KUNING SOLID
Color:          #1A1500
Border:         none
Border-radius:  12px
Padding:        10px 18px
Display:        flex, align-items center, gap 8px
Font-size:      13px / 700
Box-shadow:     0 4px 20px rgba(245,195,0,0.3)
Cursor:         pointer
White-space:    nowrap
```

### 12.3 Icon + Text
```
Robot Icon:
  Font-size:    18px (emoji 🤖 atau SVG icon)
  Color:        #1A1500

Text: "Generate AI Insights"
  Font-size:    13px / 700
  Color:        #1A1500
```

### 12.4 Hover State
```
Background:     #EAB800   (sedikit lebih gelap)
Box-shadow:     0 6px 24px rgba(245,195,0,0.4)
Transform:      translateY(-2px)
Transition:     all 0.2s ease
```

---

## 13. INTERACTION STATES

### 13.1 Chart Toggle (6 Months / Yearly)
```
Click → switch chart data between 6 months dan yearly view
Active state: bg #F5C300, text #1A1500
Inactive state: bg transparent, text #8A8070
Smooth transition: data fade atau slide (250ms)
```

### 13.2 Export Button Click
```
Each button shows dropdown on click:
EXPORT CENTER → pilihan format (custom)
PDF → trigger browser PDF download
EXCEL → download .xlsx file

Dropdown:
  bg #252000, border #2E2800, radius 8px, z-index 200
  Items: padding 10px 16px, hover bg rgba(245,195,0,0.05), color #FFFFFF
```

### 13.3 Bar Chart Hover
```
Inactive bar hover:
  Background:   #4A3F00 (sedikit lebih terang dari #3A3200)
  Tooltip:      show month + value, bg #1A1500, border #2E2800, radius 6px, padding 8px 12px

Active bar (MAY) hover:
  Background:   #E0B000
  Tooltip:      show month + value + "Highest this period ↑"
```

### 13.4 Donut Chart Hover
```
Each segment hover:
  Highlight:    segment brightens (opacity atau glow)
  Tooltip:      "Elite Yearly — 45% (208 sold)", bg dark, radius 6px

Center text:
  Default:      "462 / total sold"
  On hover:     update to show hovered segment's count
```

### 13.5 PT Ranking Row Click
```
Click row → navigate to PT detail page atau open slide-over
  /admin/pt/[id] atau side panel dengan full PT profile
```

### 13.6 AI Insights Button
```
Click → open AI Insights modal atau panel
Modal: full-width panel dari bawah atau right side
Content: AI-generated analysis dari semua metrics di halaman
Loading state: button shows spinner + "Generating..."
```

---

## 14. GRID RECAP — ZONA LAYOUT

| Zone                      | X Offset | Y Offset  | Width                    | Height    |
|---------------------------|----------|-----------|--------------------------|-----------|
| Sidebar                   | 0        | 0         | 220px                    | 100vh     |
| Header Bar                | 220px    | 0         | calc(100vw - 220px)      | 56px      |
| Action Row                | 244px    | 80px      | calc(100vw - 264px)      | ~48px     |
| KPI Cards Row             | 244px    | 148px     | calc(100vw - 264px)      | ~88px     |
| Charts Row                | 244px    | 256px     | calc(100vw - 264px)      | ~300px    |
|   Revenue Analytics (~60%)| 244px    | 256px     | 1.5fr of content         | ~300px    |
|   Packages Distribution   | ~830px   | 256px     | 1fr of content           | ~300px    |
| PT Performance Ranking    | 244px    | 576px     | calc(100vw - 264px)      | ~200px    |
| Floating AI Button        | fixed    | bottom:24 | auto (fit-content)       | ~40px     |
| AI Bar (fixed)            | 220px    | bottom: 0 | calc(100vw - 220px)      | 44px      |

---

## 15. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Admin Reports (Laporan Operasional)
   CSS Custom Properties — Design Tokens
   Generated: 2026-06-24
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:             #1A1500;
  --color-bg-card:                #252000;
  --color-bg-sidebar:             #141000;
  --color-bg-header:              #1E1900;
  --color-bg-table-header:        #1A1500;
  --color-accent-primary:         #F5C300;
  --color-accent-hover:           #E0B000;
  --color-text-primary:           #FFFFFF;
  --color-text-secondary:         #8A8070;
  --color-text-muted:             #5A5040;
  --color-text-on-accent:         #1A1500;
  --color-bar-active:             #F5C300;
  --color-bar-inactive:           #3A3200;
  --color-bar-hover:              #4A3F00;
  --color-gridline:               rgba(90, 80, 64, 0.3);
  --color-donut-elite:            #F5C300;
  --color-donut-monthly:          #3B82F6;
  --color-donut-intro:            #4CAF50;
  --color-rank-1:                 #F5C300;
  --color-rank-other:             #8A8070;
  --color-revenue-gain:           #F5C300;
  --color-badge-elite-bg:         rgba(245, 195, 0, 0.15);
  --color-badge-elite-text:       #F5C300;
  --color-export-btn-border:      #2E2800;
  --color-export-btn-text:        #8A8070;
  --color-export-btn-hover:       #F5C300;
  --color-ai-btn-bg:              #F5C300;
  --color-ai-btn-shadow:          rgba(245, 195, 0, 0.3);
  --color-star-filled:            #F5C300;
  --color-star-empty:             #2E2800;
  --color-toggle-active-bg:       #F5C300;
  --color-toggle-active-text:     #1A1500;
  --color-border-card:            #2E2800;
  --color-border-sidebar:         #2A2400;

  /* ── TYPOGRAPHY ── */
  --font-family-primary:          "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-kpi-value:               32px;
  --text-rank-1:                  18px;
  --text-rank-other:              16px;
  --text-donut-center:            24px;
  --text-ai-button:               13px;
  --text-panel-title:             14px;
  --text-trainer-name:            13px;
  --text-revenue-gain:            13px;

  /* ── SPACING ── */
  --space-xs:                     4px;
  --space-sm:                     8px;
  --space-md:                     12px;
  --space-base:                   16px;
  --space-lg:                     20px;
  --space-xl:                     24px;

  /* ── BORDER RADIUS ── */
  --radius-xs:                    4px;
  --radius-sm:                    6px;
  --radius-md:                    8px;
  --radius-lg:                    10px;
  --radius-xl:                    12px;
  --radius-full:                  50%;

  /* ── SHADOWS ── */
  --shadow-card:                  0 2px 8px rgba(0, 0, 0, 0.4);
  --shadow-ai-button:             0 4px 20px rgba(245, 195, 0, 0.3);
  --shadow-sidebar:               2px 0 8px rgba(0, 0, 0, 0.5);

  /* ── LAYOUT ── */
  --sidebar-width:                220px;
  --header-height:                56px;
  --ai-bar-height:                44px;
  --kpi-cols:                     3;
  --charts-ratio:                 1.5fr 1fr;
  --chart-bar-height:             200px;
  --donut-diameter:               160px;
  --donut-stroke-width:           28px;
  --ranking-grid:                 0.5fr 2fr 1.8fr 1fr 1.2fr 1fr;
  --page-padding:                 24px;
  --ai-btn-bottom:                24px;
  --ai-btn-right:                 24px;
}
```

---

## 16. CATATAN AI — IMPLEMENTATION NOTES (15 poin)

1. **Header Title Kuning = Reporting Screen**: "LAPORAN OPERASIONAL" menggunakan `color: #F5C300`. Ini konsisten dengan halaman reporting/monitoring lainnya (Booking, Pembayaran). Pattern global: halaman yang memerlukan perhatian aktif menggunakan header kuning.

2. **Bar Chart: HANYA MAY = Kuning**: Ini adalah aturan KERAS — hanya bar bulan tertinggi/terkini yang berwarna kuning (#F5C300). Semua bar lain harus menggunakan `#3A3200`. Jika data berubah dan bulan lain menjadi tertinggi, update warna bar tertinggi ke kuning secara programatik.

3. **Bar Chart Implementation**: Gunakan salah satu dari:
   - Pure CSS: `div` dengan `height: [persen]%` dalam flexbox container
   - Recharts: `<BarChart>` dengan `<Bar fill>` conditional berdasarkan index
   - Chart.js: `backgroundColor` array dengan logika `index === maxIndex ? '#F5C300' : '#3A3200'`
   - SVG: `<rect>` elements dengan transform-origin untuk flip vertical

4. **Donut Chart SVG Implementation**:
   ```javascript
   // Menggunakan SVG stroke-dasharray technique:
   const circumference = 2 * Math.PI * r; // r = 54 (outer - stroke/2)
   const eliteOffset = circumference * 0;       // starts at 0
   const monthlyOffset = circumference * 0.45;  // starts at 45%
   const introOffset = circumference * 0.75;    // starts at 75%
   ```
   Atau gunakan library: Recharts `<PieChart>`, D3.js `d3.arc()`, atau Chart.js `type: 'doughnut'`.

5. **Rank #01 = Larger + Yellow**: Rank #01 menggunakan `font-size: 18px` dan `color: #F5C300`. Rank lain menggunakan `font-size: 16px` dan `color: #8A8070`. Buat fungsi `getRankStyle(rank)` yang return style object berdasarkan rank number.

6. **Revenue Gain = Selalu Kuning**: Semua nilai di kolom "Revenue Gain" menggunakan `color: #F5C300` tanpa kondisi. Ini membuat kolom ini mudah diidentifikasi secara visual dalam tabel panjang.

7. **Floating AI Button Z-Index**: Z-index harus cukup tinggi (500+) untuk muncul di atas semua konten, termasuk fixed AI Bar (z-index 90) dan sticky header (z-index 100). Pastikan tidak ada z-index stacking context yang memblok.

8. **Star Rating Component**: Buat reusable `<StarRating count={5} filled={4} />` component:
   - Filled star: SVG star path dengan `fill: #F5C300`
   - Empty star: SVG star path dengan `fill: #2E2800`
   - Gunakan `aria-label="Rating: [N] dari 5 bintang"` untuk accessibility

9. **Export Buttons**: Semua 3 tombol export menggunakan outline style (transparent bg, border abu) bukan solid kuning. Ini berbeda dari CTA utama. Pattern: export/secondary actions = outline, primary actions = solid kuning.

10. **Chart Toggle State**: Toggle "6 Months" / "Yearly" menggunakan pill-group design:
    - Bungkus dalam container dengan `border: 1px solid #2E2800; border-radius: 4px; overflow: hidden`
    - Active button: `background: #F5C300; color: #1A1500` (tidak perlu border tambahan)
    - Gunakan `aria-pressed="true/false"` bukan radio input untuk accessibility

11. **KPI Cards: 3 Kolom (bukan 4)**: Halaman Reports menggunakan 3 KPI cards, bukan 4 seperti halaman lain. Pastikan `grid-template-columns: 1fr 1fr 1fr`. Card ketiga memiliki badge inline "Elite" yang harus ditampilkan di dalam card, bukan sebagai label eksternal.

12. **Charts Row Ratio**: Revenue Analytics menggunakan `flex: 1.5` dan Packages Distribution menggunakan `flex: 1`. Ini memberikan chart kiri ~60% dan chart kanan ~38% dari total lebar. Gunakan `display: flex; gap: 20px` bukan `display: grid` untuk flexibility.

13. **PT Ranking Table Accessibility**: Gunakan proper ARIA roles dan announce rank prominently:
    - `role="table"`, `role="rowgroup"`, `role="row"`, `role="columnheader"`, `role="cell"`
    - `aria-label="Rank 1 dari 3: Coach Marcus V, 142 sesi, Rp 42.6M, rating 5 bintang"`

14. **Generate AI Insights Flow**: Klik floating button trigger:
    1. Button state: "Generating..." + spinner (1.5-3 detik loading)
    2. Open side panel atau modal dengan analisis AI
    3. Content: trend analysis, anomaly detection, recommendations
    4. Error state: "Gagal generate. Coba lagi?" button

15. **Responsive Adaptation**: Pada viewport < 1024px:
    - Charts row berubah dari side-by-side menjadi stacked
    - KPI cards berubah dari 3 kolom ke 2 kolom, lalu 1 kolom di < 640px
    - PT Ranking table: hide SPECIALTY column, show only RANK/NAME/SESSIONS/REVENUE/RATING
    - Floating AI button stays fixed tapi ukuran mengecil di mobile

---

*Spec ini generated dari analisis visual screen Admin Reports.png*
*Design system reference: ADMIN_DASHBOARD_UI_SPEC.md*
*Total sections: 16 | Detail level: ⭐⭐⭐⭐⭐ Full Detail*

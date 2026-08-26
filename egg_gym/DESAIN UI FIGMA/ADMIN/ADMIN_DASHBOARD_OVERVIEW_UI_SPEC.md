# ADMIN_DASHBOARD_OVERVIEW_UI_SPEC.md
# Egg Gym App — Admin Dashboard Overview Screen
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Admin > Dashboard Overview
# Resolution: 1140 × 1060 px (approx)
# Last Updated: 2026-06-25

---

## 1. DESIGN TOKENS — COLOR PALETTE

Semua token warna digunakan konsisten di seluruh Admin screens.
Reference utama: ADMIN_EQUIPMENT_MANAGEMENT_UI_SPEC.md

| Token Name                | HEX Value              | Usage                                               |
|---------------------------|------------------------|-----------------------------------------------------|
| --color-bg-primary        | #1A1500                | Main content background                             |
| --color-bg-card           | #252000                | Stat cards, chart panel, panel backgrounds          |
| --color-bg-sidebar        | #141000                | Sidebar background                                  |
| --color-bg-header         | #1E1900                | Top header bar background                           |
| --color-bg-input          | #2A2400                | Search bar & input field background                 |
| --color-accent-primary    | #F5C300                | Active stat card (revenue), chart bar aktif, badge  |
| --color-accent-hover      | #E0B000                | Button hover state                                  |
| --color-text-primary      | #FFFFFF                | Headings, stat numbers, card titles                 |
| --color-text-secondary    | #8A8070                | Labels, captions, helper text, sub-labels           |
| --color-text-muted        | #5A5040                | Disabled, placeholder, timestamps                   |
| --color-text-on-accent    | #1A1500                | Text on yellow/accent elements                      |
| --color-status-active     | #4CAF50                | Positive delta (retention rate indicator)           |
| --color-status-warning    | #F59E0B                | Warning indicators, maintenance alert icon          |
| --color-status-danger     | #EF4444                | Danger/error, maintenance alert icon                |
| --color-status-info       | #3B82F6                | Info icons in Recent Activity (booking icon)        |
| --color-status-neutral    | #6B7280                | Inactive chart bars, footer stat labels             |
| --color-border-card       | #352E00                | Card & panel borders                                |
| --color-border-sidebar    | #2A2400                | Sidebar dividers                                    |
| --color-chart-bar-active  | #F5C300                | Current month (JUN) bar — highlighted               |
| --color-chart-bar-inactive| #3A3300                | Past months bars (JAN–MAY) — muted                  |
| --color-progress-fill     | #F5C300                | PT booking trend progress bar fill                  |
| --color-progress-track    | #3A3300                | PT booking trend progress bar background            |
| --color-delta-positive    | #4CAF50                | "+12% vs last month", "+5.2%", "+1.8%" delta text   |
| --color-activity-icon-bg  | #2A2400                | Recent activity icon container background           |
| --color-revenue-card-bg   | #F5C300                | Revenue stat card (kuning) background               |
| --color-revenue-card-text | #1A1500                | Revenue stat card text color                        |
| --color-footer-bar-bg     | #1E1900                | Bottom summary bar background                       |
| --color-overlay-dark      | rgba(0,0,0,0.7)        | Modal backdrop                                      |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Monospace:  "JetBrains Mono", "Fira Code", monospace  (untuk angka finansial)
```

### Skala Tipografi Lengkap
| Token                      | Size | Weight | Line-H | Letter-Sp       | Usage                                      |
|----------------------------|------|--------|--------|-----------------|--------------------------------------------|
| --text-page-title          | 18px | 700    | 1.2    | 2px (uppercase) | "DASHBOARD OVERVIEW" header breadcrumb     |
| --text-stat-number-xl      | 32px | 800    | 1.0    | -0.5px          | "1,250" / "Rp 145.2M" utama stat card      |
| --text-stat-number-lg      | 28px | 800    | 1.0    | -0.5px          | "48" / "82" stat card angka                |
| --text-stat-label          | 11px | 600    | 1.3    | 1.5px uppercase | "TOTAL MEMBER AKTIF", "BOOKING HARI INI"   |
| --text-stat-sublabel       | 12px | 400    | 1.4    | 0px             | "+12% vs last month", "98% capacity used"  |
| --text-section-title       | 18px | 700    | 1.2    | 0px             | "Membership Sales Trend", "Recent Activity"|
| --text-section-subtitle    | 11px | 600    | 1.2    | 2px uppercase   | "FINANCIAL PERFORMANCE (6 MONTHS)"         |
| --text-chart-toggle        | 11px | 600    | 1.0    | 1px uppercase   | "WEEKLY" / "MONTHLY" toggle tabs           |
| --text-chart-axis          | 11px | 400    | 1.0    | 0px             | JAN, FEB, MAR, APR, MAY, JUN axis labels   |
| --text-chart-tooltip       | 11px | 700    | 1.0    | 0px             | "145M" tooltip di atas bar aktif           |
| --text-activity-title      | 14px | 600    | 1.3    | 0px             | "Pembayaran terbaru dari Naufal"            |
| --text-activity-meta       | 11px | 400    | 1.4    | 0px             | "2 minutes ago • Rp 1,200,000"             |
| --text-pt-name             | 13px | 500    | 1.3    | 0px             | "Coach Adrian", "Coach Sarah"              |
| --text-pt-count            | 13px | 700    | 1.3    | 0px             | "128 Sesi", "92 Sesi" (kuning)             |
| --text-insight-label       | 10px | 700    | 1.2    | 1.5px uppercase | "PAKET PALING POPULER", "PT SESI TERBANYAK"|
| --text-insight-value       | 15px | 700    | 1.3    | 0px             | "Platinum Membership", "Coach Adrian"      |
| --text-footer-stat-label   | 10px | 600    | 1.2    | 1.5px uppercase | "MEMBER GROWTH", "RETENTION RATE"          |
| --text-footer-stat-number  | 20px | 800    | 1.0    | 0px             | "84%", "92.1%", "48 / 50"                 |
| --text-footer-delta        | 11px | 600    | 1.0    | 0px             | "+5.2%", "+1.8%" delta positif             |
| --text-footer-timestamp    | 10px | 400    | 1.3    | 0.5px           | "LAST UPDATE Oct 12, 2023 - 14:45 WIB"    |
| --text-nav-item            | 13px | 500    | 1.4    | 0px             | Sidebar navigation items                   |
| --text-nav-active          | 13px | 700    | 1.4    | 0px             | Sidebar active item (DASHBOARD)            |
| --text-sidebar-brand       | 14px | 700    | 1.2    | 0px             | "Editorial Athletics"                      |
| --text-sidebar-subbrand    | 10px | 500    | 1.2    | 1px uppercase   | "ELITE MANAGEMENT"                         |
| --text-search              | 13px | 400    | 1.0    | 0px             | Search bar input                           |
| --text-audit-btn           | 11px | 700    | 1.0    | 1px uppercase   | "VIEW FULL AUDIT LOG"                      |
| --text-revenue-target      | 12px | 400    | 1.3    | 0px             | "Target: 150M" sub-label pada revenue card |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px)
| Token          | Value | Usage                                                     |
|----------------|-------|-----------------------------------------------------------|
| --space-xs     | 4px   | Badge padding, dot gap, tiny gaps                        |
| --space-sm     | 8px   | Icon-to-text gap, activity item inner gap                |
| --space-md     | 12px  | Card inner padding vertical, section label gap           |
| --space-base   | 16px  | Standard component margin, card padding horizontal       |
| --space-lg     | 20px  | Grid gap between cards, section spacing                  |
| --space-xl     | 24px  | Panel padding, bottom section gap                        |
| --space-2xl    | 32px  | Major section separation (chart → bottom panels)         |
| --space-3xl    | 48px  | Page top padding                                         |

### Border Radius
| Token          | Value | Usage                                                     |
|----------------|-------|-----------------------------------------------------------|
| --radius-xs    | 4px   | Small badges, toggle chips                               |
| --radius-sm    | 6px   | Input fields, chart toggle buttons                       |
| --radius-md    | 10px  | Stat cards, activity panel, PT trend panel               |
| --radius-lg    | 14px  | Large panels (chart panel, quick insights panel)         |
| --radius-xl    | 20px  | Modal outer containers                                   |
| --radius-full  | 50%   | Avatar circles, activity icon containers                 |

### Box Shadows
| Token            | Value                              | Usage                             |
|------------------|------------------------------------|-----------------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)         | Stat cards, panels default        |
| --shadow-hover   | 0 8px 20px rgba(0,0,0,0.6)        | Cards/panels on hover             |
| --shadow-button  | 0 2px 6px rgba(245,195,0,0.3)     | CTA/audit log button              |
| --shadow-sidebar | 2px 0 8px rgba(0,0,0,0.5)         | Sidebar right edge                |
| --shadow-modal   | 0 8px 32px rgba(0,0,0,0.7)        | Modal overlays                    |

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Total Canvas:     ~1140 × 1060 px
Sidebar:          220px wide × 100vh (fixed)
Header Bar:       calc(100vw - 220px) × 56px (sticky)
Main Content:     calc(100vw - 220px), padding: 20px all sides
Footer Stats Bar: calc(100vw - 220px) × 60px (bottom strip, non-fixed)
Content Gap:      20px
```

### ASCII Layout Diagram
```
┌─────────────────────┬──────────────────────────────────────────────────────────┐
│  SIDEBAR (220px)    │        HEADER BAR (56px height)                          │
│  ───────────────    │  ─────────────────────────────────────────────────────   │
│  ◈ Editorial        │  DASHBOARD OVERVIEW   [🔍 Search members, PT...]  🔔 ❓ 👤│
│    Athletics        ├──────────────────────────────────────────────────────────┤
│    ELITE MGMT       │                                                           │
│  ───────────────    │  ┌──────────────┐ ┌──────────────┐ ┌────────────┐ ┌────┐│
│  ⊞ Dashboard ◄AKTIF │  │TOTAL MEMBER  │ │ TOTAL PT     │ │ BOOKING    │ │ Rp ││
│  👥 Member          │  │ AKTIF        │ │ AKTIF        │ │ HARI INI   │ │145M││
│  📅 Paket Membership│  │ 1,250        │ │ 48           │ │ 82         │ │────││
│  ⭐ Personal Trainer│  │ +12% vs last │ │ 98% capacity │ │ Next 14:00 │ │150M││
│  📋 Booking & Sesi  │  └──────────────┘ └──────────────┘ └────────────┘ └────┘│
│  💰 Pembayaran      │                                                           │
│  🏋 Alat Gym        │  ┌────────────────────────────┐  ┌──────────────────────┐│
│  🔍 Audit Trail     │  │ Membership Sales Trend      │  │ Recent Activity      ││
│  📊 Laporan         │  │ FINANCIAL PERF (6 MONTHS)   │  │ REAL-TIME GYM LOGS   ││
│  ⚙  Pengaturan      │  │ [WEEKLY] [MONTHLY▼]         │  │                      ││
│  ───────────────    │  │  📊 Bar Chart (JAN-JUN)     │  │ • Pembayaran Naufal  ││
│  [👤] Alex Mercer   │  │  JUN bar = kuning (#F5C300) │  │ • Booking Budi       ││
│      ELITE ADMIN    │  │  Others = muted dark        │  │ • Perubahan Platinum ││
│                     │  └────────────────────────────┘  │ • Maintenance Alert  ││
│                     │                                   └──────────────────────┘│
│                     │  ┌──────────────────┐ ┌──────────────────────────────┐   │
│                     │  │ Booking PT Trend  │ │ Quick Insights               │   │
│                     │  │ Coach Adrian 128  │ │ ☆ Platinum Membership        │   │
│                     │  │ Coach Sarah  92   │ │ 👤 Coach Adrian              │   │
│                     │  │ Coach Budi   76   │ │ 🏋 Power Rack                │   │
│                     │  └──────────────────┘ │ [VIEW FULL AUDIT LOG]        │   │
│                     │                        └──────────────────────────────┘   │
│                     │  ══════════════════════════════════════════════════════   │
│                     │  MEMBER GROWTH  RETENTION RATE  ACTIVE PT  LAST UPDATE   │
│                     │  84% +5.2%      92.1% +1.8%     48/50      Oct 12, 2023  │
└─────────────────────┴──────────────────────────────────────────────────────────┘
```

---

## 5. KOMPONEN: SIDEBAR

### 5.1 Container Sidebar
```
Width:          220px
Height:         100vh
Background:     #141000
Border-right:   1px solid #2A2400
Box-shadow:     2px 0 8px rgba(0,0,0,0.5)
Position:       fixed, left: 0, top: 0
Z-index:        200
Overflow-y:     auto
Display:        flex flex-column
```

### 5.2 Area Logo / Brand
```
Container:
  Padding:      16px 16px 14px
  Border-bottom: 1px solid #2A2400

Logo Icon:
  Width/Height: 32px
  Fill:         #F5C300

Brand Name:
  Text:         "Editorial Athletics"
  Font-size:    14px
  Font-weight:  700
  Color:        #FFFFFF

Sub-brand:
  Text:         "ELITE MANAGEMENT"
  Font-size:    10px
  Font-weight:  500
  Color:        #8A8070
  Letter-spacing:1px
  Text-transform:uppercase
```

### 5.3 Menu Item (Default State)
```
Display:        flex, flex-direction row
Align-items:    center
Padding:        10px 16px
Height:         40px
Gap:            10px

Icon:
  Width:        16px
  Color:        #8A8070

Text:
  Font-size:    13px
  Font-weight:  500
  Color:        #8A8070

Hover state:
  Background:   #1E1900
  Icon-color:   #D4AA00
  Text-color:   #D4AA00
```

### 5.4 Menu Item (Active State — Dashboard)
```
Background:     #252000
Border-left:    3px solid #F5C300
Padding-left:   13px
Icon-color:     #F5C300
Text-color:     #F5C300
Font-weight:    700
```

### 5.5 Daftar Navigation Items (Urutan)
```
1.  ⊞  Dashboard          ← ACTIVE (screen ini)
2.  👥  Member
3.  📅  Paket Membership
4.  ⭐  Personal Trainer
5.  📋  Booking & Sesi PT
6.  💰  Pembayaran
7.  🏋  Alat Gym
8.  🔍  Audit Trail
9.  📊  Laporan
10. ⚙   Pengaturan
```

### 5.6 Profile Area (Bottom)
```
Position:       margin-top auto
Padding:        12px 16px
Border-top:     1px solid #2A2400

Avatar:
  Width:        36px
  Height:       36px
  Border-radius:50%
  Object-fit:   cover (foto profil nyata / illustrated avatar)

Name:
  Text:         "Alex Mercer"
  Font-size:    13px
  Font-weight:  600
  Color:        #FFFFFF

Role:
  Text:         "ELITE ADMIN"
  Font-size:    10px
  Font-weight:  500
  Color:        #8A8070
  Letter-spacing:1px
  Text-transform:uppercase
```

---

## 6. KOMPONEN: TOP HEADER BAR

### 6.1 Container
```
Height:         56px
Background:     #1E1900
Border-bottom:  1px solid #2A2400
Padding:        0 20px
Display:        flex, align-items center, justify-content space-between
Position:       sticky, top 0
Z-index:        100
Width:          calc(100vw - 220px)
```

### 6.2 Kiri — Breadcrumb
```
Text:           "DASHBOARD OVERVIEW"
Font-size:      18px
Font-weight:    700
Color:          #F5C300
Letter-spacing: 2px
Text-transform: uppercase
```

### 6.3 Tengah — Search Bar
```
Container:
  Width:        300px
  Height:       32px
  Background:   #2A2400
  Border:       1px solid #352E00
  Border-radius:6px
  Padding:      0 10px
  Gap:          8px

Search Icon:
  Width:        14px
  Color:        #5A5040

Input:
  Placeholder:  "Search members, PT, or sessions..."
  Font-size:    13px
  Color:        #FFFFFF
  Placeholder-color: #5A5040

  Focus state:
    Border (parent): 1px solid #F5C300
```

### 6.4 Kanan — Action Icons
```
Display:        flex, align-items center, gap 14px

Notification Bell:
  Icon-size:    20px
  Color:        #8A8070
  Hover-color:  #F5C300

Help / Question Mark:
  Icon-size:    20px
  Color:        #8A8070
  Hover-color:  #F5C300

Profile Avatar:
  Width:        28px
  Height:       28px
  Border-radius:50%
  Object-fit:   cover (illustrated avatar wajah)
  Cursor:       pointer
```

---

## 7. KOMPONEN: STAT CARDS (ROW ATAS)

### 7.1 Grid Container
```
Display:        grid
Grid-template-columns: repeat(4, 1fr)
Gap:            20px
Margin-bottom:  20px
```

### 7.2 Stat Card — Default (3 cards kiri)

#### Card 1: Total Member Aktif
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  10px
Padding:        20px
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)

Label:
  Text:         "TOTAL MEMBER AKTIF"
  Font-size:    11px
  Font-weight:  600
  Color:        #8A8070
  Letter-spacing:1.5px
  Text-transform:uppercase
  Margin-bottom:8px

Number:
  Text:         "1,250"
  Font-size:    32px
  Font-weight:  800
  Color:        #FFFFFF
  Font-family:  monospace (JetBrains Mono)
  Margin-bottom:8px

Sub-label / Delta:
  Icon:         ↑ (up arrow)
  Icon-color:   #4CAF50
  Text:         "+12% vs last month"
  Font-size:    12px
  Font-weight:  400
  Color:        #4CAF50
```

#### Card 2: Total PT Aktif
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  10px
Padding:        20px

Label:          "TOTAL PT AKTIF"
Number:         "48"  (Font-size: 28px, Weight: 800, Color: #FFFFFF)

Sub-label:
  Icon:         ✓ (checkmark, green circle)
  Text:         "98% capacity used"
  Color:        #8A8070
  Font-size:    12px
```

#### Card 3: Booking Hari Ini
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  10px
Padding:        20px

Label:          "BOOKING HARI INI"
Number:         "82"  (Font-size: 28px, Weight: 800, Color: #FFFFFF)

Sub-label:
  Icon:         🕐 (clock icon, color #8A8070)
  Text:         "Next: 14:00 session"
  Color:        #8A8070
  Font-size:    12px
```

### 7.3 Stat Card — Revenue (card kanan, KUNING)
```
Background:     #F5C300
Border:         none
Border-radius:  10px
Padding:        20px
Box-shadow:     0 4px 16px rgba(245,195,0,0.3)

Label:
  Text:         "PENDAPATAN BULAN INI"
  Font-size:    11px
  Font-weight:  600
  Color:        #1A1500 (gelap, kontras di atas kuning)
  Letter-spacing:1.5px
  Text-transform:uppercase
  Margin-bottom:6px

Number:
  Text:         "Rp 145.2M"
  Font-size:    28px
  Font-weight:  800
  Color:        #1A1500
  Font-family:  monospace

Sub-label:
  Icon:         💳 (card/payment icon, color #1A1500 opacity 0.6)
  Text:         "Target: 150M"
  Font-size:    12px
  Color:        rgba(26,21,0,0.7)

Decorative element (kanan bawah):
  Opacity:      0.15
  Color:        #1A1500
  Content:      large background icon (currency/chart abstract)
```

---

## 8. KOMPONEN: MEMBERSHIP SALES TREND (CHART PANEL)

### 8.1 Container
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  14px
Padding:        24px
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
Width:          ~60% of content area (kiri dari Recent Activity)
Min-height:     320px
```

### 8.2 Panel Header
```
Display:        flex, justify-content space-between, align-items flex-start

Kiri:
  Title:
    Text:       "Membership Sales Trend"
    Font-size:  18px
    Font-weight:700
    Color:      #FFFFFF

  Sub-title:
    Text:       "FINANCIAL PERFORMANCE (6 MONTHS)"
    Font-size:  11px
    Font-weight:600
    Color:      #8A8070
    Letter-spacing:2px
    Text-transform:uppercase
    Margin-top: 4px

Kanan — Toggle WEEKLY / MONTHLY:
  Container:
    Background: #1A1500
    Border:     1px solid #352E00
    Border-radius:6px
    Display:    flex
    Gap:        0

  Tab Inactive (WEEKLY):
    Padding:    6px 12px
    Font-size:  11px
    Font-weight:600
    Color:      #8A8070
    Text-transform:uppercase
    Letter-spacing:1px
    Background: transparent
    Cursor:     pointer

  Tab Active (MONTHLY):
    Background: #F5C300
    Color:      #1A1500
    Border-radius:4px
    Padding:    6px 12px
```

### 8.3 Bar Chart
```
Chart Type:     Vertical bar chart
Data:           6 bulan (JAN, FEB, MAR, APR, MAY, JUN)
Height:         ~220px
Width:          100% of panel

Bar — Inactive (JAN–MAY):
  Fill:         #3A3300
  Border-radius:4px top
  Opacity:      1

Bar — Active (JUN, current month):
  Fill:         #F5C300
  Border-radius:4px top
  Box-shadow:   0 0 12px rgba(245,195,0,0.4)

Tooltip (di atas bar JUN):
  Background:   #F5C300
  Color:        #1A1500
  Font-size:    11px
  Font-weight:  700
  Padding:      4px 8px
  Border-radius:4px
  Content:      "145M"
  Arrow:        small downward triangle pointing to bar

X-axis Labels:
  Font-size:    11px
  Font-weight:  400
  Color:        #5A5040
  Text-transform:uppercase
  Margin-top:   8px
```

---

## 9. KOMPONEN: RECENT ACTIVITY PANEL

### 9.1 Container
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  14px
Padding:        24px
Width:          ~38% of content area (kanan dari chart)
Min-height:     320px
```

### 9.2 Panel Header
```
Title:
  Text:         "Recent Activity"
  Font-size:    18px
  Font-weight:  700
  Color:        #FFFFFF

Sub-title:
  Text:         "REAL-TIME GYM LOGS"
  Font-size:    11px
  Font-weight:  600
  Color:        #8A8070
  Letter-spacing:2px
  Text-transform:uppercase
  Margin-top:   4px
```

### 9.3 Activity Item (List)
```
Display:        flex, align-items flex-start, gap 12px
Padding:        12px 0
Border-bottom:  1px solid #352E00
Last-child: border-bottom none

Icon Container:
  Width:        36px
  Height:       36px
  Border-radius:50%
  Background:   #2A2400
  Display:      flex, align-items center, justify-content center
  Flex-shrink:  0

  Icon-size:    16px
  Icon-color:   varies per type (see below)

Content:
  Flex: 1

  Title:
    Font-size:  14px
    Font-weight:600
    Color:      #FFFFFF
    Line-height:1.3

  Meta:
    Font-size:  11px
    Font-weight:400
    Color:      #8A8070
    Margin-top: 3px
```

### 9.4 Activity Type → Icon Mapping
```
1. Pembayaran terbaru dari Naufal
   Icon:        💳 payment/card icon
   Icon-color:  #F5C300
   Meta:        "2 minutes ago • Rp 1,200,000"

2. Booking terbaru dari Budi
   Icon:        📅 calendar icon
   Icon-color:  #3B82F6
   Meta:        "15 minutes ago • Sessions with Coach Adrian"

3. Perubahan data paket Platinum
   Icon:        ✏️ edit/pencil icon
   Icon-color:  #F59E0B
   Meta:        "1 hour ago • Price adjusted by Admin"

4. Maintenance Alert: Treadmill #4
   Icon:        ⚠️ triangle warning icon
   Icon-color:  #EF4444
   Meta:        "3 hours ago • Scheduled for tomorrow"
```

---

## 10. KOMPONEN: BOOKING PT TREND PANEL

### 10.1 Container
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  10px
Padding:        20px
Width:          ~48% of content row (kiri dari Quick Insights)
```

### 10.2 Panel Header
```
Title:
  Text:         "Booking PT Trend"
  Font-size:    16px
  Font-weight:  700
  Color:        #FFFFFF
  Margin-bottom:16px
```

### 10.3 PT Progress Row
```
Display:        flex, flex-direction column
Gap:            12px

Per Row:
  Header row:
    Display:    flex, justify-content space-between
    Name:
      Text:     "Coach Adrian" / "Coach Sarah" / "Coach Budi"
      Font-size:13px
      Font-weight:500
      Color:    #FFFFFF

    Count:
      Text:     "128 Sesi" / "92 Sesi" / "76 Sesi"
      Font-size:13px
      Font-weight:700
      Color:    #F5C300

  Progress Bar:
    Height:     6px
    Background: #3A3300  (track)
    Border-radius:3px
    Margin-top: 6px

    Fill:
      Background: #F5C300
      Border-radius:3px
      Width:    proportional — Coach Adrian ~80%, Coach Sarah ~57%, Coach Budi ~47%
```

---

## 11. KOMPONEN: QUICK INSIGHTS PANEL

### 11.1 Container
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  10px
Padding:        20px
Width:          ~50% of content row (kanan dari PT Trend)
```

### 11.2 Panel Header
```
Title:
  Text:         "Quick Insights"
  Font-size:    16px
  Font-weight:  700
  Color:        #FFFFFF
  Margin-bottom:16px
```

### 11.3 Insight Row
```
Display:        flex, align-items center, gap 14px
Padding:        10px 0
Border-bottom:  1px solid #352E00

Icon Container:
  Width:        36px
  Height:       36px
  Border-radius:8px
  Background:   #1A1500
  Display:      flex center

Per Insight:

1. PAKET PALING POPULER
   Icon:        ☆ star icon, color #F5C300
   Label:       "PAKET PALING POPULER"
   Value:       "Platinum Membership"

2. PT SESI TERBANYAK
   Icon:        👤 person icon, color #3B82F6
   Label:       "PT SESI TERBANYAK"
   Value:       "Coach Adrian"

3. ALAT GYM TERPOPULER
   Icon:        🏋 dumbbell/gym icon, color #F5C300
   Label:       "ALAT GYM TERPOPULER"
   Value:       "Power Rack"

Label:
  Font-size:    10px
  Font-weight:  700
  Color:        #8A8070
  Letter-spacing:1.5px
  Text-transform:uppercase

Value:
  Font-size:    15px
  Font-weight:  700
  Color:        #FFFFFF
```

### 11.4 Audit Log Button
```
Display:        block
Width:          100%
Margin-top:     16px
Padding:        10px 16px
Background:     transparent
Border:         1px solid #352E00
Border-radius:  6px
Text:           "VIEW FULL AUDIT LOG"
Font-size:      11px
Font-weight:    700
Color:          #8A8070
Text-align:     center
Letter-spacing: 1px
Text-transform: uppercase
Cursor:         pointer

Hover state:
  Border-color: #F5C300
  Color:        #F5C300
```

---

## 12. KOMPONEN: FOOTER STATS BAR

### 12.1 Container
```
Background:     #1E1900
Border-top:     1px solid #352E00
Padding:        16px 20px
Display:        flex, align-items center
Gap:            40px
Margin-top:     20px
```

### 12.2 Stat Item
```
Display:        flex, flex-direction column

Label:
  Font-size:    10px
  Font-weight:  600
  Color:        #8A8070
  Letter-spacing:1.5px
  Text-transform:uppercase
  Margin-bottom:4px

Number + Delta Row:
  Display:      flex, align-items baseline, gap 6px

  Number:
    Font-size:  20px
    Font-weight:800
    Color:      #FFFFFF

  Delta:
    Font-size:  11px
    Font-weight:600
    Color:      #4CAF50  (positif)
```

### 12.3 Data Stats
```
1. MEMBER GROWTH
   Number:      "84%"
   Delta:       "+5.2%"

2. RETENTION RATE
   Number:      "92.1%"
   Delta:       "+1.8%"

3. ACTIVE PT
   Number:      "48 / 50"
   Sub-text:    "Capacity" (font-size: 11px, color: #8A8070, setelah angka)
   Delta:       (none)
```

### 12.4 Timestamp (kanan)
```
Margin-left:    auto

Label:
  Text:         "LAST UPDATE"
  Font-size:    10px
  Font-weight:  600
  Color:        #8A8070
  Letter-spacing:1px
  Text-transform:uppercase

Value:
  Text:         "Oct 12, 2023 - 14:45 WIB"
  Font-size:    12px
  Font-weight:  400
  Color:        #FFFFFF
  Margin-top:   2px
```

---

## 13. STATES & INTERACTIONS

### 13.1 Stat Cards
```
Default:    normal display
Hover:      border-color → #F5C300 (1px), box-shadow → 0 8px 20px rgba(0,0,0,0.6)
Transition: 0.2s ease
```

### 13.2 Chart Toggle (Weekly / Monthly)
```
Click tab inactive → active:
  Background berubah ke #F5C300
  Color berubah ke #1A1500
  Chart data di-update (animasi fade + redraw bars)
  Durasi: 300ms ease
```

### 13.3 Bar Chart Hover
```
Hover di atas bar:
  Opacity bar yang di-hover: 1
  Opacity bar lain: 0.5
  Tooltip muncul: scale(0) → scale(1), durasi 150ms
```

### 13.4 Recent Activity Auto-update
```
List item baru muncul dari atas (slide-down + fade-in):
  translateY(-16px) → translateY(0)
  Opacity: 0 → 1
  Durasi: 300ms ease-out
  Item lama tergeser ke bawah
```

### 13.5 Progress Bars (PT Trend)
```
Mount animation:
  Width: 0% → target% dalam 800ms ease-out
  Trigger: Intersection Observer saat panel masuk viewport
```

---

## 14. DATA MODEL

### 14.1 Summary Stats (Top Cards)
```typescript
interface DashboardStats {
  totalMemberAktif: number;         // 1250
  memberGrowthPercent: number;      // +12
  totalPTAktif: number;             // 48
  ptCapacityPercent: number;        // 98
  bookingHariIni: number;           // 82
  nextSessionTime: string;          // "14:00"
  pendapatanBulanIni: number;       // 145200000
  targetPendapatan: number;         // 150000000
}
```

### 14.2 Chart Data
```typescript
interface SalesTrendData {
  period: 'weekly' | 'monthly';
  data: Array<{
    label: string;     // "JAN", "FEB", dst
    value: number;     // dalam juta (ex: 90, 100, 110, ...)
    isActive: boolean; // true hanya untuk bulan saat ini
  }>;
}
```

### 14.3 Recent Activity
```typescript
interface ActivityLog {
  id: string;
  type: 'payment' | 'booking' | 'data_change' | 'maintenance';
  title: string;
  meta: string;
  timestamp: Date;
  relativeTime: string;  // "2 minutes ago"
}
```

### 14.4 PT Trend
```typescript
interface PTBookingTrend {
  trainerName: string;   // "Coach Adrian"
  sessionCount: number;  // 128
  maxSessions: number;   // untuk kalkulasi % bar
}
```

### 14.5 Quick Insights
```typescript
interface QuickInsights {
  paketTerpopuler: string;      // "Platinum Membership"
  ptSesiTerbanyak: string;      // "Coach Adrian"
  alatTerpopuler: string;       // "Power Rack"
}
```

### 14.6 Footer Stats
```typescript
interface FooterStats {
  memberGrowth: number;         // 84
  memberGrowthDelta: number;    // +5.2
  retentionRate: number;        // 92.1
  retentionDelta: number;       // +1.8
  activePT: number;             // 48
  ptCapacity: number;           // 50
  lastUpdated: string;          // "Oct 12, 2023 - 14:45 WIB"
}
```

---

## 15. AKSESIBILITAS (A11Y)

```
1. Stat Cards:
   - role="region" aria-label="Dashboard Statistics"
   - Tiap card: aria-label="[label]: [value], [delta]"

2. Chart:
   - role="img" aria-label="Membership Sales Trend bar chart, 6 months data"
   - Sediakan fallback tabel data untuk screen reader

3. Toggle WEEKLY/MONTHLY:
   - role="tablist"
   - Tiap tab: role="tab", aria-selected="true/false"

4. Recent Activity:
   - role="log" aria-live="polite" aria-label="Recent Activity"
   - Setiap entry: role="listitem"

5. Progress bars (PT Trend):
   - role="progressbar"
   - aria-valuenow, aria-valuemin="0", aria-valuemax="[max]"
   - aria-label="[nama trainer]: [count] sesi"

6. "VIEW FULL AUDIT LOG" button:
   - Minimum hit target: 44px height
   - aria-label="View full audit log"
```

---

## 16. CATATAN AI — IMPLEMENTATION NOTES (15 poin)

1. **Stat Cards Revenue Highlight**: Revenue card (kuning #F5C300) adalah satu-satunya card dengan background berwarna di row ini. Ini desain intentional untuk menarik perhatian admin ke metrik finansial utama. Pastikan teks di atasnya menggunakan `#1A1500` agar contrast ratio ≥ 4.5:1 (WCAG AA).

2. **Bar Chart Library**: Gunakan `Recharts` (React) atau `Chart.js` dengan konfigurasi custom. Bar JUN harus selalu di-highlight otomatis berdasarkan bulan berjalan. Gunakan `Date.now()` untuk menentukan bar aktif secara dinamis, bukan hardcode.

3. **Chart Toggle State**: State `period: 'weekly' | 'monthly'` dikelola di level komponen chart. Saat toggle berpindah, fetch data baru dari API dengan param `?period=weekly` atau `?period=monthly` dan re-render chart dengan animasi `ease-out` 300ms.

4. **Recent Activity Real-Time**: Gunakan WebSocket atau Server-Sent Events (SSE) untuk push activity log terbaru. Item baru muncul di atas list dengan animasi `slide-down + fade-in`. Batasi tampilan maksimal 4–6 item; item lama dihapus dari DOM setelah overflow (bukan hapus dari DB).

5. **Progress Bar Calculation**: Width bar PT Trend = `(sessionCount / maxSessionCount) * 100%`. Coach dengan sesi terbanyak selalu 100% sebagai baseline. Animasi fill saat mount: `width: 0 → target` dalam 800ms `ease-out` via Intersection Observer.

6. **Footer Stats Auto-Refresh**: Footer bar sebaiknya auto-refresh setiap 60 detik menggunakan polling REST API. Tampilkan animasi fade-out → update → fade-in saat data berubah. Update timestamp "LAST UPDATE" setiap kali data di-refresh.

7. **Responsive Chart**: Chart panel dan Recent Activity panel menggunakan `display: flex; gap: 20px` di desktop. Di tablet (≤ 1024px), stack vertikal. Di mobile (≤ 640px), chart menjadi horizontal scroll dengan `overflow-x: auto`.

8. **Delta Indicator Component**: Buat reusable `<DeltaBadge value={+12} />` component yang otomatis render ↑ (hijau) untuk positif dan ↓ (merah) untuk negatif. Gunakan di stat cards dan footer stats secara konsisten.

9. **Revenue Card Decorative Element**: Elemen dekoratif di sudut kanan bawah revenue card (ikon abstrak dengan opacity rendah) menggunakan `position: absolute; right: -8px; bottom: -8px; opacity: 0.12; transform: rotate(-10deg)`. Container card harus `position: relative; overflow: hidden`.

10. **Quick Insights Data Source**: Data "Paket Paling Populer", "PT Sesi Terbanyak", dan "Alat Gym Terpopuler" di-aggregate dari query DB dengan time range rolling 30 hari. Cache hasil di Redis dengan TTL 15 menit untuk performa optimal.

11. **Activity Icon Color System**: Buat mapping object `ACTIVITY_ICON_MAP` yang memetakan `type → { icon, color }`:
    - `payment` → `{ icon: CreditCard, color: '#F5C300' }`
    - `booking` → `{ icon: Calendar, color: '#3B82F6' }`
    - `data_change` → `{ icon: Edit, color: '#F59E0B' }`
    - `maintenance` → `{ icon: AlertTriangle, color: '#EF4444' }`

12. **Search Bar Global Search**: Search bar di header berfungsi sebagai global search lintas entity (member, PT, sesi). Implementasi: debounce 300ms → query API `/search?q=...` → tampilkan dropdown result dengan kategori (Members, Trainers, Sessions). Tutup dropdown saat klik di luar atau tekan Escape.

13. **Sidebar Active State**: Saat navigasi ke Dashboard, set `activePage = 'dashboard'` di global state/context. Sidebar membaca state ini untuk render active styling. Jangan hardcode active state per-page; gunakan route matching (`usePathname()` di Next.js atau `useLocation()` di React Router).

14. **Footer Bar Positioning**: Footer stats bar bukan `position: fixed` — ia mengikuti alur dokumen di bagian bawah konten. Ini berbeda dengan Equipment Management screen yang memiliki AI Bar fixed. Pastikan tidak ada `padding-bottom` tambahan pada main content jika AI bar tidak ada di screen ini.

15. **"VIEW FULL AUDIT LOG" Navigation**: Tombol ini me-navigate ke route `/admin/audit-trail`. Implementasikan sebagai `<Link>` (Next.js) atau `<NavLink>` (React Router) bukan `<button onClick>`, agar mendukung right-click → open in new tab dan browser history yang benar.

---

*Spec ini generated dari analisis visual screen Admin_Dashboard_Overview.png*
*Design system reference: ADMIN_EQUIPMENT_MANAGEMENT_UI_SPEC.md*
*Total sections: 16 | Detail level: ⭐⭐⭐⭐⭐ Full Detail*

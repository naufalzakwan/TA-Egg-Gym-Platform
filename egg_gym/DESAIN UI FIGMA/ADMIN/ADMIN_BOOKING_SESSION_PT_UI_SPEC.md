# ADMIN_BOOKING_SESSION_PT_UI_SPEC.md
# Egg Gym App — Admin Booking & Sesi PT Screen
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Admin > Booking & Sesi PT > Booking & Sesi Monitoring
# Resolution: ~1220 × 960 px
# Last Updated: 2026-06-25

---

## 1. DESIGN TOKENS — COLOR PALETTE

| Token Name                      | HEX Value              | Usage                                                         |
|---------------------------------|------------------------|---------------------------------------------------------------|
| --color-bg-primary              | #1A1500                | Main content background                                       |
| --color-bg-sidebar              | #141000                | Sidebar background                                            |
| --color-bg-header               | #1A1500                | Top header bar background (menyatu dengan bg)                 |
| --color-bg-table                | #252000                | Booking table panel background                                |
| --color-bg-table-row            | #252000                | Table row background default                                  |
| --color-bg-table-row-alt        | #1E1900                | Alternating row background (subtle stripe)                    |
| --color-bg-table-row-hover      | #2E2800                | Table row hover background                                    |
| --color-bg-live-card            | #252000                | Live Progress session card background                         |
| --color-bg-live-card-inner      | #1E1900                | Inner data area inside live progress card                     |
| --color-bg-incentive-card       | #252000                | Coach Incentive Active card background                        |
| --color-bg-incentive-icon       | #F5C300                | Star icon container background (incentive card)               |
| --color-bg-avatar               | #3A3300                | Member/coach avatar placeholder background                    |
| --color-bg-search               | #252000                | Search bar background (header)                                |
| --color-accent-primary          | #F5C300                | Active tab (MENUNGGU), status badge, progress fill, icon      |
| --color-accent-hover            | #E0B000                | Button/tab hover                                              |
| --color-text-primary            | #FFFFFF                | Member name, coach name, date/time, card title                |
| --color-text-secondary          | #8A8070                | Column headers, sub-labels, incentive description             |
| --color-text-muted              | #5A5040                | Tier labels, placeholder text, inactive tab text              |
| --color-text-on-accent          | #1A1500                | Text on yellow (active tab, status badge)                     |
| --color-text-page-title         | #F5C300                | "BOOKING & SESI MONITORING" header title                      |
| --color-text-incentive-title    | #F5C300                | "COACH INCENTIVE ACTIVE" title text                           |
| --color-text-incentive-bold     | #FFFFFF                | Bold terms in incentive description (Tier 2 Bonuses, Adrian)  |
| --color-text-progress-pct       | #F5C300                | Percentage text (65%, 22%)                                    |
| --color-text-session-meta       | #8A8070                | "TRAINING PROGRESS", "UPPER BODY STRENGTH", "SESSION: #12"    |
| --color-tab-active-bg           | #F5C300                | Active tab background                                         |
| --color-tab-active-text         | #1A1500                | Active tab text color                                         |
| --color-tab-inactive-text       | #8A8070                | Inactive tab text                                             |
| --color-tab-inactive-hover      | #D4AA00                | Inactive tab hover text                                       |
| --color-status-menunggu-bg      | #F5C300                | "MENUNGGU" status badge background                            |
| --color-status-menunggu-text    | #1A1500                | "MENUNGGU" status badge text                                  |
| --color-status-dikonfirmasi-bg  | #3B82F6                | "DIKONFIRMASI" badge background (tab label color ref)         |
| --color-status-selesai-bg       | #4CAF50                | "SELESAI" badge background                                    |
| --color-status-ditolak-bg       | #EF4444                | "DITOLAK" badge background                                    |
| --color-progress-fill           | #F5C300                | Training progress bar fill                                    |
| --color-progress-track          | #3A3300                | Training progress bar track                                   |
| --color-live-dot                | #EF4444                | Red blinking dot beside "LIVE PROGRESS"                       |
| --color-border-table            | #352E00                | Table panel border, row divider                               |
| --color-border-card             | #352E00                | Live progress card border                                     |
| --color-border-sidebar          | #2A2400                | Sidebar dividers                                              |
| --color-border-search           | #352E00                | Search bar border                                             |
| --color-border-search-focus     | #F5C300                | Search bar focus border                                       |
| --color-watermark               | rgba(245,195,0,0.04)   | Background watermark text ("BOOKING & SESSION")               |
| --color-coach-icon              | #F5C300                | Swap/assign arrows icon (coach column)                        |
| --color-overlay-dark            | rgba(0,0,0,0.7)        | Modal backdrop                                                |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Monospace:  "JetBrains Mono", "Fira Code", monospace (waktu/jadwal)
```

### Skala Tipografi Lengkap
| Token                          | Size | Weight | Line-H | Letter-Sp       | Usage                                              |
|--------------------------------|------|--------|--------|-----------------|----------------------------------------------------|
| --text-page-title              | 20px | 800    | 1.0    | 2px uppercase   | "BOOKING & SESI MONITORING" header                 |
| --text-tab-active              | 13px | 700    | 1.0    | 1px uppercase   | "MENUNGGU" tab aktif                               |
| --text-tab-inactive            | 13px | 500    | 1.0    | 1px uppercase   | "DIKONFIRMASI", "SELESAI", "DITOLAK"               |
| --text-table-col-header        | 11px | 700    | 1.0    | 1.5px uppercase | "MEMBER", "PERSONAL TRAINER", "JADWAL", "STATUS"   |
| --text-member-name             | 16px | 700    | 1.2    | 0px             | "Naufal Azhar", "Sarah Wijaya", "Budi Santoso"     |
| --text-member-tier             | 11px | 500    | 1.2    | 0px             | "Elite Tier", "Standard Tier", "VIP Tier"          |
| --text-coach-name              | 14px | 600    | 1.2    | 0px             | "Coach Adrian", "Coach Maya"                       |
| --text-jadwal-date             | 14px | 600    | 1.3    | 0px             | "24 Okt 2023", "25 Okt 2023"                       |
| --text-jadwal-time             | 13px | 400    | 1.3    | 0px             | "08:00 - 09:30", "14:00 - 15:00", "07:00 - 08:30" |
| --text-status-badge            | 11px | 700    | 1.0    | 1px uppercase   | "MENUNGGU" status badge                            |
| --text-live-section-title      | 16px | 800    | 1.0    | 2px uppercase   | "LIVE PROGRESS"                                    |
| --text-live-member-name        | 15px | 700    | 1.2    | 0px             | "Naufal Azhar", "Jessica Loh" (live card)          |
| --text-live-coach-sub          | 11px | 600    | 1.2    | 0.5px uppercase | "WITH COACH ADRIAN", "WITH COACH SARAH"            |
| --text-live-progress-label     | 10px | 700    | 1.2    | 1.5px uppercase | "TRAINING PROGRESS"                                |
| --text-live-progress-pct       | 20px | 800    | 1.0    | 0px             | "65%", "22%"                                       |
| --text-live-session-meta       | 11px | 600    | 1.2    | 1px             | "UPPER BODY STRENGTH", "HIGH INTENSITY CARDIO"     |
| --text-live-session-number     | 11px | 600    | 1.2    | 1px             | "SESSION: #12", "SESSION: #04"                     |
| --text-incentive-title         | 13px | 800    | 1.2    | 1px uppercase   | "COACH INCENTIVE ACTIVE"                           |
| --text-incentive-body          | 13px | 400    | 1.5    | 0px             | Deskripsi incentive (normal weight)                |
| --text-incentive-bold          | 13px | 700    | 1.5    | 0px             | "Tier 2 Bonuses", "Coach Adrian", "3 more sessions"|
| --text-nav-item                | 13px | 500    | 1.4    | 0px             | Sidebar nav items                                  |
| --text-nav-active              | 13px | 700    | 1.4    | 0px             | "BOOKING & SESI PT" active                         |
| --text-sidebar-brand           | 14px | 700    | 1.2    | 0px             | "Editorial Athletics"                              |
| --text-sidebar-subbrand        | 10px | 500    | 1.2    | 1px uppercase   | "ELITE MANAGEMENT"                                 |
| --text-profile-name            | 13px | 600    | 1.3    | 0px             | "Alex Rivera"                                      |
| --text-profile-role            | 10px | 500    | 1.2    | 1px uppercase   | "HEAD ADMINISTRATOR"                               |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px)
| Token          | Value | Usage                                                          |
|----------------|-------|----------------------------------------------------------------|
| --space-xs     | 4px   | Badge padding vertical, avatar-to-text gap minimum            |
| --space-sm     | 8px   | Icon-to-text gap, badge padding horizontal, row icon gap      |
| --space-md     | 12px  | Table row vertical padding, live card inner section gap       |
| --space-base   | 16px  | Table panel padding, live card padding, tab gap               |
| --space-lg     | 20px  | Between table panel and live section horizontal gap           |
| --space-xl     | 24px  | Page header-to-tabs gap, section margin                       |
| --space-2xl    | 32px  | Major section vertical separation                             |

### Border Radius
| Token          | Value | Usage                                                          |
|----------------|-------|----------------------------------------------------------------|
| --radius-xs    | 4px   | Status badge (MENUNGGU)                                        |
| --radius-sm    | 6px   | Tab buttons inactive, search input                             |
| --radius-md    | 8px   | Coach icon arrow container, avatar circle alt                  |
| --radius-lg    | 12px  | Table panel container, live progress card                      |
| --radius-xl    | 16px  | Incentive card                                                 |
| --radius-full  | 50%   | Member/coach avatar, live progress avatar                      |

### Box Shadows
| Token              | Value                              | Usage                                 |
|--------------------|------------------------------------|---------------------------------------|
| --shadow-panel     | 0 2px 8px rgba(0,0,0,0.4)         | Table panel, live cards               |
| --shadow-row-hover | 0 4px 12px rgba(0,0,0,0.3)        | Table row on hover                    |
| --shadow-tab-active| 0 2px 8px rgba(245,195,0,0.25)    | Active tab (MENUNGGU)                 |
| --shadow-sidebar   | 2px 0 8px rgba(0,0,0,0.5)         | Sidebar right edge                    |
| --shadow-live-dot  | 0 0 6px rgba(239,68,68,0.6)       | Red live dot pulse glow               |

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Total Canvas:     ~1220 × 960 px
Sidebar:          210px wide × 100vh (fixed)
Header Bar:       calc(100vw - 210px) × 56px (sticky)
Main Content:     calc(100vw - 210px), padding: 20px 24px
Left Column:      ~63% content width (tabs + booking table)
Right Column:     ~33% content width (Live Progress + Incentive)
Column Gap:       20px
```

### ASCII Layout Diagram
```
┌─────────────────────┬───────────────────────────────────────────────────────────────┐
│  SIDEBAR (210px)    │  HEADER (56px)                                                │
│  ───────────────    │  BOOKING & SESI MONITORING   [🔍 Search sessions...]  🔔 ❓ 👤 │
│  ◈ Editorial        ├───────────────────────────────────────────────────────────────┤
│    Athletics        │                                                               │
│    ELITE MGMT       │  ┌──────────────────────────────────────┐ ┌─────────────────┐│
│  ───────────────    │  │ [MENUNGGU▼] [DIKONFIRMASI] [SELESAI] [DITOLAK]           ││
│  ⊞ Dashboard        │  ├──────────────────────────────────────┤ │ LIVE PROGRESS 🔴││
│  👥 Member          │  │ MEMBER    PERSONAL  JADWAL  STATUS   │ │                 ││
│  📅 Paket Membership│  │           TRAINER                    │ │ ┌─────────────┐ ││
│  ⭐ Personal Trainer│  │ ──────────────────────────────────── │ │ │ Naufal Azhar│ ││
│  📋 Booking & Sesi  │  │ [👤]Naufal  Coach    24 Okt  MENUNGGU│ │ │ w/ Coach    │ ││
│     PT     ◄ AKTIF  │  │    Azhar   Adrian   08:00-  ────────│ │ │ Adrian      │ ││
│  💰 Pembayaran      │  │    Elite            09:30           │ │ │ 65% ████░░  │ ││
│  🏋 Alat Gym        │  │ ──────────────────────────────────── │ │ │ Upper Body  │ ││
│  🔍 Audit Trail     │  │ [👤]Sarah   Coach    24 Okt  MENUNGGU│ │ │ SESSION: #12│ ││
│  📊 Laporan         │  │    Wijaya  Maya     14:00-  ────────│ │ └─────────────┘ ││
│  ⚙  Pengaturan      │  │    Std              15:00           │ │ ┌─────────────┐ ││
│  ───────────────    │  │ ──────────────────────────────────── │ │ │ Jessica Loh │ ││
│  [👤] Alex Rivera   │  │ [👤]Budi    Coach    25 Okt  MENUNGGU│ │ │ w/ Coach    │ ││
│      HEAD ADMIN     │  │    Santoso Adrian   07:00-  ────────│ │ │ Sarah       │ ││
│                     │  │    VIP              08:30           │ │ │ 22% ██░░░░  │ ││
│                     │  └──────────────────────────────────── ┘ │ │ High Intens.│ ││
│                     │                                          │ │ SESSION: #04│ ││
│                     │   [watermark faint "BOOKING & SESSION"]  │ └─────────────┘ ││
│                     │                                          │ ┌─────────────┐ ││
│                     │                                          │ │ ⭐ COACH     │ ││
│                     │                                          │ │  INCENTIVE  │ ││
│                     │                                          │ │  ACTIVE...  │ ││
│                     │                                          │ └─────────────┘ ││
│                     │                                          └─────────────────┘│
└─────────────────────┴───────────────────────────────────────────────────────────────┘
```

---

## 5. KOMPONEN: SIDEBAR

### 5.1 Container
```
Width:          210px
Height:         100vh
Background:     #141000
Border-right:   1px solid #2A2400
Box-shadow:     2px 0 8px rgba(0,0,0,0.5)
Position:       fixed, left: 0, top: 0
Z-index:        200
Display:        flex flex-column
```

### 5.2 Area Brand
```
Padding:        16px 16px 14px
Border-bottom:  1px solid #2A2400

Logo Icon:
  Width/Height: 28px
  Fill:         #F5C300

Brand Name:
  Text:         "Editorial Athletics"
  Font-size:    14px
  Font-weight:  700
  Color:        #FFFFFF

Sub-brand:
  Text:         "ELITE MANAGEMENT"
  Font-size:    10px
  Color:        #8A8070
  Letter-spacing:1px
  Text-transform:uppercase
```

### 5.3 Navigation Items (Urutan)
```
1.  ⊞  Dashboard
2.  👥  Member
3.  📅  Paket Membership
4.  ⭐  Personal Trainer
5.  📋  Booking & Sesi PT    ← ACTIVE
6.  💰  Pembayaran
7.  🏋  Alat Gym
8.  🔍  Audit Trail
9.  📊  Laporan
10. ⚙   Pengaturan
```

### 5.4 Menu Item Active (Booking & Sesi PT)
```
Background:     #252000
Border-left:    3px solid #F5C300
Padding-left:   13px
Icon:           📋 calendar icon, color #F5C300
Text:           "BOOKING & SESI PT"
Font-size:      13px
Font-weight:    700
Color:          #F5C300
```

### 5.5 Profile Area (Bottom)
```
Padding:        12px 16px
Border-top:     1px solid #2A2400

Avatar:
  Width/Height: 36px
  Border-radius:50%
  Object-fit:   cover (illustrated portrait)

Name:
  Text:         "Alex Rivera"
  Font-size:    13px
  Font-weight:  600
  Color:        #FFFFFF

Role:
  Text:         "HEAD ADMINISTRATOR"
  Font-size:    10px
  Color:        #8A8070
  Letter-spacing:1px
  Text-transform:uppercase
```

---

## 6. KOMPONEN: TOP HEADER BAR

### 6.1 Container
```
Height:         56px
Background:     #1A1500
Border-bottom:  1px solid #2A2400
Padding:        0 24px
Display:        flex, align-items center, justify-content space-between
Position:       sticky, top: 0
Z-index:        100
Width:          calc(100vw - 210px)
```

### 6.2 Kiri — Page Title
```
Text:           "BOOKING & SESI MONITORING"
Font-size:      20px
Font-weight:    800
Color:          #F5C300
Letter-spacing: 2px
Text-transform: uppercase
```

### 6.3 Tengah-Kanan — Search Bar
```
Container:
  Width:        280px
  Height:       34px
  Background:   #252000
  Border:       1px solid #352E00
  Border-radius:6px
  Padding:      0 12px
  Display:      flex, align-items center, gap 8px

Search Icon:
  Width:        14px
  Color:        #5A5040

Input:
  Placeholder:  "Search sessions..."
  Font-size:    13px
  Color:        #FFFFFF
  Background:   transparent
  Placeholder-color: #5A5040

  Focus state:
    Border (parent): 1px solid #F5C300
```

### 6.4 Kanan — Icons + Avatar
```
Display:        flex, align-items center, gap 14px

Notification Bell:
  Icon-size:    20px
  Color:        #8A8070

Help:
  Icon-size:    20px
  Color:        #8A8070

Avatar:
  Width:        28px
  Height:       28px
  Border-radius:50%
  Object-fit:   cover
```

---

## 7. KOMPONEN: TAB FILTER (STATUS)

### 7.1 Container
```
Display:        flex, flex-direction row
Gap:            8px
Margin-bottom:  16px
```

### 7.2 Tab — Active (MENUNGGU)
```
Background:     #F5C300
Color:          #1A1500
Font-size:      13px
Font-weight:    700
Letter-spacing: 1px
Text-transform: uppercase
Padding:        10px 20px
Border-radius:  6px
Border:         none
Cursor:         pointer
Box-shadow:     0 2px 8px rgba(245,195,0,0.25)
```

### 7.3 Tab — Inactive (DIKONFIRMASI, SELESAI, DITOLAK)
```
Background:     transparent
Color:          #8A8070
Font-size:      13px
Font-weight:    500
Letter-spacing: 1px
Text-transform: uppercase
Padding:        10px 20px
Border-radius:  6px
Border:         none
Cursor:         pointer

Hover state:
  Color:        #D4AA00
  Background:   rgba(245,195,0,0.08)
```

### 7.4 Tab Data
```
Tab 1: "MENUNGGU"        ← ACTIVE
Tab 2: "DIKONFIRMASI"
Tab 3: "SELESAI"
Tab 4: "DITOLAK"
```

---

## 8. KOMPONEN: BOOKING TABLE PANEL

### 8.1 Container
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  12px
Overflow:       hidden
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
```

### 8.2 Table Header Row
```
Display:        grid
Grid-template-columns: 2.5fr 1.8fr 1.8fr 1.4fr
Background:     #1E1900
Padding:        12px 20px
Border-bottom:  1px solid #352E00

Column Header:
  Font-size:    11px
  Font-weight:  700
  Color:        #8A8070
  Letter-spacing:1.5px
  Text-transform:uppercase
```

### 8.3 Column Definitions
```
Col 1: MEMBER          — Flex 2.5 (avatar + nama + tier)
Col 2: PERSONAL TRAINER — Flex 1.8 (arrow icon + nama coach)
Col 3: JADWAL          — Flex 1.8 (tanggal + jam)
Col 4: STATUS          — Flex 1.4 (badge status)
```

### 8.4 Table Row (Data Row)
```
Display:        grid
Grid-template-columns: 2.5fr 1.8fr 1.8fr 1.4fr
Padding:        16px 20px
Border-bottom:  1px solid #352E00
Align-items:    center
Min-height:     72px

Last-child:     border-bottom: none

Hover state:
  Background:   #2E2800
  Cursor:       pointer
  Transition:   background 0.15s

Odd row:        background #252000
Even row:       background #1E1900 (subtle alternating)
```

---

## 9. KOMPONEN: TABLE ROW — MEMBER CELL

### 9.1 Member Cell Layout
```
Display:        flex, align-items center, gap 12px
```

### 9.2 Avatar
```
Width:          44px
Height:         44px
Border-radius:  50%
Background:     #3A3300
Object-fit:     cover
Flex-shrink:    0

(Setiap member punya illustrated avatar berbeda:
 Naufal: orange-toned, safety gear style
 Sarah: yellow/brown toned, casual
 Budi: grey/blue toned, sporty)
```

### 9.3 Text Stack
```
Name:
  Font-size:    16px
  Font-weight:  700
  Color:        #FFFFFF
  Line-height:  1.2

Tier Label:
  Font-size:    11px
  Font-weight:  500
  Color:        #8A8070
  Margin-top:   2px
```

### 9.4 Tier Color Coding (Opsional Enhancement)
```
Elite Tier:     color #F5C300 (kuning/premium)
VIP Tier:       color #A78BFA (ungu/eksklusif)
Standard Tier:  color #8A8070 (abu default)
```

---

## 10. KOMPONEN: TABLE ROW — PERSONAL TRAINER CELL

### 10.1 PT Cell Layout
```
Display:        flex, align-items center, gap 8px
```

### 10.2 Swap/Assign Icon
```
Container:
  Width:        24px
  Height:       24px
  Display:      flex center

Icon:           ↕ / swap-vertical arrows (double headed)
Icon-size:      16px
Color:          #F5C300
Cursor:         pointer

Tooltip on hover: "Ganti Personal Trainer"

Hover state:
  Opacity:      0.7
  Transform:    scale(1.1)
```

### 10.3 Coach Name
```
Font-size:      14px
Font-weight:    600
Color:          #FFFFFF
```

---

## 11. KOMPONEN: TABLE ROW — JADWAL CELL

### 11.1 Layout
```
Display:        flex, flex-direction column, gap 2px
```

### 11.2 Date
```
Font-size:      14px
Font-weight:    600
Color:          #FFFFFF
Font-family:    monospace (JetBrains Mono)
```

### 11.3 Time Range
```
Font-size:      13px
Font-weight:    400
Color:          #8A8070
Font-family:    monospace
```

---

## 12. KOMPONEN: TABLE ROW — STATUS CELL

### 12.1 Status Badge — MENUNGGU
```
Display:        inline-flex
Background:     #F5C300
Color:          #1A1500
Font-size:      11px
Font-weight:    700
Padding:        5px 10px
Border-radius:  4px
Letter-spacing: 1px
Text-transform: uppercase
Width:          fit-content
```

### 12.2 Status Badge — Variasi Lain (Reference)
```
DIKONFIRMASI:
  Background:   #3B82F6
  Color:        #FFFFFF

SELESAI:
  Background:   #4CAF50
  Color:        #FFFFFF

DITOLAK:
  Background:   #EF4444
  Color:        #FFFFFF
```

---

## 13. KOMPONEN: LIVE PROGRESS SECTION (PANEL KANAN)

### 13.1 Section Header
```
Display:        flex, align-items center, gap 8px
Margin-bottom:  16px

Title:
  Text:         "LIVE PROGRESS"
  Font-size:    16px
  Font-weight:  800
  Color:        #FFFFFF
  Letter-spacing:2px
  Text-transform:uppercase

Live Indicator Dot:
  Width:        8px
  Height:       8px
  Border-radius:50%
  Background:   #EF4444
  Box-shadow:   0 0 6px rgba(239,68,68,0.6)
  Animation:    pulse (scale 1 → 1.4 → 1, 1.2s ease-in-out infinite)
```

### 13.2 Live Progress Card Container
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  12px
Padding:        16px
Margin-bottom:  12px
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
```

### 13.3 Card Header Row
```
Display:        flex, align-items center, gap 12px
Margin-bottom:  14px

Avatar:
  Width:        44px
  Height:       44px
  Border-radius:50%
  Object-fit:   cover
  Background:   #3A3300

Text Stack:
  Name:
    Font-size:  15px
    Font-weight:700
    Color:      #FFFFFF

  Sub (coach):
    Font-size:  11px
    Font-weight:600
    Color:      #8A8070
    Letter-spacing:0.5px
    Text-transform:uppercase
    Margin-top: 2px

Ghost icon (kanan):
  Width:        32px
  Height:       32px
  Border-radius:50%
  Background:   rgba(255,255,255,0.04)
  Icon:         silhouette / ghost avatar shape
  Opacity:      0.3
  Margin-left:  auto
```

### 13.4 Progress Row
```
Display:        flex, align-items center, justify-content space-between
Margin-bottom:  8px

Label:
  Text:         "TRAINING PROGRESS"
  Font-size:    10px
  Font-weight:  700
  Color:        #8A8070
  Letter-spacing:1.5px
  Text-transform:uppercase

Percentage:
  Font-size:    20px
  Font-weight:  800
  Color:        #F5C300
```

### 13.5 Progress Bar
```
Height:         6px
Background:     #3A3300
Border-radius:  3px
Margin-bottom:  10px

Fill:
  Background:   #F5C300
  Border-radius:3px
  Width:        [percentage]%
  Transition:   width 0.5s ease
```

### 13.6 Session Meta Row
```
Display:        flex, justify-content space-between, align-items center

Left:
  Text:         "[FOCUS AREA]" e.g. "UPPER BODY STRENGTH"
  Font-size:    11px
  Font-weight:  600
  Color:        #8A8070
  Letter-spacing:1px
  Text-transform:uppercase

Right:
  Text:         "SESSION: #[number]" e.g. "SESSION: #12"
  Font-size:    11px
  Font-weight:  600
  Color:        #8A8070
  Letter-spacing:1px
  Text-transform:uppercase
```

### 13.7 Live Card Data
```
Card 1:
  Avatar:       Naufal Azhar (orange-tone illustrated)
  Name:         "Naufal Azhar"
  Sub:          "WITH COACH ADRIAN"
  Progress:     65%
  Focus:        "UPPER BODY STRENGTH"
  Session:      "SESSION: #12"

Card 2:
  Avatar:       Jessica Loh (warm-tone illustrated)
  Name:         "Jessica Loh"
  Sub:          "WITH COACH SARAH"
  Progress:     22%
  Focus:        "HIGH INTENSITY CARDIO"
  Session:      "SESSION: #04"
```

---

## 14. KOMPONEN: COACH INCENTIVE ACTIVE CARD

### 14.1 Container
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  16px
Padding:        16px
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
Display:        flex, align-items flex-start, gap 14px
```

### 14.2 Icon Container
```
Width:          40px
Height:         40px
Background:     #F5C300
Border-radius:  10px
Display:        flex center
Flex-shrink:    0

Icon:
  ⭐ star icon
  Width:        20px
  Color:        #1A1500
```

### 14.3 Content
```
Flex: 1

Title:
  Text:         "COACH INCENTIVE ACTIVE"
  Font-size:    13px
  Font-weight:  800
  Color:        #F5C300
  Letter-spacing:1px
  Text-transform:uppercase
  Margin-bottom:6px

Body Text:
  Font-size:    13px
  Font-weight:  400
  Color:        #8A8070
  Line-height:  1.5

  Bold Terms (inline):
    "Tier 2 Bonuses":    font-weight 700, color #FFFFFF
    "Coach Adrian":      font-weight 700, color #FFFFFF
    "3 more sessions":   font-weight 700, color #FFFFFF

Full text:
  "System automatically unlocks Tier 2 Bonuses once coach Adrian
  completes 3 more sessions today."
```

---

## 15. KOMPONEN: BACKGROUND WATERMARK

### 15.1 Spec
```
Content:        Faint large text (likely "BOOKING & SESSION" atau silhouette figures)
Position:       absolute, bottom: 0, left: 220px, right: 0
Font-size:      ~100px
Font-weight:    900
Color:          rgba(245,195,0,0.04)
Text-transform: uppercase
Z-index:        0
Pointer-events: none
User-select:    none
Overflow:       hidden
```

---

## 16. STATES & INTERACTIONS

### 16.1 Tab Switching
```
Click tab inactive:
  Active tab: background #F5C300, color #1A1500, box-shadow
  Previous tab: background transparent, color #8A8070
  Table content: fade-out (150ms) → filter data → fade-in (150ms)
  Transition: 200ms ease
```

### 16.2 Table Row Hover
```
Background: #252000 → #2E2800 (150ms)
Cursor: pointer
Optional: subtle right-arrow indicator muncul di kanan row
```

### 16.3 Table Row Click
```
Click buka detail drawer/modal sesi:
  Slide-in dari kanan (translateX(100%) → translateX(0), 280ms ease-out)
  Backdrop: rgba(0,0,0,0.5) fade-in 200ms
  Konten: detail booking, history, tombol konfirmasi/tolak
```

### 16.4 Swap PT Icon Click (↕)
```
Click ↕ icon di kolom Personal Trainer:
  Buka dropdown/modal daftar PT yang tersedia
  Setelah pilih PT baru → update row optimistically
  Toast notification: "Personal Trainer berhasil diubah ke Coach [Nama]"
```

### 16.5 Live Progress Real-Time Update
```
Progress bar:   animate fill setiap 30 detik (polling atau WebSocket push)
Persentase:     counter animation saat nilai berubah (ease-out 500ms)
Live dot:       pulse animation berlanjut selama ada sesi aktif
Jika sesi selesai: kartu fade-out dan hilang dari list
```

### 16.6 Search Sessions
```
Debounce:       300ms
Filter:         match pada nama member, nama coach, tanggal, atau status
Highlight:      matching text di-wrap dalam <mark> dengan background rgba(245,195,0,0.2)
No results:     tampilkan empty state illustration dengan teks "Tidak ada sesi ditemukan"
```

### 16.7 Incentive Card Interaction
```
Card ini read-only / informational
Hover: subtle border glow rgba(245,195,0,0.15)
Optional click: navigate ke /admin/reports/coach-incentive
```

---

## 17. DATA MODEL

### 17.1 Booking Session
```typescript
type BookingStatus = 'menunggu' | 'dikonfirmasi' | 'selesai' | 'ditolak';
type MemberTier = 'Elite Tier' | 'VIP Tier' | 'Standard Tier' | 'Basic Tier';

interface BookingSession {
  id: string;
  member: {
    id: string;
    name: string;             // "Naufal Azhar"
    tier: MemberTier;         // "Elite Tier"
    avatarUrl: string;
  };
  personalTrainer: {
    id: string;
    name: string;             // "Coach Adrian"
    avatarUrl: string;
  };
  jadwal: {
    date: string;             // "24 Okt 2023"
    timeStart: string;        // "08:00"
    timeEnd: string;          // "09:30"
    isoDateTime: Date;
  };
  status: BookingStatus;
  createdAt: Date;
  updatedAt: Date;
}
```

### 17.2 Live Progress Session
```typescript
interface LiveSession {
  id: string;
  memberId: string;
  memberName: string;         // "Naufal Azhar"
  memberAvatarUrl: string;
  coachName: string;          // "Coach Adrian"
  progressPercent: number;    // 65
  focusArea: string;          // "UPPER BODY STRENGTH"
  sessionNumber: number;      // 12
  startedAt: Date;
  estimatedEndAt: Date;
}
```

### 17.3 Coach Incentive
```typescript
interface CoachIncentive {
  coachId: string;
  coachName: string;            // "Coach Adrian"
  currentTier: number;          // 1
  nextTier: number;             // 2
  sessionsRemaining: number;    // 3
  tierBonusAmount: number;      // nominal bonus
  isActive: boolean;
  resetAt: Date;                // end of day
}
```

### 17.4 Tab Filter State
```typescript
interface TabFilterState {
  activeTab: BookingStatus;
  searchQuery: string;
  totalCounts: Record<BookingStatus, number>;
}
```

---

## 18. AKSESIBILITAS (A11Y)

```
1. Tab Filter:
   - role="tablist" aria-label="Filter status booking"
   - Tiap tab: role="tab", aria-selected="true/false"
   - Panel tabel: role="tabpanel", aria-labelledby="tab-menunggu"
   - Keyboard: Arrow keys untuk navigasi antar tab

2. Booking Table:
   - role="table" aria-label="Daftar booking sesi PT"
   - Header row: role="row" dengan <th scope="col"> untuk setiap kolom
   - Data row: role="row", aria-label="Booking [Nama Member] dengan [Coach] pada [Tanggal]"
   - Clickable row: tabIndex=0, role="button" untuk keyboard access

3. Swap PT Icon:
   - role="button"
   - aria-label="Ganti Personal Trainer untuk sesi Naufal Azhar"
   - tabIndex=0
   - onKeyDown: Enter/Space trigger action

4. Status Badge:
   - role="status" aria-label="Status: Menunggu"

5. Live Progress:
   - Section: role="region" aria-label="Live Progress Sesi Aktif"
   - Progress bar: role="progressbar" aria-valuenow="65" aria-valuemin="0" aria-valuemax="100"
   - aria-label="Training progress Naufal Azhar: 65%"
   - Live dot: aria-label="Live - sesi sedang berlangsung" aria-live="polite"

6. Search:
   - aria-label="Cari sesi booking"
   - aria-controls="booking-table"
   - Results count: aria-live="polite" mengumumkan jumlah hasil

7. Coach Incentive Card:
   - role="region" aria-label="Coach Incentive Info"
   - Bold terms: <strong> semantic HTML
```

---

## 19. CATATAN AI — IMPLEMENTATION NOTES (15 poin)

1. **Tab Filter + URL Sync**: Status tab aktif disimpan di URL query param `?status=menunggu`. Ini memungkinkan sharing link langsung ke tab tertentu, back-button browser berfungsi natural, dan server-side filtering yang efisien. Implementasikan dengan `useSearchParams()` (React Router) atau `router.query` (Next.js).

2. **Booking Table Pagination**: Meskipun screen hanya menampilkan 3 rows (data sample), implementasikan virtual scroll atau pagination untuk data produksi yang bisa ratusan entries. Gunakan `react-virtual` untuk virtual scrolling atau tambahkan "Load More" button di bawah tabel. Page size default: 20 rows.

3. **Swap PT (Reassign Trainer) Flow**: Klik ↕ icon → fetch `/api/trainers/available?date=2023-10-24&time=08:00` untuk PT yang available di slot tersebut → tampilkan dropdown list dengan nama + foto PT → pilih → konfirmasi dialog "Yakin ganti PT dari Coach Adrian ke Coach [Nama]?" → PATCH `/api/bookings/:id/reassign` → update row optimistically → rollback jika API error.

4. **Live Progress WebSocket**: Panel Live Progress menggunakan WebSocket connection ke endpoint `wss://api.editorialathletics.com/ws/live-sessions`. Server push event setiap ada perubahan progress (tiap 30 detik atau ketika PT update). Client subscribe ke topic `live-sessions:gym-id`. Implementasikan reconnect logic dengan exponential backoff.

5. **Live Progress Progress Bar Calculation**: Progress `%` dihitung dari kombinasi: (jumlah exercise selesai / total exercise planned) × 100. Atau alternatif: (waktu berlalu / durasi sesi total) × 100. Koordinasikan dengan tim backend untuk formula yang dipakai agar konsisten antara PT app dan admin dashboard.

6. **Coach Incentive Counter**: Angka "3 more sessions" adalah real-time countdown dari target harian coach. Ini harus update otomatis saat sesi baru selesai. Gunakan WebSocket yang sama dengan Live Progress untuk push update, atau polling setiap 5 menit via `/api/coaches/:id/incentive-status`.

7. **Status Badge Color System**: Buat centralized mapping object `STATUS_BADGE_CONFIG`:
   ```typescript
   const STATUS_BADGE_CONFIG = {
     menunggu:      { bg: '#F5C300', text: '#1A1500', label: 'MENUNGGU' },
     dikonfirmasi:  { bg: '#3B82F6', text: '#FFFFFF', label: 'DIKONFIRMASI' },
     selesai:       { bg: '#4CAF50', text: '#FFFFFF', label: 'SELESAI' },
     ditolak:       { bg: '#EF4444', text: '#FFFFFF', label: 'DITOLAK' },
   }
   ```
   Gunakan satu `<StatusBadge status={booking.status} />` component di seluruh app untuk konsistensi.

8. **Member Tier Visual Hierarchy**: Tier label di bawah nama member sebaiknya memiliki color coding untuk memudahkan admin scan visual: Elite Tier → #F5C300 (kuning), VIP Tier → #A78BFA (ungu), Standard Tier → #8A8070 (abu). Tambahkan juga icon kecil (crown, diamond, user) sebelum tier text untuk cue visual tambahan.

9. **Row Click → Booking Detail Drawer**: Klik row tabel membuka sliding drawer dari kanan (width: 480px). Konten drawer: header (nama member + status), section info booking (tanggal, waktu, PT, paket), section history sesi sebelumnya, section notes, dan action buttons (Konfirmasi / Tolak / Reschedule). Drawer menutup via backdrop click atau tombol × atau swipe-right (mobile).

10. **Search Scope & Performance**: Search "Search sessions..." mencari cross-field: nama member, nama PT, tanggal (format "24 okt"), dan status. Di client-side, gunakan Fuse.js dengan threshold 0.3 untuk fuzzy matching. Di server-side (untuk production data), kirim query ke `/api/bookings?search=naufal&status=menunggu`. Debounce 300ms sebelum API call.

11. **Empty State per Tab**: Tiap tab saat tidak ada data harus punya empty state yang informatif:
    - Menunggu: "Tidak ada booking menunggu konfirmasi"
    - Dikonfirmasi: "Tidak ada sesi yang dikonfirmasi hari ini"
    - Selesai: "Belum ada sesi yang selesai hari ini"
    - Ditolak: "Tidak ada booking yang ditolak"
    Tambahkan ilustrasi kecil dan CTA yang relevan per state.

12. **Jadwal Cell Date Format**: Tampilkan tanggal dalam format "24 Okt 2023" (bahasa Indonesia). Gunakan `Intl.DateTimeFormat('id-ID', { day: 'numeric', month: 'short', year: 'numeric' })` untuk formatting yang locale-aware. Untuk time range, format "08:00 - 09:30" menggunakan 24-hour clock.

13. **Live Progress Kartu Order**: Kartu live progress diurutkan berdasarkan `progressPercent` descending — member yang paling jauh progress-nya muncul pertama. Ini membantu admin monitor yang hampir selesai. Jika progress sama, urutkan berdasarkan `startedAt` ascending.

14. **Responsive Behavior**: Di tablet (≤ 1024px): kolom JADWAL dan STATUS collapse menjadi satu baris sub-info di bawah nama member (card-style rows). Panel Live Progress move ke bawah tabel (full width). Di mobile (≤ 640px): tabel berubah menjadi card list, Live Progress dan Incentive card ditampilkan sebagai collapsible accordion.

15. **Row Action Confirmation**: Jika admin memiliki aksi langsung dari row (misal: quick-konfirmasi via right-click context menu atau long-press mobile), tampilkan confirmation popover inline — bukan navigate ke halaman baru. Pattern ini mempercepat bulk-processing booking. Implementasikan `useContextMenu` hook dengan actions: Konfirmasi, Tolak, Reschedule, Lihat Detail.

---

*Spec ini generated dari analisis visual screen Admin_Booking___Session_PT.png*
*Design system reference: ADMIN_EQUIPMENT_MANAGEMENT_UI_SPEC.md + ADMIN_DASHBOARD_OVERVIEW_UI_SPEC.md + ADMIN_SYSTEM_SETTINGS_UI_SPEC.md*
*Total sections: 19 | Detail level: ⭐⭐⭐⭐⭐ Full Detail*

# ADMIN_EQUIPMENT_MANAGEMENT_UI_SPEC.md
# Egg Gym App — Admin Equipment Management Screen
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Admin > Equipment Management (Manajemen Aset)
# Resolution: 1286 × 1160 px
# Last Updated: 2026-06-27
# Source of truth: Admin Equipment Management.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Semua token warna digunakan konsisten di seluruh Admin screens.

| Token Name                | HEX Value         | Usage                                         |
|---------------------------|-------------------|-----------------------------------------------|
| --color-bg-primary        | #1A1500           | Main content background                       |
| --color-bg-card           | #252000           | Card & panel backgrounds                      |
| --color-bg-sidebar        | #141000           | Sidebar background                            |
| --color-bg-header         | #1A1500           | Top header bar background (transparan menyatu)|
| --color-bg-input          | #2A2400           | Search bar & input field background           |
| --color-accent-primary    | #F5C300           | Active filter, CTA buttons, active badges     |
| --color-accent-hover      | #E0B000           | Button hover state                            |
| --color-text-primary      | #FFFFFF           | Headings, card titles, primary content        |
| --color-text-secondary    | #8A8070           | Labels, captions, helper text                 |
| --color-text-muted        | #5A5040           | Disabled, placeholder                         |
| --color-text-on-accent    | #1A1500           | Text on yellow/accent elements                |
| --color-status-available  | #4CAF50           | "Tersedia" badge                              |
| --color-status-maintenance| #F5C300           | "Maintenance" badge                           |
| --color-status-danger     | #EF4444           | "Rusak" badge / notification dot              |
| --color-border-card       | #352E00           | Card borders                                  |
| --color-border-sidebar    | #2A2400           | Sidebar dividers                              |
| --color-badge-cardio      | #8A8070           | Category label "CARDIO" (teks, bukan pill)    |
| --color-badge-strength    | #8A8070           | Category label "STRENGTH"                     |
| --color-badge-freeweights | #8A8070           | Category label "FREE WEIGHTS"                 |
| --color-watermark         | rgba(255,255,255,0.03)| Watermark "EQUIPMENT" di belakang judul   |
| --color-alert-bg          | #F5C300           | Alert card (Audit Report) background          |
| --color-alert-text        | #1A1500           | Alert card text                               |
| --color-stat-accent       | #4CAF50           | Stat panel left border accent                 |
| --color-toast-bg          | #1A1500           | Toast "SISTEM AKTIF" background                |
| --color-overlay-image     | rgba(0,0,0,0.4)   | Card image gradient overlay                   |
| --color-overlay-dark      | rgba(0,0,0,0.7)   | Modal backdrop / ID badge bg                  |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Monospace:  "JetBrains Mono", "Fira Code", monospace  (untuk ID/kode alat)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-sidebar-brand     | 20px | 800    | 1.1    | 0px              | "Editorial Athletics" brand        |
| --text-sidebar-sub       | 10px | 600    | 1.2    | 2px (uppercase)  | "ELITE MANAGEMENT" sub-brand       |
| --text-breadcrumb        | 14px | 800    | 1.0    | 1px (uppercase)  | "ALAT GYM" header breadcrumb       |
| --text-page-label        | 11px | 700    | 1.2    | 3px (uppercase)  | "ELITE INVENTORY" supra-title      |
| --text-page-title        | 34px | 800    | 1.1    | -0.5px           | "Manajemen Aset" H1                |
| --text-watermark         | 96px | 800    | 1.0    | 0px              | Watermark "EQUIPMENT" di belakang  |
| --text-section-title     | 20px | 800    | 1.3    | 0px              | "Ringkasan Status Alat" heading    |
| --text-card-category     | 10px | 700    | 1.2    | 1.5px (uppercase)| Label kategori di card body        |
| --text-card-title        | 18px | 800    | 1.3    | 0px              | Nama alat di equipment card        |
| --text-card-body         | 13px | 400    | 1.5    | 0px              | Deskripsi alat                     |
| --text-filter-tab        | 11px | 700    | 1.0    | 1px (uppercase)  | Label filter tab                   |
| --text-badge             | 10px | 700    | 1.0    | 0.5px (uppercase)| Status badges                      |
| --text-stat-number       | 34px | 800    | 1.0    | 0px              | Angka di ringkasan status          |
| --text-stat-label        | 10px | 600    | 1.3    | 1px (uppercase)  | Label di bawah angka statistik     |
| --text-button-cta        | 13px | 700    | 1.0    | 0px              | "+ Tambah Alat" button             |
| --text-button-detail     | 11px | 700    | 1.0    | 1px (uppercase)  | "DETAIL >" di card footer          |
| --text-alert-label       | 10px | 700    | 1.2    | 2px              | "AUDIT REPORT" label               |
| --text-alert-body        | 20px | 800    | 1.3    | 0px              | Pesan alert                        |
| --text-alert-cta         | 11px | 700    | 1.0    | 1px              | "BUKA LAPORAN" button              |
| --text-nav-item          | 13px | 600    | 1.4    | 0.5px (uppercase)| Sidebar navigation items           |
| --text-search            | 13px | 400    | 1.0    | 0px              | Search bar input                   |
| --text-id-badge          | 10px | 600    | 1.0    | 0.5px            | Equipment ID overlay (EQ-001 dll)  |
| --text-toast-title       | 11px | 700    | 1.0    | 1px (uppercase)  | "SISTEM AKTIF" toast title         |
| --text-toast-body        | 11px | 400    | 1.3    | 0px              | Toast body text                    |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Badge padding, tiny gaps                        |
| --space-sm     | 8px   | Card footer icon gaps, list item inner gaps     |
| --space-md     | 12px  | Card body padding, filter gap                   |
| --space-base   | 16px  | Standard component margin                       |
| --space-lg     | 20px  | Main grid gap, section spacing                  |
| --space-xl     | 24px  | Card-to-card gap, page padding                  |
| --space-2xl    | 32px  | Major section separation                        |
| --space-3xl    | 48px  | Page top padding                                |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-xs    | 4px   | Status badges, ID badges                        |
| --radius-sm    | 6px   | Input fields, small icon buttons                |
| --radius-md    | 10px  | Equipment cards, panels                         |
| --radius-lg    | 14px  | Large panels, toast notification                |
| --radius-pill  | 999px | Filter tabs (fully rounded), status badge pill  |
| --radius-full  | 50%   | Avatar circles, dot indicators                  |

### Box Shadows
| Token            | Value                              | Usage                        |
|------------------|------------------------------------|------------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)         | Equipment cards default      |
| --shadow-hover   | 0 8px 20px rgba(0,0,0,0.6)        | Cards on hover               |
| --shadow-button  | 0 2px 8px rgba(245,195,0,0.35)    | Primary CTA buttons          |
| --shadow-toast   | 0 8px 24px rgba(0,0,0,0.6)        | Toast notification           |
| --shadow-modal   | 0 8px 32px rgba(0,0,0,0.7)        | Modal overlays               |

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Total Canvas:   1286 × 1160 px
Sidebar:        240px wide × 100vh (fixed)
Header Bar:     calc(100vw - 240px) × 64px (sticky)
Main Content:   calc(100vw - 240px) width, padding: 24px 32px
Page Padding:   24px (vertikal) / 32px (horizontal)
Content Gap:    24px
Toast (float):  fixed, bottom-right
```

### ASCII Layout Diagram
```
┌─────────────────────┬────────────────────────────────────────────────────────┐
│  SIDEBAR (240px)    │  HEADER BAR (64px)                                     │
│  ───────────────    │  ALAT GYM   [🔍 Cari nama atau kode alat...]  🔔 ❓ 👤 │
│  Editorial          ├────────────────────────────────────────────────────────┤
│  Athletics          │   ELITE INVENTORY            (watermark "EQUIPMENT")   │
│  ELITE MANAGEMENT   │   Manajemen Aset                      [+ Tambah Alat]  │
│  ───────────────    │                                                        │
│  ⊞ DASHBOARD        │  [SEMUA ALAT] [CARDIO] [STRENGTH] [FREE WGT] [FUNC]   │
│  👥 MEMBER          │                                                        │
│  💳 PAKET MEMBERSHIP│  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐  │
│  ⭐ PERSONAL TRAINER│  │ EQ-001       │ │ EQ-012       │ │ EQ-005       │  │
│  ☑ BOOKING & SESI PT│  │ [treadmill]  │ │ [dumbbells]  │ │ [leg press]  │  │
│  💠 ALAT GYM ◄AKTIF │  │ 🟢 TERSEDIA  │ │ 🟢 TERSEDIA  │ │ 🟡 MAINTENANCE│ │
│  🗂 AUDIT TRAIL     │  │ CARDIO       │ │ FREE WEIGHTS │ │ STRENGTH     │  │
│  📊 LAPORAN         │  │ Treadmill    │ │ Chrome       │ │ Leg Press    │  │
│  ⚙ PENGATURAN       │  │ Pro X        │ │ Dumbbells    │ │ Elite        │  │
│  ───────────────    │  │ desc...      │ │ desc...      │ │ desc...      │  │
│  [👤] Admin Elite   │  │ ✏️ 🗑️  DETAIL>│ │ ✏️ 🗑️ DETAIL>│ │ ✏️ 🗑️ DETAIL>│  │
│  SUPER ADMIN        │  └──────────────┘ └──────────────┘ └──────────────┘  │
│                     │  ┌────────────────────────────────┐ ┌───────────────┐ │
│                     │  │ Ringkasan Status Alat          │ │ AUDIT REPORT  │ │
│                     │  │ PEMBARUAN TERAKHIR: 10 MNT LALU│ │ Butuh inspeksi│ │
│                     │  │ 124    118    4      2         │ │ rutin untuk 12│ │
│                     │  │ TOTAL  BEROP  SERVIS  RUSAK    │ │ alat minggu   │ │
│                     │  └────────────────────────────────┘ │ ini.          │ │
│                     │                  ┌──────────────────┐│ [BUKA LAPORAN]│ │
│                     │                  │⚡ SISTEM AKTIF    │└───────────────┘ │
│                     │                  │ Database sinkron…│                  │
│                     │                  └──────────────────┘                  │
└─────────────────────┴────────────────────────────────────────────────────────┘
```

---

## 5. KOMPONEN: SIDEBAR

### 5.1 Container Sidebar
```
Width:          240px
Height:         100vh
Background:     #141000
Border-right:   1px solid #2A2400
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
  Color:        #F5C300
Sub-brand:
  Text:         "ELITE MANAGEMENT"
  Font-size:    10px
  Font-weight:  600
  Color:        #8A8070
  Letter-spacing:2px
  Text-transform:uppercase
  Margin-top:   4px
```

### 5.3 Menu Item (Default State)
```
Display:        flex, align-items center
Padding:        12px 24px
Gap:            12px
Icon-color:     #8A8070
Text:
  Font-size:    13px
  Font-weight:  600
  Color:        #8A8070
  Letter-spacing:0.5px
  Text-transform:uppercase
Hover:
  Color:        #FFFFFF
  Icon-color:   #F5C300
```

### 5.4 Menu Item (Active State — ALAT GYM)
```
Icon-color:     #F5C300
Text-color:     #F5C300
Font-weight:    700
Indicator:      garis vertikal kuning #F5C300 (2px) di sisi kanan item aktif
```

### 5.5 Daftar Navigation Items (Urutan FINAL — sesuai gambar)
```
1.  ⊞  DASHBOARD
2.  👥  MEMBER
3.  💳  PAKET MEMBERSHIP
4.  ⭐  PERSONAL TRAINER
5.  ☑  BOOKING & SESI PT
6.  💠  ALAT GYM            ← ACTIVE (screen ini)
7.  🗂  AUDIT TRAIL
8.  📊  LAPORAN
9.  ⚙  PENGATURAN
```

### 5.6 Profile Area (Bottom)
```
Position:       margin-top auto
Padding:        16px 24px
Border-top:     1px solid #2A2400
Display:        flex, align-items center, gap 12px

Avatar:
  Width/Height: 40px
  Border-radius:50%
  Content:      foto profil (real photo)

Name:
  Text:         "Admin Elite"
  Font-size:    14px
  Font-weight:  700
  Color:        #FFFFFF
Role:
  Text:         "SUPER ADMIN"
  Font-size:    10px
  Font-weight:  600
  Color:        #8A8070
  Letter-spacing:1px
```

---

## 6. KOMPONEN: TOP HEADER BAR

### 6.1 Container
```
Height:         64px
Background:     transparan (menyatu dengan #1A1500)
Padding:        0 32px
Display:        flex, align-items center, justify-content space-between
Position:       sticky, top 0
Z-index:        100
Width:          calc(100vw - 240px)
```

### 6.2 Kiri — Breadcrumb
```
Text:           "ALAT GYM"
Font-size:      14px
Font-weight:    800
Color:          #F5C300
Letter-spacing: 1px
Text-transform: uppercase
```

### 6.3 Tengah — Search Bar
```
Container:
  Width:        ~400px
  Height:       40px
  Background:   #2A2400
  Border:       1px solid #352E00
  Border-radius:8px
  Padding:      0 14px
  Gap:          10px
Search Icon:
  Color:        #5A5040
Input:
  Placeholder:  "Cari nama atau kode alat..."
  Placeholder-color: #5A5040
  Color:        #FFFFFF
  Font-size:    13px
Focus:
  Border:       1px solid #F5C300
```

### 6.4 Kanan — Action Icons
```
Display:        flex, align-items center, gap 20px

Notification Bell:
  Icon-size:    20px
  Color:        #FFFFFF
  Badge dot:    6px, bg #EF4444 (top-right)

Help Icon (?):       ← bukan settings gear
  Icon-size:    20px
  Shape:        lingkaran outline dengan tanda tanya
  Color:        #FFFFFF

Profile Avatar:
  Width/Height: 32px
  Border-radius:50%
  Content:      foto profil (real photo)
  Cursor:       pointer
```

---

## 7. KOMPONEN: PAGE HEADER SECTION

### 7.1 Watermark (di belakang judul)
```
Text:           "EQUIPMENT"
Font-size:      96px
Font-weight:    800
Color:          rgba(255,255,255,0.03)
Text-transform: uppercase
Position:       absolute, di belakang supra-label & H1
Z-index:        0
Pointer-events: none
```

### 7.2 Kiri — Judul
```
Supra-label:
  Text:         "ELITE INVENTORY"
  Font-size:    11px
  Font-weight:  700
  Color:        #F5C300
  Letter-spacing:3px
  Text-transform:uppercase
  Margin-bottom:8px

Main Title (H1):
  Text:         "Manajemen Aset"
  Font-size:    34px
  Font-weight:  800
  Color:        #FFFFFF
  Letter-spacing:-0.5px
  Z-index:      1 (di atas watermark)
```

### 7.3 Kanan — Tombol "+ Tambah Alat"
```
Text:           "+ Tambah Alat"
Font-size:      13px
Font-weight:    700
Color:          #1A1500
Background:     #F5C300
Border-radius:  8px
Padding:        12px 22px
Box-shadow:     0 2px 8px rgba(245,195,0,0.35)
Display:        flex, align-items center, gap 8px
Hover:
  Background:   #E0B000
  Transform:    translateY(-1px)
```

---

## 8. KOMPONEN: FILTER TAB BAR

### 8.1 Container
```
Display:        flex, gap 12px
Margin:         24px 0
```

### 8.2 Tab Default
```
Padding:        9px 20px
Background:     #252000
Border:         1px solid #352E00
Border-radius:  999px   (pill penuh)
Font-size:      11px
Font-weight:    700
Color:          #8A8070
Letter-spacing: 1px
Text-transform: uppercase
Hover:
  Color:        #FFFFFF
  Border-color: #5A4800
```

### 8.3 Tab Active (SEMUA ALAT)
```
Background:     #F5C300
Border:         1px solid #F5C300
Color:          #1A1500
Font-weight:    700
```

### 8.4 Daftar Filter Tabs (5 opsi)
```
Tab 1: "SEMUA ALAT"   ← Active (kuning)
Tab 2: "CARDIO"
Tab 3: "STRENGTH"
Tab 4: "FREE WEIGHTS"
Tab 5: "FUNCTIONAL"
```

---

## 9. KOMPONEN: EQUIPMENT CARDS GRID

### 9.1 Grid Container
```
Display:              grid
Grid-template-columns:repeat(3, 1fr)
Gap:                  24px

Breakpoints:
  < 1024px:    repeat(2, 1fr)
  < 640px:     repeat(1, 1fr)
```

### 9.2 Card Container
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  10px
Overflow:       hidden
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
Display:        flex, flex-direction column
Hover:
  Transform:    translateY(-4px)
  Box-shadow:   0 8px 20px rgba(0,0,0,0.6)
  Border-color: rgba(245,195,0,0.4)
```

### 9.3 Card — Image Area
```
Height:         ~210px
Position:       relative
Overflow:       hidden
Image:
  Width/Height: 100%
  Object-fit:   cover
  Loading:      lazy
Gradient Overlay:
  Background:   linear-gradient(to bottom, transparent 55%, rgba(0,0,0,0.4) 100%)
```

### 9.4 Card — ID Badge Overlay (Top-Left)
```
Position:       absolute, top 12px, left 12px
Background:     rgba(0,0,0,0.7)
Color:          #FFFFFF
Font-size:      10px
Font-weight:    600
Font-family:    monospace
Padding:        3px 9px
Border-radius:  4px
Letter-spacing: 0.5px
```

### 9.5 Card — Status Badge Overlay (Bottom-Left Image)
```
Position:       absolute, bottom 12px, left 12px
Font-size:      10px
Font-weight:    700
Letter-spacing: 0.5px
Text-transform: uppercase
Padding:        4px 12px
Border-radius:  999px (pill)
Display:        flex, align-items center, gap 6px (dengan dot)

Status → Style:
  TERSEDIA:     bg rgba(76,175,80,0.15), border #4CAF50, text #4CAF50, dot #4CAF50
  MAINTENANCE:  bg rgba(245,195,0,0.15), border #F5C300, text #F5C300, dot #F5C300
  RUSAK:        bg rgba(239,68,68,0.15), border #EF4444, text #EF4444, dot #EF4444
```

### 9.6 Card — Body Content
```
Padding:        16px 18px

Category Label:
  Font-size:    10px
  Font-weight:  700
  Color:        #8A8070
  Letter-spacing:1.5px
  Text-transform:uppercase
  Margin-bottom:6px

Equipment Name:
  Font-size:    18px
  Font-weight:  800
  Color:        #FFFFFF
  Margin-bottom:8px

Description:
  Font-size:    13px
  Font-weight:  400
  Color:        #8A8070
  Line-height:  1.5
  -webkit-line-clamp: 3
```

### 9.7 Card — Footer Actions
```
Padding:        12px 18px 16px
Border-top:     1px solid #2A2400
Display:        flex, justify-content space-between, align-items center

Kiri — Icon Actions (gap 8px):
  Edit Icon (pensil):
    Size:       36px × 36px
    Background: #2A2400
    Border-radius:6px
    Color:      #8A8070
    Hover:      color #F5C300
  Delete Icon (tempat sampah):
    Size:       36px × 36px
    Background: #2A2400
    Border-radius:6px
    Color:      #8A8070
    Hover:      color #EF4444

Kanan — Detail Button:
  Text:         "DETAIL >"
  Font-size:    11px
  Font-weight:  700
  Color:        #F5C300
  Letter-spacing:1px
  Text-transform:uppercase
  Hover:        color #E0B000, underline
```

### 9.8 Data Contoh — Equipment Cards (FINAL — sesuai gambar)
```
CARD 1 — Treadmill Pro X
  ID badge:         "EQ-001"
  Status badge:     "TERSEDIA"      → hijau #4CAF50
  Category label:   "CARDIO"
  Name:             "Treadmill Pro X"
  Description:      "Premium endurance machine with integrated performance
                     tracking and ergonomic shock absorption."

CARD 2 — Chrome Dumbbells
  ID badge:         "EQ-012"
  Status badge:     "TERSEDIA"      → hijau #4CAF50
  Category label:   "FREE WEIGHTS"
  Name:             "Chrome Dumbbells"
  Description:      "Professional grade chrome finish hand weights for elite
                     strength conditioning and hypertrophy."

CARD 3 — Leg Press Elite
  ID badge:         "EQ-005"
  Status badge:     "MAINTENANCE"   → kuning #F5C300
  Category label:   "STRENGTH"
  Name:             "Leg Press Elite"
  Description:      "Engineered for maximum stability and linear path movement
                     for isolated lower body development."
```

---

## 10. KOMPONEN: RINGKASAN STATUS ALAT

### 10.1 Container
```
Background:     #252000
Border:         1px solid #352E00
Border-left:    4px solid #F5C300   (accent bar kiri)
Border-radius:  10px
Padding:        24px 28px
Flex:           3
```

### 10.2 Header Row
```
Display:        flex, justify-content space-between, align-items center
Margin-bottom:  20px

Judul:
  Text:         "Ringkasan Status Alat"
  Font-size:    20px
  Font-weight:  800
  Color:        #FFFFFF

Sub-label kanan:
  Text:         "PEMBARUAN TERAKHIR: 10 MENIT LALU"
  Font-size:    10px
  Font-weight:  600
  Color:        #8A8070
  Letter-spacing:1px
  Text-transform:uppercase
```

### 10.3 Stats Row (4 angka)
```
Display:        flex, gap 48px

Stat Item:
  Angka:
    Font-size:  34px
    Font-weight:800
  Label:
    Font-size:  10px
    Font-weight:600
    Color:      #8A8070
    Letter-spacing:1px
    Text-transform:uppercase

Nilai:
  "124" → color #F5C300   label: "TOTAL ASET"
  "118" → color #4CAF50   label: "BEROPERASI"
  "4"   → color #F5C300   label: "DALAM SERVIS"
  "2"   → color #EF4444   label: "RUSAK"
```

---

## 11. KOMPONEN: ALERT CARD — AUDIT REPORT

### 11.1 Container
```
Background:     #F5C300
Border-radius:  10px
Padding:        24px
Display:        flex, flex-direction column, justify-content space-between
Flex:           2
Max-width:      300px
```

### 11.2 Label
```
Text:           "AUDIT REPORT"
Font-size:      10px
Font-weight:    700
Color:          rgba(26,21,0,0.6)
Letter-spacing: 2px
Text-transform: uppercase
Margin-bottom:  12px
```

### 11.3 Pesan Alert
```
Text:           "Butuh inspeksi rutin untuk 12 alat minggu ini."
Font-size:      20px
Font-weight:    800
Color:          #1A1500
Line-height:    1.3
```

### 11.4 Tombol CTA
```
Text:           "BUKA LAPORAN"
Font-size:      11px
Font-weight:    700
Color:          #1A1500
Background:     rgba(0,0,0,0.12)
Border-radius:  6px
Padding:        8px 16px
Align-self:     flex-start
Margin-top:     16px
Text-transform: uppercase
Letter-spacing: 1px
Hover:
  Background:   rgba(0,0,0,0.2)
```

---

## 12. KOMPONEN: BOTTOM SECTION LAYOUT

### 12.1 Container Wrapper
```
Display:        flex, gap 24px, align-items stretch
Margin-top:     32px
```

### 12.2 Distribusi Lebar
```
Ringkasan Status Alat (panel kiri):   flex 3
Alert Card Audit Report (panel kanan): flex 2, max-width 300px
```

---

## 13. KOMPONEN: TOAST NOTIFICATION (Floating Bottom-Right)

### 13.1 Container
```
Position:       fixed, bottom 24px, right 24px
Background:     #1A1500
Border:         1px solid #352E00
Border-radius:  14px
Padding:        14px 18px
Box-shadow:     0 8px 24px rgba(0,0,0,0.6)
Display:        flex, align-items center, gap 12px
Max-width:      ~380px
Z-index:        300
```

### 13.2 Icon (Kiri)
```
Shape:          lingkaran 32px
Background:     #F5C300
Icon:           ⚡ (petir), color #1A1500
Border-radius:  50%
```

### 13.3 Konten (Kanan)
```
Title:
  Text:         "SISTEM AKTIF"
  Font-size:    11px
  Font-weight:  700
  Color:        #FFFFFF
  Letter-spacing:1px
  Text-transform:uppercase

Body:
  Text:         "Database sinkron dengan 14 cabang Editorial Athletics."
  Font-size:    11px
  Font-weight:  400
  Color:        #8A8070
```

---

## 14. GRID RECAP — RINGKASAN ZONA LAYOUT

| Zone                  | X Offset | Y Offset  | Width                   | Height    |
|-----------------------|----------|-----------|-------------------------|-----------|
| Sidebar               | 0        | 0         | 240px                   | 100vh     |
| Header Bar            | 240px    | 0         | calc(100vw - 240px)     | 64px      |
| Page Header           | 272px    | 88px      | calc(100vw - 304px)     | ~110px    |
| Filter Tab Bar        | 272px    | 200px     | calc(100vw - 304px)     | ~42px     |
| Equipment Grid (3-col)| 272px    | 266px     | calc(100vw - 304px)     | ~450px    |
| Bottom Section Row    | 272px    | 800px     | calc(100vw - 304px)     | ~190px    |
| Toast (floating)      | auto     | auto      | ~380px                  | ~64px     |

---

## 15. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Admin Equipment Management (Manajemen Aset)
   CSS Custom Properties — Design Tokens
   Visual-verified: Admin Equipment Management.png
   Generated: 2026-06-27
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:          #1A1500;
  --color-bg-card:             #252000;
  --color-bg-sidebar:          #141000;
  --color-bg-input:            #2A2400;
  --color-accent-primary:      #F5C300;
  --color-accent-hover:        #E0B000;
  --color-text-primary:        #FFFFFF;
  --color-text-secondary:      #8A8070;
  --color-text-muted:          #5A5040;
  --color-text-on-accent:      #1A1500;
  --color-status-available:    #4CAF50;
  --color-status-maintenance:  #F5C300;
  --color-status-danger:       #EF4444;
  --color-border-card:         #352E00;
  --color-border-sidebar:      #2A2400;
  --color-watermark:           rgba(255,255,255,0.03);
  --color-alert-bg:            #F5C300;
  --color-alert-text:          #1A1500;
  --color-toast-bg:            #1A1500;
  --color-overlay-image:       rgba(0,0,0,0.4);
  --color-overlay-dark:        rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:       "Inter", "Segoe UI", -apple-system, sans-serif;
  --font-family-mono:          "JetBrains Mono", "Fira Code", monospace;
  --text-sidebar-brand:        20px;
  --text-breadcrumb:           14px;
  --text-page-label:           11px;
  --text-page-title:           34px;
  --text-watermark:            96px;
  --text-section-title:        20px;
  --text-card-title:           18px;
  --text-card-body:            13px;
  --text-filter-tab:           11px;
  --text-badge:                10px;
  --text-stat-number:          34px;
  --text-stat-label:           10px;
  --text-button-cta:           13px;
  --text-alert-body:           20px;
  --text-nav-item:             13px;

  /* ── SPACING ── */
  --space-xs:                  4px;
  --space-sm:                  8px;
  --space-md:                  12px;
  --space-base:                16px;
  --space-lg:                  20px;
  --space-xl:                  24px;
  --space-2xl:                 32px;
  --space-3xl:                 48px;

  /* ── BORDER RADIUS ── */
  --radius-xs:                 4px;
  --radius-sm:                 6px;
  --radius-md:                 10px;
  --radius-lg:                 14px;
  --radius-pill:               999px;
  --radius-full:               50%;

  /* ── SHADOWS ── */
  --shadow-card:               0 2px 8px rgba(0,0,0,0.4);
  --shadow-hover:              0 8px 20px rgba(0,0,0,0.6);
  --shadow-button:             0 2px 8px rgba(245,195,0,0.35);
  --shadow-toast:              0 8px 24px rgba(0,0,0,0.6);
  --shadow-modal:              0 8px 32px rgba(0,0,0,0.7);

  /* ── LAYOUT ── */
  --sidebar-width:             240px;
  --header-height:             64px;
  --card-grid-cols:            3;
  --card-gap:                  24px;
  --page-padding-x:            32px;
  --page-padding-y:            24px;
  --filter-tab-height:         42px;
  --card-image-height:         210px;
  --bottom-section-gap:        24px;
}
```

---

## 16. CATATAN AI — IMPLEMENTATION NOTES (12 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Admin Equipment Management.png`. Semua kode alat (EQ-001, EQ-012, EQ-005), label status (TERSEDIA, MAINTENANCE), dan teks (pesan toast, placeholder search) harus persis sama dengan gambar.

2. **Card Grid Responsive**: `grid-template-columns: repeat(auto-fill, minmax(300px, 1fr))`. Fallback 2 kolom (≤1024px), 1 kolom (≤640px).

3. **Image Loading**: Gunakan `loading="lazy"` + `object-fit: cover`. Tinggi image area ~210px untuk menjaga rasio editorial.

4. **Status Badge = Pill Outline**: Badge status di gambar memakai gaya pill (border-radius penuh) dengan dot indikator di kiri, bukan solid block. Map:
   - `TERSEDIA` → border+text+dot `#4CAF50`, bg transparan 15%
   - `MAINTENANCE` → border+text+dot `#F5C300`, bg transparan 15%
   - `RUSAK` → border+text+dot `#EF4444`, bg transparan 15%

5. **ID Badge Posisi Top-Left**: Berbeda dari layout lama — ID badge (EQ-xxx) ada di **kiri-atas** image, status badge di **kiri-bawah** image. Tidak ada category badge overlay di image; kategori ditampilkan sebagai label teks di card body.

6. **Filter Tab Pill**: Semua filter tab fully-rounded (`border-radius: 999px`). Tab aktif "SEMUA ALAT" solid kuning `#F5C300`.

7. **Watermark "EQUIPMENT"​**: Render teks raksasa semi-transparan (`rgba(255,255,255,0.03)`) di belakang supra-label & H1 sebagai elemen dekoratif. Gunakan `z-index: 0` dan `pointer-events: none`.

8. **Header Icons**: Urutan kanan = Notification Bell (dengan dot merah) → **Help icon "?"​** (bukan settings gear) → Profile Avatar (foto asli, bukan inisial huruf).

9. **Sidebar Menu Final**: 9 item dengan label uppercase: DASHBOARD, MEMBER, PAKET MEMBERSHIP, PERSONAL TRAINER, BOOKING & SESI PT, ALAT GYM (aktif), AUDIT TRAIL, LAPORAN, PENGATURAN. Indikator aktif = garis kuning vertikal di sisi kanan item.

10. **Toast Floating**: Notifikasi "SISTEM AKTIF" adalah toast melayang di kanan-bawah (bukan AI bar full-width). Background gelap `#1A1500`, ikon petir kuning bulat, body text: "Database sinkron dengan 14 cabang Editorial Athletics."

11. **Stat Panel Accent**: Panel "Ringkasan Status Alat" punya border-left kuning 4px. Label sub-header: "PEMBARUAN TERAKHIR: 10 MENIT LALU". Stats: 124 TOTAL ASET, 118 BEROPERASI, 4 DALAM SERVIS, 2 RUSAK.

12. **Edit/Delete Accessibility**: Icon button (36×36px) wajib punya `aria-label="Edit [nama_alat]"` / `aria-label="Hapus [nama_alat]"` dan `title` untuk tooltip native.

---

*Spec ini generated dari analisis visual screen Admin Equipment Management.png (visual-verified).*
*Total sections: 16 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

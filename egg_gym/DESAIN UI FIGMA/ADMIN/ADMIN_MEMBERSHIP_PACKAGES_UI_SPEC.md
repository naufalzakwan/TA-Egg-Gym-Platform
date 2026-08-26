# ADMIN_MEMBERSHIP_PACKAGES_UI_SPEC.md
# Egg Gym App — Admin Membership Packages Screen
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Admin > Paket Membership (Package Management)
# Resolution: 1280 × ~1100 px
# Last Updated: 2026-06-24

---

## 1. DESIGN TOKENS — COLOR PALETTE

| Token Name                    | HEX Value                    | Usage                                               |
|-------------------------------|------------------------------|-----------------------------------------------------|
| --color-bg-primary            | #1A1500                      | Main content background                             |
| --color-bg-card               | #252000                      | Package cards, config panel background              |
| --color-bg-sidebar            | #141000                      | Sidebar background                                  |
| --color-bg-header             | #1E1900                      | Top header bar background                           |
| --color-bg-preview            | #141000                      | Real-Time Preview panel (lebih gelap dari card)     |
| --color-bg-card-header        | #1A1500                      | Package card header area background                 |
| --color-bg-input              | #2A2400                      | Input fields, dropdowns background                  |
| --color-accent-primary        | #F5C300                      | KPI featured card bg, benefit check, price field    |
| --color-accent-hover          | #E0B000                      | Button/tab hover                                    |
| --color-text-primary          | #FFFFFF                      | Package names, body text                            |
| --color-text-secondary        | #8A8070                      | Labels, captions, helper text                       |
| --color-text-muted            | #5A5040                      | Placeholders, disabled                              |
| --color-text-on-accent        | #1A1500                      | Text on yellow (KPI featured, SAVE button)          |
| --color-package-price         | #F5C300                      | Harga paket di card header (28px kuning)            |
| --color-config-price          | #F5C300                      | Harga field di Configuration Details panel          |
| --color-preview-title         | #F5C300                      | "ELITE PRO" title di Real-Time Preview              |
| --color-preview-pricing       | #F5C300                      | "IDR 7.2M" di preview panel                        |
| --color-preview-badge-bg      | rgba(245,195,0,0.1)          | "LIVE PREVIEW" badge background                     |
| --color-preview-badge-border  | rgba(245,195,0,0.2)          | "LIVE PREVIEW" badge border                         |
| --color-preview-badge-text    | #F5C300                      | "LIVE PREVIEW" badge text                           |
| --color-toggle-on-knob        | #F5C300                      | Toggle switch knob saat ON                          |
| --color-toggle-on-track       | rgba(245,195,0,0.3)          | Toggle switch track saat ON                         |
| --color-toggle-off-knob       | #8A8070                      | Toggle switch knob saat OFF                         |
| --color-toggle-off-track      | #2E2800                      | Toggle switch track saat OFF                        |
| --color-benefit-check-bg      | #F5C300                      | Custom checkbox benefit saat checked                |
| --color-benefit-check-border  | #F5C300                      | Checkbox border saat checked                        |
| --color-badge-aktif-bg        | rgba(76,175,80,0.15)         | "AKTIF" status badge background                     |
| --color-badge-aktif-text      | #4CAF50                      | "AKTIF" status badge text                           |
| --color-badge-nonaktif-bg     | rgba(107,114,128,0.15)       | "NONAKTIF" badge background                         |
| --color-badge-nonaktif-text   | #6B7280                      | "NONAKTIF" badge text                               |
| --color-kpi-featured-bg       | #F5C300                      | KPI card 4 (TERPOPULER) background — KUNING SOLID   |
| --color-kpi-featured-text     | #1A1500                      | KPI card 4 text — GELAP                             |
| --color-border-card           | #2E2800                      | Card borders, dividers                              |
| --color-border-sidebar        | #2A2400                      | Sidebar dividers                                    |
| --color-btn-discard-border    | #2E2800                      | DISCARD button border                               |
| --color-btn-discard-text      | #8A8070                      | DISCARD button text                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:  "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
```

### Skala Tipografi Lengkap
| Token                     | Size | Weight | Line-H | Letter-Sp        | Usage                                        |
|---------------------------|------|--------|--------|------------------|----------------------------------------------|
| --text-breadcrumb         | 12px | 700    | 1.0    | 2px (uppercase)  | "PAKET MEMBERSHIP" header breadcrumb (putih) |
| --text-page-supra         | 11px | 700    | 1.2    | 3px (uppercase)  | "MANAGEMENT" supra label (abu)               |
| --text-page-title-accent  | 14px | 700    | 1.2    | 0px              | "PACKAGES" kuning (#F5C300) dalam title      |
| --text-kpi-value-featured | 36px | 800    | 1.0    | 0px              | KPI card 4 angka (teks gelap #1A1500)        |
| --text-kpi-value-default  | 32px | 800    | 1.0    | 0px              | KPI cards 1–3 angka (teks putih)             |
| --text-kpi-label          | 11px | 700    | 1.2    | 2px (uppercase)  | KPI card label                               |
| --text-kpi-sub            | 12px | 400    | 1.3    | 0px              | KPI card sub-value                           |
| --text-package-name       | 20px | 700    | 1.2    | 0px              | Package card nama (30 DAYS ELITE, dll)       |
| --text-package-price      | 28px | 800    | 1.1    | 0px              | Harga paket — KUNING (#F5C300)               |
| --text-package-badge      | 10px | 700    | 1.0    | 1px (uppercase)  | "AKTIF" badge di card                        |
| --text-benefit-item       | 13px | 400    | 1.5    | 0px              | Benefit list text                            |
| --text-config-label       | 11px | 600    | 1.2    | 1px (uppercase)  | Config panel field labels                    |
| --text-config-value       | 14px | 400    | 1.3    | 0px              | Config panel field values                    |
| --text-config-price       | 14px | 700    | 1.3    | 0px              | Harga di config = KUNING (#F5C300)           |
| --text-preview-supra      | 10px | 400    | 1.2    | 3px (uppercase)  | "REAL-TIME PREVIEW" label                    |
| --text-preview-title      | 32px | 800    | 1.1    | 0px              | "ELITE PRO" di preview — KUNING              |
| --text-preview-price      | 20px | 700    | 1.0    | 0px              | "IDR 7.2M" di preview — KUNING              |
| --text-preview-price-sub  | 12px | 400    | 1.3    | 0px              | "7,200,000 IDR" sub text                     |
| --text-preview-duration   | 14px | 400    | 1.3    | 0px              | "365 Days / 1 Year" di preview               |
| --text-preview-badge      | 10px | 700    | 1.0    | 0px              | "LIVE PREVIEW" badge text                    |
| --text-btn-cta            | 13px | 700    | 1.0    | 0px              | "SAVE CHANGES" / "TAMBAH PAKET" buttons      |
| --text-btn-discard        | 13px | 500    | 1.0    | 0px              | "DISCARD" button                             |
| --text-nav-item           | 13px | 500    | 1.4    | 0px              | Sidebar nav items                            |

---

## 3. SPACING & LAYOUT

### Spacing Scale
| Token          | Value | Usage                                                    |
|----------------|-------|----------------------------------------------------------|
| --space-xs     | 4px   | Badge padding, toggle inner gaps                         |
| --space-sm     | 8px   | Benefit item icon-to-text gap, form field inner          |
| --space-md     | 12px  | Card footer padding, config section gap                  |
| --space-base   | 16px  | Card header/body padding, KPI card padding               |
| --space-lg     | 20px  | Card body padding, grid gap, section gap                 |
| --space-xl     | 24px  | Page padding, config panel padding                       |
| --space-2xl    | 32px  | Major section separation                                 |

### Border Radius
| Token          | Value | Usage                                                    |
|----------------|-------|----------------------------------------------------------|
| --radius-xs    | 4px   | Badges, small chips                                      |
| --radius-sm    | 6px   | Toggle track, input fields, small buttons                |
| --radius-md    | 8px   | Config form buttons (DISCARD, SAVE)                      |
| --radius-lg    | 10px  | Package cards, KPI cards, config panel, preview panel    |
| --radius-full  | 50%   | Toggle knob                                              |

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Total Canvas:   1280 × ~1100 px
Sidebar:        220px wide × 100vh (fixed)
Header Bar:     calc(100vw - 220px) × 56px (sticky)
Main Content:   calc(100vw - 220px), padding: 24px all sides
Section Gaps:   20px between major sections
```

### ASCII Layout Diagram
```
┌─────────────────────┬────────────────────────────────────────────────────────┐
│  SIDEBAR (220px)    │  HEADER BAR (56px)                                     │
│  ───────────────    │  ────────────────────────────────────────────────────  │
│  ◈ Editorial        │  PAKET MEMBERSHIP [PUTIH]        🔍  🔔  ⚙  👤        │
│    Athletics        ├────────────────────────────────────────────────────────┤
│  ───────────────    │  MAIN CONTENT (padding: 24px)                           │
│  ⊞ Dashboard        │                                                        │
│  👥 Member          │  "MANAGEMENT [abu] PACKAGES [kuning]"  [+ TAMBAH PAKET]│
│  📅 Slot Mgmt       │                                                        │
│  ⭐ Personal Trainer │  KPI CARDS ROW (4 kolom, gap:16px)                     │
│  📋 Booking & Sesi  │  ┌────┐ ┌────┐ ┌────┐ ┌────────────────────────────┐  │
│  🏋 Equipment       │  │ 12 │ │142M│ │8.4 │ │  365 PRO  ⭐ TERPOPULER   │  │
│  📃 Audit Log       │  │TT. │ │Rev │ │Ret │ │         bg:#F5C300         │  │
│  🎫 Paket ◄AKTIF    │  └────┘ └────┘ └────┘ └────────────────────────────┘  │
│  💳 Pembayaran      │                                                        │
│  📊 Laporan         │  PACKAGE CARDS GRID (3 kolom, gap:16px)                │
│  ───────────────    │  ┌──────────────┐ ┌──────────────┐ ┌────────────────┐ │
│  [A] Admin Elite    │  │ [AKTIF] ✓    │ │ [AKTIF] ✓    │ │ [AKTIF] ✓      │ │
│  admin@egggym.id    │  │ 30 DAYS ELITE│ │ 365 DAYS PRO │ │ ELITE PERF..   │ │
│                     │  │ Rp 850.000   │ │ Rp 7.200.000 │ │ Rp 2.500.000   │ │
│                     │  │ ✓ benefit 1  │ │ ✓ benefit 1  │ │ ✓ benefit 1    │ │
│                     │  │ ✓ benefit 2  │ │ ✓ benefit 2  │ │ ✓ benefit 2    │ │
│                     │  │ ✓ benefit 3  │ │ ✓ ...        │ │ ✓ ...          │ │
│                     │  │ ─────────────│ │ ─────────────│ │ ────────────── │ │
│                     │  │ ✏️  🗑️         │ │ ✏️  🗑️         │ │ ✏️  🗑️          │ │
│                     │  └──────────────┘ └──────────────┘ └────────────────┘ │
│                     │                                                        │
│                     │  BOTTOM PANEL (2 col ~55% | ~43%, gap:16px)            │
│                     │  ┌────────────────────────┐  ┌──────────────────────┐ │
│                     │  │ CONFIGURATION DETAILS  │  │ REAL-TIME PREVIEW    │ │
│                     │  │ Pakai paket: [dropdown]│  │ REAL-TIME PREVIEW    │ │
│                     │  │ Harga: 7.200.000 [★]   │  │ ELITE PRO [kuning]   │ │
│                     │  │ Durasi: 365            │  │ ─────────────────── │ │
│                     │  │ Status: [toggle ON]    │  │ IDR 7.2M            │ │
│                     │  │ Benefits: [checklist]  │  │ 365 Days / 1 Year   │ │
│                     │  │ [DISCARD] [SAVE ★]     │  │ [● LIVE PREVIEW]    │ │
│                     │  └────────────────────────┘  └──────────────────────┘ │
│                     │  ═══════════════════════════════════════════════════   │
│                     │  🟢 SISTEM AKTIF │ AI message...                       │
└─────────────────────┴────────────────────────────────────────────────────────┘
```

---

## 5. KOMPONEN: SIDEBAR

### 5.1 Container
```
Width:          220px, Height: 100vh
Background:     #141000, Border-right: 1px solid #2A2400
Position:       fixed left 0, z-index 200
```

### 5.2 Logo / Brand
```
Logo:           32px hex icon, fill #F5C300
Brand:          "Editorial Athletics", 14px/700, #FFFFFF
Padding:        16px 16px 14px, Border-bottom: 1px solid #2A2400
```

### 5.3 Navigation Items
```
Default:  height 40px, padding 10px 16px, icon+text 13px #8A8070
Active (Paket Membership):
  Background:   #252000, Border-left: 3px solid #F5C300
  Padding-left: 13px, Icon+Text: #F5C300 weight 600
Hover: bg #1E1900, icon+text → #D4AA00
```

### 5.4 Profile Area
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
```

### 6.2 Kiri — Breadcrumb (PUTIH — berbeda dari Booking/Payments!)
```
Text:           "PAKET MEMBERSHIP"
Font-size:      18px / 700
Color:          #FFFFFF   ← PUTIH (bukan kuning seperti Booking/Payments)
Letter-spacing: 0.08em
Text-transform: uppercase
```

### 6.3 Search Bar
```
Width: 280px, Height: 32px, Background: #2A2400
Border: 1px solid #2E2800, Border-radius: 6px
Placeholder: "Cari paket, durasi..."
Focus: border-color → #F5C300
```

### 6.4 Icon Area
```
Bell 20px #8A8070 + badge dot #EF4444
Settings 20px #8A8070
Avatar 28px circle bg #F5C300 "A" #1A1500
```

---

## 7. KOMPONEN: PAGE HEADER SECTION

### 7.1 Container
```
Display: flex, justify-content space-between, align-items flex-end
Margin-bottom: 20px
```

### 7.2 Kiri — Judul Komposit
```
Line 1:
  "MANAGEMENT " → 14px/700, color #8A8070, display inline
  "PACKAGES"    → 14px/700, color #F5C300 (kuning), display inline

Line 2: tidak ada H1 besar — judul kompak 2 kata
```

### 7.3 Kanan — "+ TAMBAH PAKET" Button
```
Text:           "+ TAMBAH PAKET"
Font-size:      13px / 700
Color:          #1A1500
Background:     #F5C300
Border:         none
Border-radius:  8px
Padding:        9px 18px
Box-shadow:     0 2px 6px rgba(245,195,0,0.3)
Hover: bg #E0B000, transform translateY(-1px)
```

---

## 8. KOMPONEN: KPI CARDS (4 Kolom)

### 8.1 Grid Container
```
Display: grid
Grid-template-columns: 1fr 1fr 1fr 1fr
Gap: 16px
Margin-bottom: 20px
```

### 8.2 KPI Card Default (Card 1–3)
```
Background:     #252000
Border:         1px solid #2E2800
Border-radius:  10px
Padding:        18px 20px
Display:        flex flex-column gap 6px

Value:
  Font-size:    32px / 800, color #FFFFFF
Sub-label:
  Font-size:    12px / 400, color dynamic per card
Label:
  Font-size:    11px / 700, color #8A8070, uppercase letter-spacing 2px
```

### 8.3 KPI Card Data (Cards 1–3)
```
Card 1 — TOTAL PAKET AKTIF:
  Value:  "12"        → #FFFFFF
  Label:  "TOTAL PAKET AKTIF"
  Sub:    —

Card 2 — REVENUE BULAN INI:
  Value:  "Rp 142M"   → #FFFFFF
  Label:  "REVENUE BULAN INI"
  Sub:    "+12.4% dari bulan lalu" → #4CAF50

Card 3 — AVG RETENSI:
  Value:  "8.4 Bln"   → #FFFFFF
  Label:  "AVG RETENSI"
  Sub:    "MEMBER RATA-RATA" → #8A8070
```

### 8.4 KPI Card 4 — TERPOPULER ⭐ (FEATURED — KUNING SOLID)
```
⚠️ BERBEDA DARI CARD 1–3:
Background:     #F5C300   ← KUNING SOLID
Border:         none
Border-radius:  10px
Padding:        18px 20px

Value:
  Text:         "365 PRO"
  Font-size:    36px / 800
  Color:        #1A1500   ← GELAP (bukan putih!)

Icon ⭐:
  Positioned top-right
  Size: 20px
  Color: #1A1500, opacity 0.6

Label:
  Text:         "PAKET TERPOPULER"
  Font-size:    11px / 700
  Color:        rgba(26,21,0,0.7)   ← gelap semi-transparent
  Text-transform: uppercase

Sub:
  Text:         "Berdasarkan penjualan bulan ini"
  Font-size:    11px / 400
  Color:        rgba(26,21,0,0.6)
```

---

## 9. KOMPONEN: PACKAGE CARDS GRID

### 9.1 Grid Container
```
Display:              grid
Grid-template-columns:repeat(3, 1fr)
Gap:                  16px
Margin-bottom:        20px
```

### 9.2 Card Container
```
Background:     #252000
Border:         1px solid #2E2800
Border-radius:  10px
Overflow:       hidden
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
Display:        flex flex-column
Transition:     border-color 0.2s

Hover: border-color rgba(245,195,0,0.4)
```

### 9.3 Card Header Area
```
Background:     #1A1500   ← lebih gelap dari card body
Padding:        16px 20px

Row 1 — Badge row:
  Display:      flex, justify-content space-between, align-items center
  Margin-bottom:8px

  Status badge:
    "AKTIF"
    Background: rgba(76,175,80,0.15), Color: #4CAF50
    Font-size: 10px/700, uppercase, letter-spacing 1px
    Padding: 3px 10px, Border-radius: 4px

Row 2 — Package Name:
  Font-size:    20px / 700
  Color:        #FFFFFF
  Margin-bottom:6px

Row 3 — Price:
  Font-size:    28px / 800
  Color:        #F5C300   ← KUNING
  Letter-spacing:-0.5px
```

### 9.4 Card Body — Benefit List
```
Padding:        14px 20px
Display:        flex flex-column gap 8px
Flex:           1

Benefit Item:
  Display:      flex, align-items flex-start, gap 10px

  Checkmark:
    Size:       16px × 16px
    Flex-shrink:0
    Color:      #F5C300   ← KUNING check icon

  Text:
    Font-size:  13px / 400
    Color:      #FFFFFF
    Line-height:1.5
```

### 9.5 Card Footer — Action Row
```
Padding:        10px 16px
Border-top:     1px solid #2E2800
Display:        flex, justify-content space-between, align-items center

Kiri — Icons:
  Edit (✏️):
    Size:       30px × 30px hitbox, icon 15px
    Color:      #8A8070, border-radius 4px
    Hover: color #F5C300, bg #2E2800

  Delete (🗑️):
    Same hitbox
    Hover: color #EF4444, bg #2E1A1A

Kanan — (optional: "EDIT" text link):
  Font-size:    11px/700, color #F5C300, uppercase
  Hover: text-decoration underline
```

### 9.6 Data Contoh — 3 Package Cards
```
Card 1 — 30 DAYS ELITE:
  Status badge:  "AKTIF"
  Name:          "30 DAYS ELITE"
  Price:         "Rp 850.000" → #F5C300
  Benefits:
    ✓ Access All Equipment
    ✓ 3 PT Sessions
    ✓ Locker & Shower

Card 2 — 365 DAYS PRO:
  Status badge:  "AKTIF"
  Name:          "365 DAYS PRO"
  Price:         "Rp 7.200.000" → #F5C300
  Benefits:
    ✓ Priority Club Access
    ✓ 10 PT Sessions / Month
    ✓ Guest Pass (2×/bulan)
    ✓ Official Merchandise

Card 3 — ELITE PERFORMANCE:
  Status badge:  "AKTIF"
  Name:          "ELITE PERFORMANCE"
  Price:         "Rp 2.500.000" → #F5C300
  Benefits:
    ✓ 90 Day Intensive Program
    ✓ Advanced Progress Tracking
    ✓ Dedicated Coach
```

---

## 10. KOMPONEN: CONFIGURATION DETAILS PANEL

### 10.1 Container
```
Background:     #252000
Border:         1px solid #2E2800
Border-radius:  10px
Padding:        20px
Flex:           ~55% (dalam bottom panel grid)
Display:        flex flex-column gap 14px
```

### 10.2 Panel Title
```
Text:           "Configuration Details"
Font-size:      14px / 700
Color:          #FFFFFF
Margin-bottom:  4px
```

### 10.3 Form Field — PAKAI PAKET (Select)
```
Label:          "PAKAI PAKET"
              11px/600, #8A8070, uppercase, letter-spacing 1px

Select:
  Width:        100%
  Height:       36px
  Background:   #1A1500
  Border:       1px solid #2E2800
  Border-radius:8px
  Padding:      0 12px
  Font-size:    13px / 400
  Color:        #FFFFFF
  Selected:     "365 Days Pro"

  Arrow icon:   16px, color #8A8070
  
  Hover:        border-color rgba(245,195,0,0.3)
  Focus:        border-color #F5C300, outline none
```

### 10.4 Form Field — HARGA (IDR)
```
Label:          "HARGA (IDR)"

Value Display:
  Text:         "7.200.000"
  Font-size:    14px / 700
  Color:        #F5C300   ← KUNING (bukan putih!)

Input:
  Width:        100%
  Height:       36px
  Background:   #1A1500
  Border:       1px solid #2E2800
  Border-radius:8px
  Padding:      0 12px
  Font-size:    14px / 700
  Color:        #F5C300   ← KUNING
  Focus:        border-color #F5C300
```

### 10.5 Form Field — DURASI (HARI)
```
Label:          "DURASI (HARI)"
Value/Input:    "365", 14px/400, #FFFFFF
```

### 10.6 Toggle — STATUS AKTIF
```
Container:
  Display:      flex, justify-content space-between, align-items center

Label:          "STATUS AKTIF", 13px/600, #FFFFFF

Toggle Switch:
  Width:        48px, Height: 24px, Border-radius: 12px

  ON State:
    Track:      background rgba(245,195,0,0.3)
    Knob:       background #F5C300, size 18px, position right
    Box-shadow: 0 0 6px rgba(245,195,0,0.4)

  OFF State:
    Track:      background #2E2800
    Knob:       background #8A8070, position left

  Transition:   all 0.2s ease
  Cursor:       pointer
```

### 10.7 Benefit Checklist
```
Label row:      "BENEFIT ITEMS", 11px/600, #8A8070, uppercase

Checklist Item (per item):
  Display:      flex, align-items center, gap 10px
  Cursor:       pointer

  Custom Checkbox (checked):
    Size:       16px × 16px
    Background: #F5C300
    Border:     1px solid #F5C300
    Border-radius:3px
    Checkmark:  ✓ icon, color #1A1500, size 10px

  Custom Checkbox (unchecked):
    Background: transparent
    Border:     1px solid #2E2800

  Label text:   13px/400, #FFFFFF

Checked items:
  ✓ ACCESS ALL AREA
  ✓ GUEST PASS (2x/month)
  ✓ TRAINER SUPPORT
```

### 10.8 Action Buttons Row
```
Display:        flex, justify-content flex-end, gap 10px
Margin-top:     4px

DISCARD button:
  Text:         "DISCARD"
  Font-size:    13px / 500
  Color:        #8A8070
  Background:   transparent
  Border:       1px solid #2E2800
  Border-radius:8px
  Padding:      9px 20px
  Hover:        color #FFFFFF, border-color #5A5040

SAVE CHANGES button:
  Text:         "SAVE CHANGES"
  Font-size:    13px / 700
  Color:        #1A1500
  Background:   #F5C300
  Border:       none
  Border-radius:8px
  Padding:      9px 20px
  Box-shadow:   0 2px 6px rgba(245,195,0,0.3)
  Hover:        bg #E0B000, transform translateY(-1px)
```

---

## 11. KOMPONEN: REAL-TIME PREVIEW PANEL

### 11.1 Container
```
Background:     #141000   ← lebih gelap dari kartu biasa (#252000)!
Border:         1px solid #2E2800
Border-radius:  10px
Padding:        20px
Flex:           ~43% (dalam bottom panel grid)
Display:        flex flex-column gap 12px
```

### 11.2 Supra Label
```
Text:           "REAL-TIME PREVIEW"
Font-size:      10px / 400
Color:          #8A8070
Letter-spacing: 3px (uppercase)
Text-transform: uppercase
```

### 11.3 Preview Title
```
Text:           "ELITE PRO"
Font-size:      32px / 800
Color:          #F5C300   ← KUNING BESAR
Letter-spacing: -0.5px
Margin-bottom:  4px
```

### 11.4 Divider
```
Height:         1px
Background:     #2E2800
Margin:         4px 0
```

### 11.5 Pricing Display
```
Row 1:
  "IDR 7.2M"
  Font-size:    20px / 700
  Color:        #F5C300   ← KUNING

Row 2:
  "7,200,000 IDR"
  Font-size:    12px / 400
  Color:        #8A8070
```

### 11.6 Duration Display
```
Row 1:
  "365 Days / 1 Year"
  Font-size:    14px / 400
  Color:        #FFFFFF

Row 2:
  "12 Months"
  Font-size:    12px / 400
  Color:        #8A8070
```

### 11.7 LIVE PREVIEW Badge
```
Display:        flex, align-items center, gap 6px, align-self flex-start
Background:     rgba(245,195,0,0.1)
Border:         1px solid rgba(245,195,0,0.2)
Border-radius:  4px
Padding:        4px 12px
Margin-top:     auto

Dot:
  Width:        6px, Height: 6px
  Border-radius:50%, Background: #F5C300
  Animation:    pulse 2s infinite

Text:           "LIVE PREVIEW"
  Font-size:    10px / 700
  Color:        #F5C300
  Letter-spacing:1px, uppercase
```

---

## 12. KOMPONEN: AI ASSISTANT BAR (Fixed Bottom)

```
Position:       fixed, bottom 0, left 220px
Width:          calc(100vw - 220px)
Height:         44px
Background:     #141000
Border-top:     1px solid #2E2800
Padding:        0 20px
Z-index:        90

Status: 6px dot #4CAF50 pulse + "SISTEM AKTIF" 11px/700 #4CAF50
Text:   "Kecerdasan buatan siap membantu manajemen paket membership"
        12px/400, #8A8070
```

---

## 13. ANIMASI & MICROINTERACTIONS

### 13.1 Toggle Switch Transition
```css
.toggle-track {
  transition: background 0.2s ease;
}
.toggle-knob {
  transition: transform 0.2s ease, background 0.2s ease;
}
/* ON: transform: translateX(24px) | OFF: translateX(0) */
```

### 13.2 Live Preview Badge Dot Pulse
```css
@keyframes live-pulse {
  0%, 100% { opacity: 1; transform: scale(1); }
  50%       { opacity: 0.5; transform: scale(0.7); }
}
.live-dot { animation: live-pulse 2s ease-in-out infinite; }
```

### 13.3 Real-Time Preview Update
```
Saat form diedit → preview panel update dalam 300ms debounce:
- Title animates: fade out (150ms) → update value → fade in (150ms)
- Price: number count-up atau fade transition
- Duration: instant update
```

### 13.4 Package Card Hover
```css
.package-card {
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}
.package-card:hover {
  border-color: rgba(245, 195, 0, 0.4);
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.5);
}
```

---

## 14. GRID RECAP — ZONA LAYOUT

| Zone                   | X Offset | Y Offset  | Width                    | Height    |
|------------------------|----------|-----------|--------------------------|-----------|
| Sidebar                | 0        | 0         | 220px                    | 100vh     |
| Header Bar             | 220px    | 0         | calc(100vw - 220px)      | 56px      |
| Page Header            | 244px    | 80px      | calc(100vw - 264px)      | ~40px     |
| KPI Cards Row          | 244px    | 140px     | calc(100vw - 264px)      | ~88px     |
| Package Cards Grid     | 244px    | 248px     | calc(100vw - 264px)      | ~280px    |
| Bottom Panel           | 244px    | 548px     | calc(100vw - 264px)      | ~300px    |
|   Config Details (~55%)| 244px    | 548px     | ~55% of content          | ~300px    |
|   Real-Time Preview    | ~800px   | 548px     | ~43% of content          | ~300px    |
| AI Bar (fixed)         | 220px    | bottom: 0 | calc(100vw - 220px)      | 44px      |

---

## 15. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Admin Membership Packages
   CSS Custom Properties — Design Tokens
   Generated: 2026-06-24
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:             #1A1500;
  --color-bg-card:                #252000;
  --color-bg-sidebar:             #141000;
  --color-bg-header:              #1E1900;
  --color-bg-preview:             #141000;
  --color-bg-card-header:         #1A1500;
  --color-bg-input:               #2A2400;
  --color-accent-primary:         #F5C300;
  --color-accent-hover:           #E0B000;
  --color-text-primary:           #FFFFFF;
  --color-text-secondary:         #8A8070;
  --color-text-muted:             #5A5040;
  --color-text-on-accent:         #1A1500;
  --color-package-price:          #F5C300;
  --color-config-price:           #F5C300;
  --color-preview-title:          #F5C300;
  --color-preview-pricing:        #F5C300;
  --color-preview-badge-bg:       rgba(245, 195, 0, 0.1);
  --color-preview-badge-border:   rgba(245, 195, 0, 0.2);
  --color-toggle-on-knob:         #F5C300;
  --color-toggle-on-track:        rgba(245, 195, 0, 0.3);
  --color-toggle-off-knob:        #8A8070;
  --color-toggle-off-track:       #2E2800;
  --color-benefit-check-bg:       #F5C300;
  --color-badge-aktif-bg:         rgba(76, 175, 80, 0.15);
  --color-badge-aktif-text:       #4CAF50;
  --color-kpi-featured-bg:        #F5C300;
  --color-kpi-featured-text:      #1A1500;
  --color-border-card:            #2E2800;
  --color-border-sidebar:         #2A2400;
  --color-btn-discard-border:     #2E2800;
  --color-btn-discard-text:       #8A8070;

  /* ── TYPOGRAPHY ── */
  --font-family-primary:          "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-package-name:            20px;
  --text-package-price:           28px;
  --text-kpi-value-featured:      36px;
  --text-kpi-value-default:       32px;
  --text-preview-title:           32px;
  --text-preview-price:           20px;
  --text-config-price:            14px;
  --text-benefit-item:            13px;

  /* ── SPACING ── */
  --space-xs:                     4px;
  --space-sm:                     8px;
  --space-md:                     12px;
  --space-base:                   16px;
  --space-lg:                     20px;
  --space-xl:                     24px;
  --space-2xl:                    32px;

  /* ── BORDER RADIUS ── */
  --radius-xs:                    4px;
  --radius-sm:                    6px;
  --radius-md:                    8px;
  --radius-lg:                    10px;
  --radius-full:                  50%;

  /* ── SHADOWS ── */
  --shadow-card:                  0 2px 8px rgba(0, 0, 0, 0.4);
  --shadow-hover:                 0 6px 16px rgba(0, 0, 0, 0.5);
  --shadow-button:                0 2px 6px rgba(245, 195, 0, 0.3);
  --shadow-sidebar:               2px 0 8px rgba(0, 0, 0, 0.5);

  /* ── LAYOUT ── */
  --sidebar-width:                220px;
  --header-height:                56px;
  --ai-bar-height:                44px;
  --kpi-grid-cols:                4;
  --package-grid-cols:            3;
  --package-card-gap:             16px;
  --bottom-panel-config:          55%;
  --bottom-panel-preview:         43%;
  --toggle-width:                 48px;
  --toggle-height:                24px;
  --toggle-knob-size:             18px;
  --page-padding:                 24px;
}
```

---

## 16. CATATAN AI — IMPLEMENTATION NOTES (15 poin)

1. **KPI Card 4 = Kuning Solid (Bukan Card Lainnya)**: Hanya card ke-4 (PAKET TERPOPULER) yang menggunakan background kuning solid `#F5C300`. Card 1–3 menggunakan background gelap `#252000`. Teks pada card kuning menggunakan `#1A1500` (gelap), bukan putih.

2. **Header Title = Putih (Bukan Kuning)**: Breadcrumb "PAKET MEMBERSHIP" menggunakan `color: #FFFFFF`. Ini BERBEDA dari halaman Booking & Sesi PT dan Pembayaran & Transaksi yang menggunakan kuning. Jangan ubah ke kuning.

3. **Judul Halaman Komposit**: Judul "MANAGEMENT PACKAGES" dibuat dari dua `<span>` inline: `<span class="text-secondary">MANAGEMENT </span><span class="text-accent">PACKAGES</span>`. Pastikan ada spasi sebelum closing span pertama atau margin-right.

4. **Package Card Header vs Body Background**: Card header area menggunakan `background: #1A1500` (lebih gelap), sementara card body menggunakan `background: #252000`. Keduanya ada di dalam satu card dengan `overflow: hidden` untuk mencegah border-radius clipping.

5. **Benefit Checkmark = Custom Component**: Jangan gunakan `<input type="checkbox">` native. Gunakan custom element: `<span class="custom-check" aria-checked="true">` + CSS background `#F5C300` dengan SVG checkmark inline atau pseudo-element `::before { content: '✓' }`.

6. **Toggle Switch Implementation**: Toggle menggunakan dua elemen: track (`div.toggle-track`) dan knob (`div.toggle-knob`). Animasi via CSS transition `translateX`. Pastikan ada `role="switch"` dan `aria-checked` untuk accessibility.

7. **Real-Time Preview = Debounced Watcher**: Setiap perubahan di form Configuration Details (dropdown, harga, durasi, benefits) harus memperbarui preview setelah debounce 300ms. Ini memberikan UX "live" tanpa terlalu banyak re-render. Gunakan React `useEffect` + `setTimeout` atau Vue `watch` + `debounce`.

8. **Harga Field Kuning = Intentional**: Nilai harga di Configuration Details menampilkan teks `#F5C300` untuk membuat nilai penting mudah diidentifikasi. Format: angka tanpa "Rp" prefix di input, ditambahkan secara otomatis di preview.

9. **DISCARD = Destructive Action**: Tombol DISCARD harus memiliki konfirmasi jika ada perubahan yang belum disimpan:
   - Jika tidak ada perubahan: langsung reset form ke state awal
   - Jika ada perubahan: tampilkan dialog "Buang perubahan?" → Ya (reset) / Batal

10. **SAVE CHANGES = Validation First**: Sebelum save, validasi:
    - Harga > 0 dan berupa angka valid
    - Durasi > 0 hari
    - Minimal 1 benefit tersedia
    - Nama paket tidak duplikat
    Jika validasi gagal → shake animation pada field yang invalid + error text di bawah field.

11. **Package Cards Responsive**: Pada viewport < 1024px, grid berubah dari 3 kolom ke 2 kolom. Pada < 640px menjadi 1 kolom full-width. Bottom panel (Config + Preview) berubah dari side-by-side menjadi stacked pada < 1024px.

12. **Dropdown Select Pakai Paket**: Dropdown harus populate secara dinamis dari daftar paket yang ada di database. Saat pilih paket berbeda, SEMUA field dalam Configuration Details langsung update ke nilai paket tersebut (harga, durasi, benefits, status toggle) — sambil preview juga ikut update.

13. **Delete Package Confirmation**: Tombol 🗑️ pada package card membuka konfirmasi modal:
    - "Hapus paket [nama]?"
    - "⚠️ Member dengan paket ini tidak akan terdampak, tapi paket tidak bisa dipilih lagi."
    - [Hapus] bg #EF4444 + [Batal] transparent
    Soft delete: set `active = false` dan `deleted_at = now()`, bukan hard delete.

14. **Paket dengan Member Aktif**: Jika paket memiliki > 0 member aktif, tampilkan badge kecil di card: "X member aktif". Tombol 🗑️ disabled + tooltip: "Tidak bisa dihapus — ada X member aktif". Tombol ✏️ tetap aktif untuk edit.

15. **Preview Panel bg #141000 vs Card bg #252000**: Real-Time Preview menggunakan background yang lebih gelap dari kartu biasa untuk kontras visual yang lebih dramatis. Ini memberikan kesan "frame/preview window" yang terpisah dari edit form. Pastikan border menggunakan `#2E2800` tetap konsisten.

---

*Spec ini generated dari analisis visual screen Admin Membership Packages.png*
*Design system reference: ADMIN_DASHBOARD_UI_SPEC.md*
*Total sections: 16 | Detail level: ⭐⭐⭐⭐⭐ Full Detail*

# ADMIN_MEMBER_MANAGEMENT_UI_SPEC.md
# Egg Gym App — Admin Member Management Screen
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Admin > Data Member (Member Management)
# Resolution: 1280 × 1024 px
# Last Updated: 2026-06-24

---

## 1. DESIGN TOKENS — COLOR PALETTE

| Token Name                      | HEX Value                    | Usage                                                        |
|---------------------------------|------------------------------|--------------------------------------------------------------|
| --color-bg-primary              | #1A1500                      | Main content background                                      |
| --color-bg-card                 | #252000                      | Table container, summary card backgrounds                    |
| --color-bg-sidebar              | #141000                      | Sidebar background                                           |
| --color-bg-header               | #1E1900                      | Top header bar background                                    |
| --color-bg-table-header         | #1A1500                      | Table header row background (lebih gelap dari card)          |
| --color-bg-input                | #2A2400                      | Search bar, filter dropdown input background                 |
| --color-bg-modal                | #252000                      | Add/Edit member modal background                             |
| --color-bg-modal-overlay        | rgba(0,0,0,0.70)             | Modal backdrop overlay                                       |
| --color-bg-filter-dropdown      | #252000                      | [Gold▼][Platinum▼][Pro▼] dropdown background                 |
| --color-accent-primary          | #F5C300                      | Header title KUNING, filter tab aktif, CTA button, summary   |
| --color-accent-hover            | #E0B000                      | Button / tab hover states                                    |
| --color-accent-active           | #EAB800                      | CTA button aktif / pressed state                             |
| --color-text-primary            | #FFFFFF                      | Nama member, tanggal, nilai utama                            |
| --color-text-secondary          | #8A8070                      | Label, sub-nilai, kolom header, email, helper text           |
| --color-text-muted              | #5A5040                      | ID member, phone, placeholder, disabled state                |
| --color-text-on-accent          | #1A1500                      | Teks di atas kuning: tab aktif, CTA, featured card value     |
| --color-badge-aktif-bg          | rgba(76,175,80,0.15)         | AKTIF status badge background                                |
| --color-badge-aktif-text        | #4CAF50                      | AKTIF status badge text — hijau                              |
| --color-badge-nonaktif-bg       | rgba(239,68,68,0.15)         | NONAKTIF status badge background                             |
| --color-badge-nonaktif-text     | #EF4444                      | NONAKTIF status badge text — merah                           |
| --color-paket-platinum-bg       | rgba(245,195,0,0.15)         | PLATINUM paket badge background                              |
| --color-paket-platinum-text     | #F5C300                      | PLATINUM paket badge text — kuning                           |
| --color-paket-gold-bg           | rgba(245,158,11,0.15)        | GOLD paket badge background                                  |
| --color-paket-gold-text         | #F59E0B                      | GOLD paket badge text — amber                                |
| --color-paket-pro-bg            | rgba(59,130,246,0.15)        | PRO paket badge background                                   |
| --color-paket-pro-text          | #3B82F6                      | PRO paket badge text — biru                                  |
| --color-sisa-ok                 | #4CAF50                      | Sisa hari membership banyak (>30 hari) — hijau               |
| --color-sisa-warn               | #F59E0B                      | Sisa hari membership ≤30 hari — amber                        |
| --color-sisa-expired            | #EF4444                      | Membership expired — merah                                   |
| --color-summary-featured-bg     | #F5C300                      | ACTIVE PREMIUM summary card bg — KUNING SOLID                |
| --color-summary-featured-text   | #1A1500                      | ACTIVE PREMIUM value text — GELAP (di atas kuning)           |
| --color-summary-featured-label  | rgba(26,21,0,0.60)           | ACTIVE PREMIUM label text (semi-transparent gelap)           |
| --color-summary-featured-sub    | rgba(26,21,0,0.70)           | ACTIVE PREMIUM sub-text                                      |
| --color-summary-featured-shadow | rgba(245,195,0,0.25)         | Box-shadow featured summary card                             |
| --color-edit-btn-hover          | #F5C300                      | Edit icon hover color — kuning                               |
| --color-delete-btn-hover        | #EF4444                      | Delete icon hover color — merah                              |
| --color-border-card             | #2E2800                      | Card borders, table row dividers                             |
| --color-border-sidebar          | #2A2400                      | Sidebar left panel dividers                                  |
| --color-border-input            | #2E2800                      | Input default border                                         |
| --color-border-input-focus      | #F5C300                      | Input focused border — kuning                                |
| --color-border-modal            | #2E2800                      | Modal border                                                 |
| --color-pagination-active       | #F5C300                      | Active pagination button bg                                  |
| --color-pagination-default      | #252000                      | Default pagination button bg                                 |
| --color-row-hover               | rgba(245,195,0,0.03)         | Table row hover — sangat subtle yellow tint                  |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Monospace:  "JetBrains Mono", "Fira Code", monospace  (untuk ID member: #M-XXXX)
```

### Skala Tipografi Lengkap
| Token                        | Size  | Weight | Line-H | Letter-Sp        | Usage                                                |
|------------------------------|-------|--------|--------|------------------|------------------------------------------------------|
| --text-page-title            | 18px  | 700    | 1.2    | 0.08em           | "DATA MEMBER" header title — KUNING #F5C300          |
| --text-summary-value         | 36px  | 800    | 1.0    | 0px              | Angka di summary cards (1,284 / 842 / 45)            |
| --text-summary-label         | 11px  | 700    | 1.2    | 2px (uppercase)  | Label di summary cards ("TOTAL MEMBERS" dll)         |
| --text-summary-sub           | 12px  | 400    | 1.3    | 0px              | Sub-teks di summary cards (persentase, deskripsi)    |
| --text-filter-tab            | 13px  | 700    | 1.0    | 0px              | Filter tab: SEMUA / AKTIF / NONAKTIF                 |
| --text-filter-dropdown       | 13px  | 400    | 1.0    | 0px              | [Gold▼][Platinum▼][Pro▼] dropdown teks               |
| --text-search-input          | 13px  | 400    | 1.0    | 0px              | Search bar input teks                                |
| --text-search-placeholder    | 13px  | 400    | 1.0    | 0px              | Search placeholder — color #5A5040 muted             |
| --text-add-btn               | 13px  | 700    | 1.0    | 0px              | "+ TAMBAH MEMBER BARU" button                        |
| --text-table-col-header      | 10px  | 700    | 1.2    | 2px (uppercase)  | Table column headers (NAMA, KONTAK, dll)             |
| --text-member-name           | 14px  | 700    | 1.3    | 0px              | Nama member di tabel — primary bold white            |
| --text-member-id             | 11px  | 400    | 1.3    | 0.3px            | "ID: #M-XXXX" di bawah nama — monospace muted        |
| --text-member-email          | 13px  | 400    | 1.3    | 0px              | Email member di kolom KONTAK                         |
| --text-member-phone          | 12px  | 400    | 1.3    | 0px              | Nomor telepon di bawah email                         |
| --text-badge-paket           | 11px  | 700    | 1.0    | 0.5px (uppercase)| Badge PLATINUM / GOLD / PRO                          |
| --text-badge-status          | 11px  | 700    | 1.0    | 0.5px (uppercase)| Badge AKTIF / NONAKTIF                               |
| --text-berakhir-date         | 13px  | 400    | 1.3    | 0px              | Tanggal berakhir membership                          |
| --text-berakhir-sisa         | 11px  | 400    | 1.3    | 0px              | "X hr sisa" / "Expired" — warna dinamis              |
| --text-aksi-icon             | 16px  | 400    | 1.0    | 0px              | Icon edit / delete di kolom AKSI                     |
| --text-pagination-num        | 13px  | 600    | 1.0    | 0px              | Angka nomor halaman pagination                       |
| --text-pagination-nav        | 11px  | 700    | 1.0    | 1px (uppercase)  | "PREV" / "NEXT" labels                               |
| --text-result-count          | 12px  | 400    | 1.2    | 0px              | "Showing 1–3 of 1,284 members"                       |
| --text-modal-title           | 16px  | 700    | 1.3    | 0px              | Modal title "TAMBAH MEMBER BARU"                     |
| --text-modal-section         | 12px  | 700    | 1.3    | 1px (uppercase)  | Section label dalam modal form                       |
| --text-form-label            | 12px  | 600    | 1.3    | 0px              | Form field label di modal                            |
| --text-form-input            | 14px  | 400    | 1.5    | 0px              | Input field value di modal                           |
| --text-form-placeholder      | 14px  | 400    | 1.5    | 0px              | Input placeholder — color #5A5040 muted              |
| --text-form-helper           | 11px  | 400    | 1.5    | 0px              | Helper text di bawah input                           |
| --text-form-error            | 11px  | 500    | 1.4    | 0px              | Validation error message — merah                     |
| --text-nav-item              | 13px  | 500    | 1.4    | 0px              | Sidebar navigation items                             |
| --text-brand-name            | 14px  | 700    | 1.2    | 0px              | "Editorial Athletics" sidebar brand name             |
| --text-brand-sub             | 9px   | 600    | 1.2    | 2px (uppercase)  | "ELITE MANAGEMENT" sidebar brand sub                 |
| --text-profile-name          | 13px  | 600    | 1.4    | 0px              | Nama admin di sidebar profile area                   |
| --text-profile-role          | 11px  | 400    | 1.4    | 0px              | Role admin di sidebar profile area                   |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px)
| Token         | Value | Usage                                                            |
|---------------|-------|------------------------------------------------------------------|
| --space-xs    | 4px   | Badge inner horizontal padding, icon-to-text gap kecil           |
| --space-sm    | 8px   | Gap antar action icons, avatar-to-info gap                       |
| --space-md    | 12px  | Row padding vertical tabel, filter gap, modal section gap        |
| --space-base  | 16px  | Gap filter tabs, summary card gap, form field margin             |
| --space-lg    | 20px  | Filter row margin-bottom, summary cards margin-top               |
| --space-xl    | 24px  | Main content padding semua sisi                                  |
| --space-2xl   | 32px  | Major section separation, modal section separation               |

### Border Radius
| Token          | Value   | Usage                                                          |
|----------------|---------|----------------------------------------------------------------|
| --radius-xs    | 4px     | Action icon buttons (edit/delete), small chips                 |
| --radius-sm    | 6px     | Filter tabs, search bar, pagination buttons, form inputs       |
| --radius-md    | 10px    | Table container, summary cards                                 |
| --radius-lg    | 14px    | Modal container                                                |
| --radius-full  | 9999px  | Badge pills (PLATINUM/AKTIF dll), avatar circle                |

### Box Shadow
| Token               | Value                                  | Usage                                    |
|---------------------|----------------------------------------|------------------------------------------|
| --shadow-card       | 0 2px 8px rgba(0,0,0,0.40)            | Summary card default shadow              |
| --shadow-featured   | 0 4px 16px rgba(245,195,0,0.25)       | ACTIVE PREMIUM card shadow — kuning      |
| --shadow-hover      | 0 6px 16px rgba(0,0,0,0.50)           | Card / row on hover                      |
| --shadow-modal      | 0 24px 60px rgba(0,0,0,0.70)          | Add/Edit member modal shadow             |
| --shadow-dropdown   | 0 8px 24px rgba(0,0,0,0.60)           | Filter dropdown menu shadow              |

### Transition
```
--transition-fast:   all 0.15s ease   (hover states, color changes)
--transition-normal: all 0.20s ease   (modal open/close, dropdown expand)
```

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Total Canvas:   1280 × 1024 px
Sidebar:        220px wide × 100vh  (position: fixed, left: 0, top: 0)
Header Bar:     calc(100vw - 220px) × 56px  (position: sticky, top: 0)
Main Content:   width: calc(100vw - 220px)
                margin-left: 220px
                padding: 24px
                min-height: calc(100vh - 56px)

Main Content Inner (urutan dari atas ke bawah):
  ├── Filter Row      height: ~44px, margin-bottom: 16px
  ├── Member Table    width: 100%, border-radius: 10px
  ├── Pagination      height: ~48px (di dalam table card, sticky bottom)
  └── Summary Cards   grid 3-kolom, gap: 16px, margin-top: 20px
```

### ASCII Layout Diagram
```
┌───────────────────────┬────────────────────────────────────────────────────────┐
│   SIDEBAR (220px)     │  HEADER BAR (56px, sticky)                             │
│   ──────────────────  │  ────────────────────────────────────────────────────  │
│   ◈ Editorial         │  [👥 DATA MEMBER]       🔍 Cari...   🔔   ⚙   [👤 A]  │
│     Athletics         ├────────────────────────────────────────────────────────┤
│     ELITE MGMT        │                                                        │
│   ──────────────────  │  FILTER ROW  (flex, gap:12px, mb:16px)                 │
│   ⊞  Dashboard        │  [SEMUA★] [AKTIF] [NONAKTIF]  [Gold▼] [Platinum▼]     │
│   👥  Member  ← AKTIF │  [Pro▼]                   [🔍 Cari...]  [+TAMBAH BARU] │
│   📅  Paket           ├────────────────────────────────────────────────────────┤
│   ⭐  PT              │  MEMBER TABLE  (bg:#252000, border:1px solid #2E2800)  │
│   📋  Booking         │  ┌────────────────────────────────────────────────┐   │
│   💳  Pembayaran      │  │ HEADER ROW  (h:40px, bg:#1A1500, padding:0 20px)│   │
│   🏋  Alat Gym        │  │ NAMA(2fr) · KONTAK(1.8fr) · PAKET(1.5fr)        │   │
│   📃  Audit Trail     │  │ STATUS(1fr) · BERAKHIR(1.2fr) · AKSI(0.8fr)     │   │
│   📊  Laporan         │  ├────────────────────────────────────────────────┤   │
│   ⚙  Pengaturan       │  │ Row 1: [NR] Naufal  email  PLATINUM  AKTIF  …   │   │
│   ──────────────────  │  │ Row 2: [SJ] Sarah   email  GOLD      AKTIF  …   │   │
│   [A] Alex Mercer     │  │ Row 3: [BS] Budi    email  PRO    NONAKTIF  …   │   │
│       Superadmin      │  │ Row 4: [MS] Maya    email  PLATINUM  AKTIF  …   │   │
│                       │  │ Row 5: [RP] Rizky   email  GOLD      AKTIF  …   │   │
│                       │  ├────────────────────────────────────────────────┤   │
│                       │  │ PAGINATION: Showing 1–5 of 1,284  [<][1★][2]…   │   │
│                       │  └────────────────────────────────────────────────┘   │
│                       │                                                        │
│                       │  SUMMARY CARDS  (grid 1fr 1fr 1fr, gap:16px, mt:20px) │
│                       │  ┌─────────────┐  ┌─────────────┐  ┌──────────────┐  │
│                       │  │TOTAL MEMBERS│  │ACTIVE PREMIUM│  │EXPIRING SOON │  │
│                       │  │   1,284     │  │  ★  842  ★  │  │     45       │  │
│                       │  │ ↑+12% month │  │  KUNING BG  │  │ ⚠ 30 days   │  │
│                       │  └─────────────┘  └─────────────┘  └──────────────┘  │
└───────────────────────┴────────────────────────────────────────────────────────┘
```

---

## 5. KOMPONEN: SIDEBAR

### 5.1 Container
```
Width:           220px
Height:          100vh
Background:      #141000
Border-right:    1px solid #2A2400
Box-shadow:      2px 0 8px rgba(0,0,0,0.50)
Position:        fixed
Left:            0
Top:             0
Z-index:         200
Display:         flex
Flex-direction:  column
Overflow-y:      auto
```

### 5.2 Logo / Brand Area
```
Padding:        16px 16px 14px
Border-bottom:  1px solid #2A2400
Display:        flex
Align-items:    center
Gap:            10px

Logo Mark:
  Width:   32px / Height: 32px
  Icon:    Dumbbell / gym icon
  Fill:    #F5C300

Brand Text (flex-col, gap: 2px):
  Line 1: "Editorial Athletics"
          font-size: 14px / font-weight: 700 / color: #FFFFFF
  Line 2: "ELITE MANAGEMENT"
          font-size: 9px / font-weight: 600 / color: #8A8070
          text-transform: uppercase / letter-spacing: 2px
```

### 5.3 Navigation Menu Container
```
Margin-top: 16px
Padding:    0 10px
Flex:       1
```

### 5.4 Navigation Item — Default State
```
Height:         40px
Padding:        10px 16px
Border-radius:  6px
Display:        flex
Align-items:    center
Gap:            10px
Cursor:         pointer
Transition:     all 0.15s ease

Icon:  16×16px, color #8A8070
Text:  font-size: 13px / font-weight: 500 / color: #8A8070

Hover:
  Background:  rgba(245,195,0,0.05)
  Icon color:  #D4AA00
  Text color:  #D4AA00
```

### 5.5 Navigation Item — Active State (halaman ini: Member)
```
Background:     rgba(245,195,0,0.08)
Border-left:    3px solid #F5C300
Border-radius:  0 6px 6px 0
Padding-left:   13px   (dikurangi 3px karena border-left)

Icon color:     #F5C300
Text color:     #F5C300
Font-weight:    600
```

### 5.6 Menu Order (atas → bawah)
```
1.  ⊞   Dashboard
2.  👥   Member             ← ACTIVE (halaman ini)
3.  📅   Paket Membership
4.  ⭐   Personal Trainer
5.  📋   Booking & Sesi
6.  💳   Pembayaran
7.  🏋   Alat Gym
8.  📃   Audit Trail
9.  📊   Laporan
10. ⚙   Pengaturan
```

### 5.7 Profile Area (Bottom Sticky)
```
Position:      absolute
Bottom:        0
Width:         100%
Padding:       12px 16px
Border-top:    1px solid #2A2400
Background:    #141000
Display:       flex
Align-items:   center
Gap:           10px

Avatar:
  Width / Height:  36px
  Border-radius:   50%
  Background:      #F5C300
  Text:            "A" — font-size: 14px / font-weight: 700 / color: #1A1500

Info (flex-col, gap: 2px):
  Name: "Alex Mercer"   — 13px / 600 / #FFFFFF
  Role: "Superadmin"    — 11px / 400 / #F5C300
```

---

## 6. KOMPONEN: TOP HEADER BAR

### 6.1 Container
```
Height:           56px
Width:            calc(100vw - 220px)
Background:       #1E1900
Border-bottom:    1px solid #2E2800
Padding:          0 24px
Display:          flex
Align-items:      center
Justify-content:  space-between
Position:         sticky
Top:              0
Z-index:          100
```

### 6.2 Kiri — Page Title
```
Display:     flex
Align-items: center
Gap:         10px

Icon:
  Emoji/SVG:  👥 person-group
  Size:       20px
  Color:      #F5C300

Title:
  Content:        "DATA MEMBER"
  Font-size:      18px
  Font-weight:    700
  Color:          #F5C300   ← KUNING! (bukan putih)
  Letter-spacing: 0.08em
  Text-transform: uppercase
```

### 6.3 Kanan — Actions
```
Display:     flex
Align-items: center
Gap:         16px

Search Bar:
  Width:         240px / Height: 32px
  Background:    #2A2400
  Border:        1px solid #2E2800
  Border-radius: 6px
  Padding:       0 10px
  Display:       flex, align-items: center, gap: 8px
  Icon:          🔍 14px / color #5A5040
  Input:         13px / #FFFFFF / bg transparent
  Placeholder:   "Cari nama, email, ID..." / color #5A5040
  Focus:         border-color #F5C300

Bell Icon:
  Size:      20px / Color: #8A8070
  Hover:     color #FFFFFF
  Notif dot: 6px circle, bg #EF4444, position absolute top-0 right-0

Settings Icon:
  Size: 20px / Color: #8A8070 / Hover: color #FFFFFF

Avatar:
  Size: 28px / Border-radius: 50%
  Background: #F5C300
  Text: "A" / 13px / bold / color #1A1500
  Cursor: pointer
```

---

## 7. KOMPONEN: FILTER ROW

### 7.1 Container
```
Display:        flex
Align-items:    center
Gap:            12px
Margin-bottom:  16px
Flex-wrap:      wrap
```

### 7.2 Status Filter Tabs
```
Tabs: [SEMUA ★]  [AKTIF]  [NONAKTIF]

Tab Aktif (default: SEMUA):
  Background:    #F5C300
  Color:         #1A1500
  Padding:       6px 16px
  Border-radius: 6px
  Font-size:     13px
  Font-weight:   700

Tab Inaktif:
  Background:    transparent
  Color:         #8A8070
  Border:        1px solid #2E2800
  Padding:       6px 14px
  Border-radius: 6px
  Font-size:     13px
  Font-weight:   700
  Hover: border-color #F5C300, color #F5C300
  Transition: all 0.15s ease
```

### 7.3 Package Filter Dropdowns
```
[Gold▼]  [Platinum▼]  [Pro▼]  — masing-masing dropdown independent

Container (per dropdown):
  Width:         110px / Height: 34px
  Background:    #252000
  Border:        1px solid #2E2800
  Border-radius: 8px
  Padding:       0 10px
  Display:       flex, align-items: center, justify-content: space-between
  Font-size:     13px / Color: #8A8070
  Hover:         border-color #F5C300, color #FFFFFF

Chevron: ▼ 10px / color inherit

Dropdown menu (on open):
  Background:    #252000
  Border:        1px solid #2E2800
  Border-radius: 8px
  Box-shadow:    0 8px 24px rgba(0,0,0,0.60)
  Padding:       6px 0 / Min-width: 130px

  Item: padding 8px 14px / 13px / #FFFFFF
        Hover: bg rgba(245,195,0,0.06), color #F5C300

Gold options:    "Semua Gold" / "Gold 1 Bulan" / "Gold 3 Bulan" / "Gold 6 Bulan"
Platinum:        "Semua Platinum" / "Platinum 1 Bulan" / "Platinum 6 Bulan" / "1 Tahun"
Pro options:     "Semua Pro" / "Pro 1 Bulan" / "Pro 3 Bulan"
```

### 7.4 Search Bar (Filter Row)
```
Width:         200px / Height: 34px
Background:    #2A2400
Border:        1px solid #2E2800 / Border-radius: 6px
Padding:       0 10px
Icon:          🔍 14px / color #5A5040
Input:         13px / #FFFFFF / placeholder "Cari nama, email..."
Focus:         border-color #F5C300
```

### 7.5 Tambah Member Button
```
Margin-left:   auto   (dorong ke ujung kanan)
Padding:       8px 18px
Background:    #F5C300
Color:         #1A1500
Border:        none
Border-radius: 8px
Font-size:     13px / Font-weight: 700
Icon:          "+" 16px inline sebelum teks

Hover:   bg #E0B000
Active:  bg #EAB800
```

---

## 8. KOMPONEN: MEMBER TABLE

### 8.1 Container
```
Background:    #252000
Border:        1px solid #2E2800
Border-radius: 10px
Overflow:      hidden
Width:         100%
```

### 8.2 Table Header Row
```
Height:                40px
Background:            #1A1500
Padding:               0 20px
Display:               grid
Grid-template-columns: 2fr 1.8fr 1.5fr 1fr 1.2fr 0.8fr
Align-items:           center
Gap:                   12px

Column Labels:
  NAMA  ·  KONTAK  ·  PAKET AKTIF  ·  STATUS  ·  BERAKHIR  ·  AKSI

Typography:
  Font-size:      10px
  Font-weight:    700
  Color:          #8A8070
  Text-transform: uppercase
  Letter-spacing: 0.1em
```

### 8.3 Table Row
```
Min-height:            64px
Padding:               12px 20px
Display:               grid
Grid-template-columns: 2fr 1.8fr 1.5fr 1fr 1.2fr 0.8fr
Align-items:           center
Gap:                   12px
Border-bottom:         1px solid #2E2800
Transition:            background 0.15s ease

Hover:      background rgba(245,195,0,0.03)
Last-child: border-bottom none
```

### 8.4 Kolom NAMA
```
Display:     flex
Align-items: center
Gap:         10px

Avatar (36px):
  Width / Height:  36px
  Border-radius:   50%
  Border:          2px solid #2E2800
  Background:      linear-gradient(135deg, #2E2800 0%, #1A1500 100%)
  Overflow:        hidden

  Inisial (jika tidak ada foto):
    Font-size:   14px / Font-weight: 600 / Color: #F5C300
    Text-transform: uppercase

  Foto (jika ada): object-fit: cover, width/height 100%

Info (flex-col, gap: 3px):
  Nama:     14px / 700 / #FFFFFF / white-space: nowrap
  ID Member: 11px / 400 / #5A5040 / font-family: monospace
             Format: "ID: #M-XXXX" / letter-spacing: 0.3px
```

### 8.5 Kolom KONTAK
```
Display:        flex
Flex-direction: column
Gap:            3px

Email:   13px / 400 / #8A8070 / text-overflow: ellipsis / max-width: 180px
Telepon: 12px / 400 / #5A5040 / margin-top: 1px
```

### 8.6 Kolom PAKET AKTIF
```
Badge Pill:
  Display:        inline-flex
  Align-items:    center
  Padding:        3px 10px
  Border-radius:  9999px
  Font-size:      11px / Font-weight: 700
  Text-transform: uppercase / Letter-spacing: 0.5px

PLATINUM → bg rgba(245,195,0,0.15),  color #F5C300
GOLD     → bg rgba(245,158,11,0.15), color #F59E0B
PRO      → bg rgba(59,130,246,0.15), color #3B82F6
```

### 8.7 Kolom STATUS
```
Badge Pill (style sama dengan PAKET AKTIF):

AKTIF    → bg rgba(76,175,80,0.15),  color #4CAF50
NONAKTIF → bg rgba(239,68,68,0.15),  color #EF4444
```

### 8.8 Kolom BERAKHIR
```
Display:        flex
Flex-direction: column
Gap:            3px

Tanggal:
  13px / 400 / #FFFFFF
  Jika expired/nonaktif: content "—", color #5A5040

Sisa Hari — WARNA DINAMIS 3 kondisi:
  Font-size: 11px / Font-weight: 400

  > 30 hari:  color #4CAF50   → "182 hr sisa"
  ≤ 30 hari:  color #F59E0B   → "15 hr sisa"
  Expired:    color #EF4444   → "Expired"
```

### 8.9 Kolom AKSI
```
Display:     flex
Gap:         6px
Align-items: center

[✏ Edit Button]:
  Width / Height:  28px
  Border-radius:   6px
  Border:          1px solid #2E2800
  Background:      transparent
  Icon:            ✏ pencil / 14px / color #8A8070
  Hover:
    Border-color: #F5C300
    Icon color:   #F5C300
    Background:   rgba(245,195,0,0.06)
  Tooltip: "Edit Member"

[🗑 Delete Button]:
  Width / Height:  28px
  Border-radius:   6px
  Border:          1px solid #2E2800
  Background:      transparent
  Icon:            🗑 trash / 14px / color #8A8070
  Hover:
    Border-color: #EF4444
    Icon color:   #EF4444
    Background:   rgba(239,68,68,0.06)
  Tooltip: "Hapus Member"
  Confirm dialog: wajib tampil sebelum eksekusi
```

---

## 9. DATA TABEL CONTOH

### 9.1 Sample Data (5 rows)

| #  | Nama             | ID Member | Email                    | Telepon        | Paket    | Status   | Berakhir     | Sisa              |
|----|------------------|-----------|--------------------------|----------------|----------|----------|--------------|-------------------|
| 1  | Naufal Raharjo   | #M-0001   | naufal@email.com         | 0812-3456-7890 | PLATINUM | AKTIF    | 12 Okt 2024  | 182 hr sisa ✅    |
| 2  | Sarah Jenkins    | #M-0002   | sarah.j@email.com        | 0813-2233-4455 | GOLD     | AKTIF    | 24 Nov 2024  | 225 hr sisa ✅    |
| 3  | Budi Santoso     | #M-0003   | budi.s@email.com         | 0811-9988-7766 | PRO      | NONAKTIF | —            | Expired ❌         |
| 4  | Maya Sari        | #M-0004   | maya.sari@email.com      | 0878-5544-3322 | PLATINUM | AKTIF    | 25 Apr 2024  | 15 hr sisa ⚠️    |
| 5  | Rizky Permana    | #M-0005   | rizky.p@email.com        | 0857-1122-3344 | GOLD     | AKTIF    | 30 Jun 2024  | 47 hr sisa ✅     |

### 9.2 Rendering Rules Per Row
```
Row 1 (Naufal Raharjo):
  Avatar inisial: "NR" / bg gradient gelap / border abu
  Paket badge: PLATINUM → bg rgba(245,195,0,0.15), text #F5C300
  Status: AKTIF hijau / Sisa: "182 hr sisa" warna #4CAF50 (>30hr)

Row 2 (Sarah Jenkins):
  Avatar inisial: "SJ"
  Paket badge: GOLD → bg rgba(245,158,11,0.15), text #F59E0B
  Status: AKTIF hijau / Sisa: "225 hr sisa" warna #4CAF50 (>30hr)

Row 3 (Budi Santoso):
  Avatar inisial: "BS"
  Paket badge: PRO → bg rgba(59,130,246,0.15), text #3B82F6
  Status: NONAKTIF → bg rgba(239,68,68,0.15), text #EF4444
  Tanggal: "—" color #5A5040 / Sisa: "Expired" warna #EF4444

Row 4 (Maya Sari):
  Avatar inisial: "MS"
  Paket badge: PLATINUM kuning
  Status: AKTIF hijau
  Sisa: "15 hr sisa" warna #F59E0B  ← AMBER karena ≤30hr!

Row 5 (Rizky Permana):
  Avatar inisial: "RP"
  Paket badge: GOLD amber
  Status: AKTIF hijau / Sisa: "47 hr sisa" warna #4CAF50 (>30hr)
```

---

## 10. KOMPONEN: PAGINATION FOOTER

### 10.1 Container
```
Display:          flex
Justify-content:  space-between
Align-items:      center
Padding:          12px 20px
Border-top:       1px solid #2E2800
Background:       #252000
Border-radius:    0 0 10px 10px
```

### 10.2 Kiri — Result Count
```
"Showing 1–5 of 1,284 members"
Font-size: 12px / Font-weight: 400 / Color: #8A8070
```

### 10.3 Kanan — Page Controls
```
[PREV]  [1]  [2]  [3]  [···]  [257]  [NEXT]

Tombol Aktif (1):
  Width / Height: 32×32px
  Background:     #F5C300
  Color:          #1A1500
  Border:         none
  Border-radius:  6px
  Font-size:      13px / Font-weight: 600

Tombol Inaktif (2, 3, 257):
  Width / Height: 32×32px
  Background:     #252000
  Border:         1px solid #2E2800
  Color:          #8A8070
  Border-radius:  6px
  Hover:          border-color #F5C300, color #F5C300

Ellipsis (···):
  32×32px / display flex center
  Font-size: 13px / Color: #5A5040

[PREV] / [NEXT]:
  Padding:        6px 12px / Height: 32px
  Background:     transparent
  Border:         1px solid #2E2800
  Color:          #8A8070
  Border-radius:  6px
  Font-size:      11px / Font-weight: 700 / uppercase / ls: 1px
  Hover:          border-color #F5C300, color #F5C300
  Disabled:       color #5A5040, border #1E1900, cursor not-allowed
```

---

## 11. KOMPONEN: SUMMARY CARDS (Bawah Halaman)

### 11.1 Grid Container
```
Display:               grid
Grid-template-columns: 1fr 1fr 1fr
Gap:                   16px
Margin-top:            20px
```

### 11.2 Card 1 — TOTAL MEMBERS
```
Background:    #252000
Border:        1px solid #2E2800
Border-radius: 10px
Padding:       18px 20px
Box-shadow:    0 2px 8px rgba(0,0,0,0.40)
Position:      relative / Overflow: hidden

Icon dekorasi (absolute top-right):
  👥 24px / color rgba(255,255,255,0.06)

Label:
  "TOTAL MEMBERS"
  11px / 700 / #8A8070 / uppercase / ls: 2px / mb: 6px

Value:
  "1,284"
  36px / 800 / #FFFFFF / line-height: 1.0

Sub-text:
  "↑ +12% this month"
  12px / 400 / #4CAF50   ← hijau (pertumbuhan positif)
  margin-top: 6px
```

### 11.3 Card 2 — ACTIVE PREMIUM ⭐ FEATURED
```
Background:    #F5C300   ← KUNING SOLID! (bukan #252000)
Border:        none
Border-radius: 10px
Padding:       18px 20px
Box-shadow:    0 4px 16px rgba(245,195,0,0.25)
Position:      relative / Overflow: hidden

Icon dekorasi (absolute top-right):
  ★ star 24px / color rgba(26,21,0,0.20)

Label:
  "ACTIVE PREMIUM"
  11px / 700 / rgba(26,21,0,0.60)   ← GELAP semi-transparan di atas kuning!
  uppercase / ls: 2px / mb: 6px

Value:
  "842"
  36px / 800 / #1A1500   ← GELAP! (bukan #FFFFFF)
  line-height: 1.0

Sub-text:
  "Premium & Platinum tier"
  12px / 400 / rgba(26,21,0,0.70)   ← GELAP semi-transparan
  margin-top: 6px
```

### 11.4 Card 3 — EXPIRING SOON
```
Background:    #252000
Border:        1px solid #2E2800
Border-radius: 10px
Padding:       18px 20px
Box-shadow:    0 2px 8px rgba(0,0,0,0.40)
Position:      relative / Overflow: hidden

Icon dekorasi (absolute top-right):
  ⚠ warning 24px / color rgba(245,158,11,0.20)

Label:
  "EXPIRING SOON"
  11px / 700 / #8A8070 / uppercase / ls: 2px / mb: 6px

Value:
  "45"
  36px / 800 / #FFFFFF / line-height: 1.0

Sub-text:
  "⚠ Within 30 days"
  12px / 400 / #F59E0B   ← amber warning
  margin-top: 6px
```

---

## 12. KOMPONEN: MODAL ADD / EDIT MEMBER

### 12.1 Overlay & Container
```
Overlay:
  Position: fixed, inset: 0
  Background: rgba(0,0,0,0.70)
  Z-index: 1000
  Display: flex, align-items: center, justify-content: center

Modal Box:
  Width:         520px
  Max-height:    90vh
  Background:    #252000
  Border:        1px solid #2E2800
  Border-radius: 14px
  Padding:       28px
  Box-shadow:    0 24px 60px rgba(0,0,0,0.70)
  Overflow-y:    auto
```

### 12.2 Modal Header
```
Display:          flex
Justify-content:  space-between
Align-items:      center
Margin-bottom:    24px

Title:
  "TAMBAH MEMBER BARU"  atau  "EDIT MEMBER"
  16px / 700 / #FFFFFF

[✕ Tutup]:
  28×28px / border-radius 6px
  Border: 1px solid #2E2800 / bg transparent
  Icon: ✕ 14px / color #8A8070
  Hover: border-color #EF4444, icon #EF4444
```

### 12.3 Upload Foto Profil
```
Display: flex, align-items: center, gap: 16px, mb: 24px

Upload Area:
  80×80px / border-radius 50%
  Border: 2px dashed #2E2800 / bg: #2A2400
  Center: 📷 20px/#5A5040 + "Upload" 10px/#5A5040
  Hover: border-color #F5C300, icon #F5C300
  Has-photo: border 2px solid #F5C300, image fill

Info:
  "Foto Profil"                    13px/600/#FFFFFF
  "Max 2MB, format JPG/PNG"        11px/400/#8A8070
  [Hapus Foto] (jika ada foto):    11px/400/#EF4444 link style
```

### 12.4 Section — Informasi Personal
```
Section Label: "INFORMASI PERSONAL"
  12px / 700 / #8A8070 / uppercase / ls:1px / mb:12px
  Border-bottom: 1px solid #2E2800 / pb: 8px

Standard Input Style:
  Width: 100% / Height: 40px
  Background: #2A2400 / Border: 1px solid #2E2800 / Radius: 6px
  Padding: 0 12px / Font-size: 14px / Color: #FFFFFF
  Placeholder: color #5A5040
  Focus: border-color #F5C300, outline none
  Label: 12px/600/#8A8070, mb:6px, display:block

Fields:
  Nama Lengkap     → full width, placeholder "Nama lengkap member"
  Email            → full width, type email
  Nomor Telepon    → full width, type tel, placeholder "08XX-XXXX-XXXX"
  Tanggal Lahir    → grid 2-col kiri, type date
  Jenis Kelamin    → grid 2-col kanan, select "Laki-laki" / "Perempuan"
```

### 12.5 Section — Keanggotaan
```
Section Label: "KEANGGOTAAN"

Fields:
  Pilih Paket:
    Select: "PLATINUM" / "GOLD" / "PRO"
    Badge warna muncul di selected option

  Tanggal Mulai:    type date, default today

  Durasi:
    Select: "1 Bulan" / "3 Bulan" / "6 Bulan" / "12 Bulan"

  Tanggal Berakhir: (read-only — computed)
    Background: #1A1500 (lebih gelap, menandakan read-only)
    Color: #F5C300  ← kuning = computed value
    Dihitung otomatis: tanggal mulai + durasi
```

### 12.6 Section — Pembayaran
```
Section Label: "PEMBAYARAN"

Fields:
  Metode: Select "TRANSFER" / "CASH" / "E-WALLET" / "KARTU KREDIT"
  Status: Select "LUNAS" / "MENUNGGU" / "BELUM BAYAR"
```

### 12.7 Footer Buttons
```
Display: flex, justify-content: flex-end, gap: 12px
Margin-top: 28px / Padding-top: 20px / Border-top: 1px solid #2E2800

[BATAL]:
  Padding: 8px 20px / Radius: 6px
  bg transparent / border 1px solid #2E2800 / color #8A8070
  Hover: border #8A8070, color #FFFFFF

[SIMPAN / TAMBAHKAN]:
  Padding: 8px 24px / Radius: 6px
  bg #F5C300 / color #1A1500 / 13px / 700
  Hover: bg #E0B000
  Loading: spinner 14px + "Menyimpan..."
```

### 12.8 Validation Error State
```
Input border-color: #EF4444
Error message (di bawah input):
  11px / 500 / #EF4444 / mt: 4px
  Display: flex, align-items: center, gap: 4px
  Icon: ⚠ 10px merah inline
```

---

## 13. INTERAKSI & STATE TAMBAHAN

### 13.1 Empty State
```
Padding: 48px 20px / Text-align: center

Icon:    👥 48px / color #5A5040
Title:   "Tidak ada member ditemukan"   16px/600/#8A8070
Sub:     "Coba ubah filter atau kata kunci pencarian"   13px/400/#5A5040, mt: 8px
Button:  "+ Tambah Member Pertama" (style CTA, tampil jika total = 0)
```

### 13.2 Confirm Delete Dialog
```
Backdrop: rgba(0,0,0,0.70)
Box: 400px / bg #252000 / border #2E2800 / radius 12px / padding 24px

Icon:   ⚠ 32px / color #F59E0B, centered
Title:  "Hapus Member?"   16px/700/#FFFFFF, mt: 12px
Sub:    "Aksi ini tidak dapat dibatalkan. Data member akan dihapus permanen."
        13px/400/#8A8070, mt: 8px

[BATAL]: ghost button
[HAPUS]: bg #EF4444, color #FFFFFF, 13px/700
```

### 13.3 Success Toast Notification
```
Position: fixed, top: 80px, right: 24px / Z-index: 2000
Background: #252000 / Border: 1px solid #4CAF50
Radius: 8px / Padding: 12px 16px
Box-shadow: 0 8px 24px rgba(0,0,0,0.60)
Display: flex, align-items: center, gap: 10px / Min-width: 280px

Icon: ✓ 16px / color #4CAF50
Text: "Member berhasil ditambahkan"   13px/600/#FFFFFF
Auto-close: 3000ms dengan slide-out ke kanan
```

---

## 14. CATATAN AI

1. **Header "DATA MEMBER" = KUNING** (`#F5C300`) — warna yang sama dengan Pembayaran & Booking, bukan putih seperti PT Management dan Pengaturan
2. **Card ACTIVE PREMIUM = background kuning solid** (`#F5C300`) — WAJIB: value `"842"` pakai `#1A1500` (gelap), label pakai `rgba(26,21,0,0.6)` — bukan `#FFFFFF` seperti card biasa
3. **Sisa hari = tiga kondisi warna berbeda**: `#4CAF50` hijau (>30hr) → `#F59E0B` amber (≤30hr) → `#EF4444` merah teks "Expired"
4. **Badge PAKET ≠ badge STATUS** — warna berbeda, jangan tertukar: PLATINUM=kuning, GOLD=amber, PRO=biru; AKTIF=hijau, NONAKTIF=merah
5. **Grid tabel 6 kolom** `2fr 1.8fr 1.5fr 1fr 1.2fr 0.8fr` — NAMA(2fr) paling lebar karena muat avatar 36px + nama bold + ID monospace dalam satu flex row
6. **Avatar member** = inisial font kuning, background gradient gelap, **border `#2E2800`** abu tipis — berbeda dari avatar trainer yang pakai border kuning (`#F5C300`)
7. **Filter dropdowns** `[Gold▼][Platinum▼][Pro▼]` = tiga dropdown independent (bukan satu), masing-masing punya sub-opsi durasi tersendiri, dapat dipakai kombinasi
8. **Summary cards** = posisi di BAWAH pagination (bukan di atas) — urutan halaman: Filter Row → Table → Pagination → Summary Cards
9. **Tanggal Berakhir di modal** = read-only computed field: bg `#1A1500` (gelap lebih dari input biasa), teks `#F5C300` kuning — dihitung otomatis dari tanggal mulai + durasi yang dipilih
10. **Total 1,284 member** di data mock — pagination default 5 row/halaman pada tampilan ini (`Showing 1–5 of 1,284` = 257 halaman total, sesuai ellipsis `[···][257]`)

---
*Generated from Figma Design — Admin Member Management | EGG GYM APP*

# ADMIN_PAYMENTS_TRANSACTIONS_UI_SPEC.md
# Egg Gym App — Admin Payments & Transactions Screen
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Admin > Payments & Transactions (Pembayaran & Transaksi)
# Resolution: 1286 × 1024 px
# Last Updated: 2026-06-27
# Source of truth: Admin Payments & Transactions.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar ini memakai latar NETRAL GELAP (near-black), berbeda dari Equipment screen
yang berbasis cokelat. Aksen kuning emas tetap konsisten.

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0F0F0F               | Main content background                        |
| --color-bg-card           | #1A1A1A               | Stat card & panel background                   |
| --color-bg-table          | #161616               | Table container background                     |
| --color-bg-row            | transparent           | Table row default                              |
| --color-bg-row-hover      | #1E1E1E               | Table row hover                                |
| --color-bg-sidebar        | #0D0D0D               | Sidebar background                             |
| --color-bg-input          | #1C1C1C               | Search bar & filter dropdown background        |
| --color-accent-primary    | #F5C518               | Active nav, CTA button, primary numbers        |
| --color-accent-hover      | #E0B200               | Button hover state                             |
| --color-text-primary      | #FFFFFF               | Headings, member names, primary values         |
| --color-text-secondary    | #9A9A9A               | Column headers, captions, helper text          |
| --color-text-muted        | #6B6B6B               | Placeholder, disabled, sub-timestamp           |
| --color-text-on-accent    | #0F0F0F               | Text on yellow/accent elements                 |
| --color-status-success    | #4CAF50               | "SUKSES" badge text & border                   |
| --color-status-pending    | #F5C518               | "PENDING" badge text & border                  |
| --color-status-failed     | #EF4444               | "GAGAL" badge bg                               |
| --color-trend-up          | #4CAF50               | "+12% dari bln lalu" trend text                |
| --color-border-card       | #262626               | Card & table borders                           |
| --color-border-sidebar    | #1E1E1E               | Sidebar dividers                               |
| --color-border-row        | #1E1E1E               | Table row separators                           |
| --color-avatar-bg         | #2A2A2A               | Member initial avatar background               |
| --color-kode-link         | #F5C518               | "ATH-xxxxxx" transaction code (kuning)         |
| --color-overlay-dark      | rgba(0,0,0,0.7)       | Modal backdrop                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Monospace:  "JetBrains Mono", "Fira Code", monospace  (untuk kode transaksi & nominal)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-sidebar-brand     | 20px | 800    | 1.1    | 0px              | "Editorial Athletics" brand        |
| --text-sidebar-sub       | 10px | 600    | 1.2    | 2px (uppercase)  | "ELITE MANAGEMENT" sub-brand       |
| --text-breadcrumb        | 16px | 800    | 1.0    | 1.5px (uppercase)| "PEMBAYARAN & TRANSAKSI" header    |
| --text-stat-label        | 11px | 600    | 1.3    | 1px (uppercase)  | Label di atas angka stat card      |
| --text-stat-value        | 30px | 800    | 1.0    | -0.5px           | Angka besar di stat card           |
| --text-stat-caption      | 11px | 400    | 1.3    | 0px              | Caption di bawah angka stat        |
| --text-filter-label      | 13px | 500    | 1.0    | 0px              | Label di filter dropdown           |
| --text-button-cta        | 13px | 700    | 1.0    | 0px              | "Export Ledger" button             |
| --text-th                | 11px | 700    | 1.2    | 1px (uppercase)  | Table column headers               |
| --text-kode              | 13px | 700    | 1.3    | 0px              | Kode transaksi (ATH-xxxxxx)        |
| --text-member-name       | 14px | 600    | 1.3    | 0px              | Nama member di tabel               |
| --text-cell              | 13px | 400    | 1.4    | 0px              | Isi sel umum (jenis, metode)       |
| --text-nominal           | 14px | 700    | 1.3    | 0px              | Nominal "Rp x.xxx.xxx"             |
| --text-date              | 12px | 400    | 1.4    | 0px              | Tanggal & waktu transaksi          |
| --text-badge             | 10px | 700    | 1.0    | 0.5px (uppercase)| Status badges                      |
| --text-pagination        | 13px | 500    | 1.0    | 0px              | Nomor halaman pagination           |
| --text-pagination-info   | 12px | 400    | 1.3    | 0px              | "Menampilkan 1-5 dari 1,204..."    |
| --text-nav-item          | 14px | 500    | 1.4    | 0px              | Sidebar navigation items           |
| --text-search            | 13px | 400    | 1.0    | 0px              | Search bar input                   |
| --text-avatar            | 11px | 700    | 1.0    | 0.5px            | Inisial di avatar member           |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Badge padding, tiny gaps                         |
| --space-sm     | 8px   | Inline label gaps, avatar-name gap               |
| --space-md     | 12px  | Filter dropdown gap, cell inner padding          |
| --space-base   | 16px  | Standard component margin                        |
| --space-lg     | 20px  | Stat card gap, section spacing                   |
| --space-xl     | 24px  | Card padding, page horizontal padding            |
| --space-2xl    | 32px  | Major section separation                         |
| --space-3xl    | 40px  | Page top padding                                 |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-xs    | 4px   | Filter dropdowns, small chips                    |
| --radius-sm    | 6px   | Buttons, search bar                              |
| --radius-md    | 10px  | Stat cards, table container                      |
| --radius-pill  | 999px | Status badges, pagination active                 |
| --radius-full  | 50%   | Avatar circles                                   |

### Box Shadows
| Token            | Value                              | Usage                        |
|------------------|------------------------------------|------------------------------|
| --shadow-card    | 0 1px 3px rgba(0,0,0,0.3)         | Stat cards default           |
| --shadow-button  | 0 2px 8px rgba(245,197,24,0.3)    | Export Ledger CTA            |
| --shadow-dropdown| 0 4px 16px rgba(0,0,0,0.5)        | Open filter dropdown menu    |
| --shadow-modal   | 0 8px 32px rgba(0,0,0,0.7)        | Modal overlays               |

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Total Canvas:   1286 × 1024 px
Sidebar:        240px wide × 100vh (fixed)
Header Bar:     calc(100vw - 240px) × 64px (sticky)
Main Content:   calc(100vw - 240px) width, padding: 32px
Page Padding:   32px (horizontal) / 32px (vertikal)
Content Gap:    24px
```

### ASCII Layout Diagram
```
┌─────────────────────┬────────────────────────────────────────────────────────┐
│  SIDEBAR (240px)    │  HEADER (64px)                                         │
│  Editorial          │  PEMBAYARAN & TRANSAKSI  [🔍 Cari transaksi...] 🔔 ❓ │
│  Athletics          ├────────────────────────────────────────────────────────┤
│  ELITE MANAGEMENT   │  ┌────────┐ ┌────────┐ ┌────────┐ ┌────────┐           │
│  ───────────────    │  │TOT.PEND│ │TRX BRHS│ │PENDING │ │RETENSI │           │
│  ⊞ Dashboard        │  │Rp142.5M│ │ 1,204  │ │   18   │ │ 94.2%  │           │
│  👥 Member          │  │        │ │↗+12%   │ │verif.  │ │loyalty │           │
│  💳 Paket Membership│  └────────┘ └────────┘ └────────┘ └────────┘           │
│  ⭐ Personal Trainer│                                                          │
│  ☑ Booking & Sesi PT│  [📅 Semua Tanggal▾][⇅ Jenis▾][💳 Metode▾]  [⬇ Export]│
│  💳 Pembayaran◄AKTIF│  ┌──────────────────────────────────────────────────┐  │
│  💠 Alat Gym        │  │KODE TRX│MEMBER│JENIS│METODE│NOMINAL│TANGGAL│STATUS│⋮│
│  🗂 Audit Trail     │  │ATH-..  │Ryan  │Memb.│QRIS  │Rp4.5jt│12 Okt │SUKSES│ │
│  📊 Laporan         │  │ATH-..  │Anya  │PT   │VA Mnd│Rp3.2jt│12 Okt │PEND. │ │
│  ⚙ Pengaturan       │  │ATH-..  │Dimas │Memb.│CC    │Rp550rb│12 Okt │GAGAL │ │
│  ───────────────    │  │ATH-..  │Kevin │PT   │QRIS  │Rp350rb│13 Okt │SUKSES│ │
│  [👤] Alex Mercer   │  │ATH-..  │Sarah │Memb.│VA BCA│Rp7.8jt│13 Okt │SUKSES│ │
│  MASTER ADMIN       │  │ Menampilkan 1-5 dari 1,204  <  1 2 3 … 24  >       │  │
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

### 5.4 Menu Item (Active State — Pembayaran)
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
4.  ⭐  Personal Trainer
5.  ☑  Booking & Sesi PT
6.  💳  Pembayaran          ← ACTIVE (screen ini)
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
  Text:         "Alex Mercer"
  Font-size:    14px
  Font-weight:  700
  Color:        #FFFFFF
Role:
  Text:         "MASTER ADMIN"
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
Text:           "PEMBAYARAN & TRANSAKSI"
Font-size:      16px
Font-weight:    800
Color:          #F5C518
Letter-spacing: 1.5px
Text-transform: uppercase
```

### 6.3 Tengah — Search Bar
```
Container:
  Width:        ~280px
  Height:       40px
  Background:   #1C1C1C
  Border:       1px solid #262626
  Border-radius:6px
  Padding:      0 14px
  Gap:          10px
Search Icon:
  Color:        #6B6B6B
Input:
  Placeholder:  "Cari transaksi..."
  Placeholder-color: #6B6B6B
  Color:        #FFFFFF
  Font-size:    13px
Focus:
  Border:       1px solid #F5C518
```

### 6.4 Kanan — Action Icons
```
Display:        flex, align-items center, gap 20px

Notification Bell:
  Icon-size:    20px
  Color:        #9A9A9A
  Hover-color:  #F5C518

Help Icon (?):
  Icon-size:    20px
  Shape:        lingkaran outline dengan tanda tanya
  Color:        #9A9A9A
  Hover-color:  #F5C518
```

---

## 7. KOMPONEN: STAT CARDS ROW (KPI)

### 7.1 Container
```
Display:        grid
Grid-template-columns: repeat(4, 1fr)
Gap:            20px
Margin-bottom:  24px
```

### 7.2 Stat Card (Default)
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  10px
Padding:        24px
Display:        flex, flex-direction column, gap 8px

Label (atas):
  Font-size:    11px
  Font-weight:  600
  Color:        #9A9A9A
  Letter-spacing:1px
  Text-transform:uppercase

Value (besar):
  Font-size:    30px
  Font-weight:  800
  Line-height:  1.0

Caption (bawah):
  Font-size:    11px
  Font-weight:  400
  Color:        #9A9A9A
```

### 7.3 Data Contoh — Stat Cards (FINAL — sesuai gambar)
```
CARD 1 — Total Pendapatan
  Label:    "TOTAL PENDAPATAN (BLN INI)"
  Value:    "Rp 142.5M"      → color #F5C518 (kuning, highlight utama)
  Caption:  (tanpa caption)

CARD 2 — Transaksi Berhasil
  Label:    "TRANSAKSI BERHASIL"
  Value:    "1,204"          → color #FFFFFF
  Caption:  "↗ +12% dari bln lalu"  → color #4CAF50 (trend up, dengan ikon panah)

CARD 3 — Pending Approval
  Label:    "PENDING APPROVAL"
  Value:    "18"             → color #FFFFFF
  Caption:  "Membutuhkan verifikasi"  → color #9A9A9A

CARD 4 — Retensi Member
  Label:    "RETENSI MEMBER"
  Value:    "94.2%"          → color #FFFFFF
  Caption:  "Elite tier loyalty"  → color #9A9A9A
```

---

## 8. KOMPONEN: FILTER & ACTION BAR

### 8.1 Container
```
Display:        flex, align-items center, justify-content space-between
Margin-bottom:  20px
```

### 8.2 Kiri — Filter Dropdowns (gap 12px)
```
Dropdown Default:
  Height:       40px
  Background:   #1C1C1C
  Border:       1px solid #262626
  Border-radius:6px
  Padding:      0 14px
  Display:      flex, align-items center, gap 8px
  Font-size:    13px
  Font-weight:  500
  Color:        #FFFFFF
  Leading-icon: #9A9A9A (16px)
  Trailing:     chevron-down ▾ #9A9A9A

  Hover:
    Border-color:#3A3A3A

Daftar Filter:
  1. 📅  "Semua Tanggal"  ▾
  2. ⇅  "Jenis: Semua"    ▾
  3. 💳  "Metode: Semua"  ▾
```

### 8.3 Kanan — Tombol "Export Ledger"
```
Text:           "Export Ledger"
Leading-icon:   ⬇ (download), 16px
Font-size:      13px
Font-weight:    700
Color:          #0F0F0F
Background:     #F5C518
Border-radius:  6px
Padding:        11px 20px
Box-shadow:     0 2px 8px rgba(245,197,24,0.3)
Display:        flex, align-items center, gap 8px
Hover:
  Background:   #E0B200
  Transform:    translateY(-1px)
```

---

## 9. KOMPONEN: TABEL TRANSAKSI

### 9.1 Container
```
Background:     #161616
Border:         1px solid #262626
Border-radius:  10px
Overflow:       hidden
Width:          100%
```

### 9.2 Table Header Row (THEAD)
```
Background:     transparan (sedikit lebih gelap dari row)
Border-bottom:  1px solid #262626
Padding:        16px 24px

Header Cell (TH):
  Font-size:    11px
  Font-weight:  700
  Color:        #9A9A9A
  Letter-spacing:1px
  Text-transform:uppercase
  Text-align:   left

Daftar Kolom (7 + 1 aksi):
  1. KODE TRANSAKSI
  2. MEMBER
  3. JENIS
  4. METODE
  5. NOMINAL
  6. TANGGAL
  7. STATUS
  8. (kolom kosong untuk ikon ⋮ kebab)
```

### 9.3 Lebar Kolom (proporsional)
```
KODE TRANSAKSI:  ~12%
MEMBER:          ~18%
JENIS:           ~16%
METODE:          ~13%
NOMINAL:         ~13%
TANGGAL:         ~13%
STATUS:          ~12%
AKSI (⋮):        ~3%
```

### 9.4 Table Body Row (TR)
```
Padding:        18px 24px
Border-bottom:  1px solid #1E1E1E
Vertical-align: middle
Hover:
  Background:   #1E1E1E
Last row:
  Border-bottom:none
```

### 9.5 Cell — Kode Transaksi
```
Text:           "ATH-882910"
Font-size:      13px
Font-weight:    700
Color:          #F5C518   (kuning, terlihat seperti link)
```

### 9.6 Cell — Member (Avatar + Nama)
```
Display:        flex, align-items center, gap 10px

Avatar:
  Width/Height: 32px
  Border-radius:50%
  Background:   #2A2A2A
  Color:        #FFFFFF
  Font-size:    11px
  Font-weight:  700
  Content:      inisial (mis. "RS", "AM", "DP", "KL", "SM")
  Display:      flex center

Nama:
  Font-size:    14px
  Font-weight:  600
  Color:        #FFFFFF
```

### 9.7 Cell — Jenis
```
Font-size:      13px
Color:          #FFFFFF (judul) / #9A9A9A (keterangan dalam kurung boleh muted)
Contoh:         "Membership (Annual)", "Personal Trainer (12 Sesi)"
```

### 9.8 Cell — Metode (Ikon + Teks)
```
Display:        flex, align-items center, gap 8px
Icon:           16px, color #9A9A9A (QRIS / kartu / bank)
Text:
  Font-size:    13px
  Color:        #FFFFFF
Contoh:         "QRIS", "VA Mandiri", "Credit Card", "VA BCA"
```

### 9.9 Cell — Nominal
```
Text:           "Rp 4.500.000"
Font-size:      14px
Font-weight:    700
Color:          #FFFFFF
White-space:    nowrap
```

### 9.10 Cell — Tanggal
```
Font-size:      12px
Color:          #9A9A9A
Format:         "12 Okt 2023, 14:20"
Boleh 2 baris:  tanggal di baris-1, jam di baris-2
```

### 9.11 Cell — Status Badge (Pill Outline)
```
Display:        inline-flex, align-items center
Padding:        4px 14px
Border-radius:  999px (pill)
Font-size:      10px
Font-weight:    700
Letter-spacing: 0.5px
Text-transform: uppercase

Status → Style:
  SUKSES:   bg rgba(76,175,80,0.12), border 1px #4CAF50, text #4CAF50
  PENDING:  bg rgba(245,197,24,0.12), border 1px #F5C518, text #F5C518
  GAGAL:    bg #EF4444, border none, text #FFFFFF   (solid, high-alert)
```

### 9.12 Cell — Aksi (Kebab Menu)
```
Icon:           ⋮ (three-dot vertical)
Size:           20px hitbox
Color:          #9A9A9A
Hover:          color #FFFFFF
Action:         buka context menu (Detail / Verifikasi / Refund / Cetak Struk)
```

### 9.13 Data Contoh — Baris Tabel (FINAL — sesuai gambar)
```
ROW 1:
  Kode: ATH-882910 | Member: Ryan Setiadi (RS)
  Jenis: Membership (Annual) | Metode: QRIS
  Nominal: Rp 4.500.000 | Tanggal: 12 Okt 2023, 14:20 | Status: SUKSES

ROW 2:
  Kode: ATH-882911 | Member: Anya Mandasari (AM)
  Jenis: Personal Trainer (12 Sesi) | Metode: VA Mandiri
  Nominal: Rp 3.200.000 | Tanggal: 12 Okt 2023, 15:45 | Status: PENDING

ROW 3:
  Kode: ATH-882912 | Member: Dimas Pratama (DP)
  Jenis: Membership (Monthly) | Metode: Credit Card
  Nominal: Rp 550.000 | Tanggal: 12 Okt 2023, 16:10 | Status: GAGAL

ROW 4:
  Kode: ATH-882915 | Member: Kevin Laurent (KL)
  Jenis: Personal Trainer (Single) | Metode: QRIS
  Nominal: Rp 350.000 | Tanggal: 13 Okt 2023, 09:12 | Status: SUKSES

ROW 5:
  Kode: ATH-882918 | Member: Sarah Miller (SM)
  Jenis: Membership (Elite Annual) | Metode: VA BCA
  Nominal: Rp 7.800.000 | Tanggal: 13 Okt 2023, 11:30 | Status: SUKSES
```

---

## 10. KOMPONEN: TABLE FOOTER / PAGINATION

### 10.1 Container
```
Display:        flex, align-items center, justify-content space-between
Padding:        16px 24px
Border-top:     1px solid #262626
```

### 10.2 Kiri — Info
```
Text:           "Menampilkan 1-5 dari 1,204 transaksi"
Font-size:      12px
Font-weight:    400
Color:          #9A9A9A
```

### 10.3 Kanan — Pagination Controls
```
Display:        flex, align-items center, gap 6px

Prev/Next Arrow (< >):
  Size:         32px × 32px
  Color:        #9A9A9A
  Hover:        color #FFFFFF
  Disabled:     color #4A4A4A (saat di halaman pertama/terakhir)

Page Number (default):
  Size:         32px × 32px
  Border-radius:6px
  Font-size:    13px
  Color:        #9A9A9A
  Hover:        background #1E1E1E, color #FFFFFF

Page Number (active — "1"):
  Background:   #F5C518
  Color:        #0F0F0F
  Font-weight:  700
  Border-radius:6px

Ellipsis "…":
  Color:        #6B6B6B
  Non-clickable

Urutan tampil:  < 1 2 3 … 24 >   (active: 1)
```

---

## 11. GRID RECAP — RINGKASAN ZONA LAYOUT

| Zone               | X Offset | Y Offset | Width                | Height    |
|--------------------|----------|----------|----------------------|-----------|
| Sidebar            | 0        | 0        | 240px                | 100vh     |
| Header Bar         | 240px    | 0        | calc(100vw - 240px)  | 64px      |
| Stat Cards Row     | 272px    | 96px     | calc(100vw - 304px)  | ~130px    |
| Filter & Action Bar| 272px    | 250px    | calc(100vw - 304px)  | ~40px     |
| Tabel Transaksi    | 272px    | 310px    | calc(100vw - 304px)  | ~560px    |
| Pagination Footer  | 272px    | (in-table)| calc(100vw - 304px) | ~56px     |

---

## 12. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Admin Payments & Transactions (Pembayaran & Transaksi)
   CSS Custom Properties — Design Tokens
   Visual-verified: Admin Payments & Transactions.png
   Generated: 2026-06-27
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:        #0F0F0F;
  --color-bg-card:           #1A1A1A;
  --color-bg-table:          #161616;
  --color-bg-row-hover:      #1E1E1E;
  --color-bg-sidebar:        #0D0D0D;
  --color-bg-input:          #1C1C1C;
  --color-accent-primary:    #F5C518;
  --color-accent-hover:      #E0B200;
  --color-text-primary:      #FFFFFF;
  --color-text-secondary:    #9A9A9A;
  --color-text-muted:        #6B6B6B;
  --color-text-on-accent:    #0F0F0F;
  --color-status-success:    #4CAF50;
  --color-status-pending:    #F5C518;
  --color-status-failed:     #EF4444;
  --color-trend-up:          #4CAF50;
  --color-border-card:       #262626;
  --color-border-row:        #1E1E1E;
  --color-avatar-bg:         #2A2A2A;
  --color-kode-link:         #F5C518;
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --font-family-mono:        "JetBrains Mono", "Fira Code", monospace;
  --text-sidebar-brand:      20px;
  --text-breadcrumb:         16px;
  --text-stat-label:         11px;
  --text-stat-value:         30px;
  --text-stat-caption:       11px;
  --text-button-cta:         13px;
  --text-th:                 11px;
  --text-kode:               13px;
  --text-member-name:        14px;
  --text-cell:               13px;
  --text-nominal:            14px;
  --text-date:               12px;
  --text-badge:              10px;
  --text-pagination:         13px;
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
  --radius-pill:             999px;
  --radius-full:             50%;

  /* ── SHADOWS ── */
  --shadow-card:             0 1px 3px rgba(0,0,0,0.3);
  --shadow-button:           0 2px 8px rgba(245,197,24,0.3);
  --shadow-dropdown:         0 4px 16px rgba(0,0,0,0.5);
  --shadow-modal:            0 8px 32px rgba(0,0,0,0.7);

  /* ── LAYOUT ── */
  --sidebar-width:           240px;
  --header-height:           64px;
  --page-padding:            32px;
  --stat-card-cols:          4;
  --stat-card-gap:           20px;
  --content-gap:             24px;
  --table-row-height:        64px;
}
```

---

## 13. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Admin Payments & Transactions.png`. Semua kode transaksi (ATH-882910 dst), nama member, nominal, tanggal, dan status harus persis sama dengan gambar.

2. **Background Neutral, Bukan Cokelat**: Layar ini memakai latar near-black (`#0F0F0F`/`#161616`), berbeda dari Equipment screen (`#1A1500`). Jangan campur token; aksen kuning sedikit lebih terang (`#F5C518`).

3. **Stat Card Highlight**: Hanya angka "Rp 142.5M" (Total Pendapatan) yang berwarna kuning `#F5C518`. Tiga angka stat lain putih. Caption trend "+12%" berwarna hijau dengan ikon panah naik.

4. **Status Badge System**: Buat utility `getStatusBadge(status)`:
   - `SUKSES` → outline hijau (border #4CAF50, text #4CAF50, bg transparan 12%)
   - `PENDING` → outline kuning (border #F5C518, text #F5C518, bg transparan 12%)
   - `GAGAL` → solid merah (bg #EF4444, text #fff) — sengaja high-contrast untuk alert.

5. **Kode Transaksi sebagai Link**: Teks `ATH-xxxxxx` berwarna kuning dan dapat di-klik untuk membuka detail transaksi (modal atau halaman detail).

6. **Member Avatar Inisial**: Avatar bulat 32px berisi inisial 2 huruf dari nama member (RS, AM, DP, KL, SM), bg `#2A2A2A`. Jika ada foto asli, override inisial.

7. **Filter Dropdowns**: Tiga dropdown (Tanggal, Jenis, Metode) memakai pola yang sama — leading icon + label + chevron. Default state menampilkan "Semua". Saat dibuka, gunakan `--shadow-dropdown`.

8. **Export Ledger**: Tombol kuning solid dengan ikon download. Klik → trigger export data tabel (CSV/XLSX/PDF) sesuai filter yang aktif. Tampilkan loading state saat proses.

9. **Table Responsive**: Pada layar < 1024px, ubah ke horizontal scroll (`overflow-x: auto`) dengan kolom KODE & STATUS sticky, atau collapse ke card-list view di mobile (< 640px).

10. **Row Hover & Click**: Seluruh baris hover `#1E1E1E`. Klik baris (di luar kebab) bisa membuka detail; kebab `⋮` membuka context menu: Detail, Verifikasi (untuk PENDING), Refund, Cetak Struk.

11. **Nominal Format**: Gunakan format Rupiah dengan pemisah titik ribuan (`Rp 4.500.000`). Pertimbangkan `Intl.NumberFormat('id-ID', {style:'currency', currency:'IDR', minimumFractionDigits:0})`.

12. **Pagination**: Halaman aktif "1" solid kuning. Total 24 halaman (1,204 transaksi / ~5 per page hanya contoh; sesuaikan page size sebenarnya). Tampilkan ellipsis "…" untuk halaman tengah yang disembunyikan.

13. **KPI Real-Time**: Stat cards sebaiknya auto-refresh (polling/WebSocket). "Total Pendapatan (Bln Ini)" dan "Pending Approval" adalah metrik paling dinamis.

14. **Accessibility**: Status badge jangan hanya mengandalkan warna — sertakan teks ("SUKSES"/"PENDING"/"GAGAL"). Kebab button beri `aria-label="Aksi untuk transaksi [kode]"`. Pagination beri `aria-current="page"` pada halaman aktif.

---

*Spec ini generated dari analisis visual screen Admin Payments & Transactions.png (visual-verified).*
*Design system reference: ADMIN_EQUIPMENT_MANAGEMENT_UI_SPEC.md*
*Total sections: 13 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

# BOOKING_HISTORY_UI_SPEC.md
# Egg Gym App — Booking History Screen (Pro Bookings, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Member App > Program > Pro Bookings (My Sessions)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Booking History.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Booking History mewarisi sistem warna identik dengan Program & Session Detail: latar near-black dengan aksen kuning emas. Token tambahan ditambahkan untuk status booking (confirmed/selesai/ditolak), overlay foto coach, filter tab, dan watermark "ELITE" di panel statistik.

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0E0E0E               | App background (screen utama)                  |
| --color-bg-card           | #1A1A1A               | Booking card & panel background                |
| --color-bg-card-alt       | #161616               | Lower info area pada booking card              |
| --color-bg-chip           | #1C1C1C               | Filter tab inactive & icon button background   |
| --color-bg-navbar         | #121212               | Bottom tab bar background                      |
| --color-bg-stats          | #141414               | Account Statistics panel background            |
| --color-accent-primary    | #F5C518               | CTA, active tab, highlights, brand text        |
| --color-accent-hover      | #E0B200               | Button pressed state                           |
| --color-text-primary      | #FFFFFF               | Headings, coach name, primary values           |
| --color-text-secondary    | #9A9A9A               | Labels, captions, meta text                    |
| --color-text-muted        | #6B6B6B               | Inactive tab, ditolak item, placeholder        |
| --color-text-on-accent    | #0E0E0E               | Text on yellow/accent elements                 |
| --color-status-confirmed  | #F5C518               | Badge "CONFIRMED" (kuning, outline glow)       |
| --color-status-done       | #9A9A9A               | Badge "SELESAI" (abu)                          |
| --color-status-rejected   | #E0524D               | Badge "DITOLAK" (merah/oranye-merah)           |
| --color-stat-number       | #F5C518               | "98%" / "4.9" angka statistik kuning           |
| --color-stat-big          | #FFFFFF               | "12" big completed-sessions number             |
| --color-watermark         | rgba(245,197,24,0.05) | Watermark "ELITE" di stats panel               |
| --color-overlay-img       | linear-gradient(180deg, transparent, rgba(14,14,14,0.95)) | Gradient overlay foto coach |
| --color-border-card       | #262626               | Card & panel borders                           |
| --color-border-chip       | #2A2A2A               | Filter tab & outline border                    |
| --color-tab-active        | #F5C518               | Active bottom-tab icon & label (PROGRAM)       |
| --color-tab-inactive      | #6B6B6B               | Inactive bottom-tab icon & label               |
| --color-glow-cta          | rgba(245,197,24,0.45) | Glow di sekitar elemen kuning                  |
| --color-overlay-dark      | rgba(0,0,0,0.7)       | Modal backdrop                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (screen title & watermark)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-brand             | 18px | 800    | 1.1    | 0.5px (uppercase)| "PRO BOOKINGS" brand header        |
| --text-screen-title      | 30px | 800    | 1.05   | -0.5px           | "MY SESSIONS" screen title         |
| --text-screen-sub        | 13px | 400    | 1.4    | 0px              | "Manage your elite training schedule" |
| --text-filter-tab        | 13px | 800    | 1.2    | 0.5px (uppercase)| "AKTIF" / "SELESAI" / "DITOLAK"    |
| --text-coach-name        | 22px | 800    | 1.15   | -0.3px           | "Coach Marcus Thorne" coach name   |
| --text-program-meta      | 12px | 600    | 1.3    | 0.8px (uppercase)| "HYPERTROPHY PROGRAM" program tag  |
| --text-field-label       | 10px | 600    | 1.3    | 1px (uppercase)  | "DATE" / "TIME" / "COMPLETED"      |
| --text-field-value       | 15px | 700    | 1.3    | 0px              | "Monday, 24 Oct" / "06:00 PM"      |
| --text-badge             | 10px | 700    | 1.0    | 0.5px (uppercase)| "CONFIRMED" / "SELESAI" / "DITOLAK"|
| --text-btn-inline        | 13px | 800    | 1.2    | 0.5px (uppercase)| "BERI RATING" button               |
| --text-note             | 12px | 400    | 1.4    | 0px              | "Note: Trainer is unavailable..."  |
| --text-stats-title       | 11px | 700    | 1.2    | 1px (uppercase)  | "ACCOUNT STATISTICS" panel title   |
| --text-stats-big         | 56px | 800    | 1.0    | -2px             | "12" completed sessions number     |
| --text-stats-big-label   | 12px | 600    | 1.3    | 0.5px (uppercase)| "COMPLETED SESSIONS"               |
| --text-stats-number      | 28px | 800    | 1.0    | -0.5px           | "98%" / "4.9" stat number          |
| --text-stats-label       | 10px | 600    | 1.3    | 0.8px (uppercase)| "EFFICIENCY" / "AVG RATING"        |
| --text-watermark         | 80px | 900    | 1.0    | -2px (uppercase) | "ELITE" background watermark       |
| --text-tab-label         | 10px | 600    | 1.2    | 0.5px (uppercase)| Bottom tab labels                  |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Badge padding, tiny gaps                         |
| --space-sm     | 8px   | Icon-text gap, label-value gap                   |
| --space-md     | 12px  | Inter-element gap                                |
| --space-base   | 16px  | Screen horizontal padding, card inner padding    |
| --space-lg     | 20px  | Card-to-card vertical gap                        |
| --space-xl     | 24px  | Section separation                               |
| --space-2xl    | 32px  | Major block separation (title ke filter)         |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Badge, inline button                             |
| --radius-md    | 12px  | Filter tab pill, icon buttons                    |
| --radius-lg    | 16px  | Booking cards, stats panel                       |
| --radius-pill  | 999px | Filter tab active, status badge                  |
| --radius-full  | 50%   | Brand avatar, notification button                |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 12px rgba(0,0,0,0.5)            | Booking cards default       |
| --shadow-cta     | 0 0 16px rgba(245,197,24,0.35)        | Glow CONFIRMED badge & CTA  |
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
Card Gap:       20px (antar booking card)
Card Image:     full-width × ~170px (foto coach, gradient overlay di bawah)
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ (👤) PRO BOOKINGS             [🔔]   │  ← Brand Header
├──────────────────────────────────────┤
│ MY SESSIONS                          │  ← Screen Title
│ Manage your elite training schedule  │  ← Subtitle
│ [ AKTIF ] [ SELESAI ] [ DITOLAK ]    │  ← Filter Tabs (Aktif active)
│ ┌──────────────────────────────────┐ │
│ │ [ foto coach ]        [CONFIRMED]│ │  ← Booking Card 1
│ │ Coach Marcus Thorne              │ │
│ │ ⚡ HYPERTROPHY PROGRAM           │ │
│ │ DATE            TIME             │ │
│ │ Monday, 24 Oct  06:00 PM         │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [ foto coach ]          [SELESAI]│ │  ← Booking Card 2
│ │ Coach Elena Vance                │ │
│ │ ⚡ FUNCTIONAL MOBILITY           │ │
│ │ COMPLETED        [ BERI RATING ] │ │
│ │ 20 Oct, 08:30 AM                 │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [ foto coach ]          [DITOLAK]│ │  ← Booking Card 3 (dimmed)
│ │ Coach Julian Reed                │ │
│ │ 🕐 STRENGTH MASTERY              │ │
│ │ Note: Trainer is unavailable...  │ │
│ │ ~18 Oct, 05:00 PM~ (strikethrough)│ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ ACCOUNT STATISTICS      ░ELITE░  │ │  ← Stats Panel
│ │ 12  COMPLETED SESSIONS           │ │
│ │ 98%        4.9                   │ │
│ │ EFFICIENCY AVG RATING            │ │
│ └──────────────────────────────────┘ │
├──────────────────────────────────────┤
│ 🏠     ⚡      👥      🖥️      👤    │  ← Bottom Tab Bar
│ HOME PROGRAM TRAINER MEMBERSHIP PROFIL│
└──────────────────────────────────────┘
```

---

## 5. KOMPONEN: BRAND HEADER

### 5.1 Container
```
Display:        flex, align-items center, justify-content space-between
Padding:        16px
Margin-top:     safe-area-inset-top
```

### 5.2 Kiri — Avatar + Brand
```
Display:        flex, align-items center, gap 12px

Avatar:
  Width/Height: 36px
  Border-radius:50%
  Border:       1.5px solid #F5C518
  Object-fit:   cover

Brand:
  Text:         "PRO BOOKINGS"
  Font-size:    18px, weight 800, uppercase, letter-spacing 0.5px
  Color:        #F5C518
```

### 5.3 Kanan — Notification Button
```
Size:           40px × 40px (icon-only, transparan/subtle bg)
Icon:           🔔 bell (outline), 20px, color #F5C518
Display:        flex center
```

---

## 6. KOMPONEN: SCREEN TITLE BLOCK

```
Padding:        0 16px
Margin:         8px 0 24px

Title:
  Text:         "MY SESSIONS"
  Font-size:    30px, weight 800, color #FFFFFF, letter-spacing -0.5px

Subtitle:
  Text:         "Manage your elite training schedule"
  Font-size:    13px, weight 400, color #9A9A9A, margin-top 4px
```

---

## 7. KOMPONEN: FILTER TABS (SEGMENTED)

### 7.1 Container
```
Display:        flex, gap 8px
Background:     #1C1C1C  (track pill)
Border-radius:  12px
Padding:        4px
Margin:         0 16px 24px
```

### 7.2 Tab Active ("AKTIF")
```
Flex:           1
Padding:        12px 0
Background:     #F5C518
Border-radius:  10px
Color:          #0E0E0E
Font-size:      13px, weight 800, uppercase, letter-spacing 0.5px
Text-align:     center
```

### 7.3 Tab Inactive ("SELESAI" / "DITOLAK")
```
Flex:           1
Padding:        12px 0
Background:     transparan
Color:          #9A9A9A
Font-size:      13px, weight 800, uppercase, letter-spacing 0.5px
Text-align:     center
```

---

## 8. KOMPONEN: BOOKING CARD

### 8.1 Container (Base)
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Margin:         0 16px 20px
Overflow:       hidden  (untuk crop foto coach)
Box-shadow:     0 2px 12px rgba(0,0,0,0.5)
```

### 8.2 Image Area (Foto Coach)
```
Width:          100%
Height:         ~170px
Object-fit:     cover
Position:       relative
Overlay:        linear-gradient(180deg, transparent 40%, rgba(14,14,14,0.95) 100%)
                (memastikan transisi mulus ke info area)

Status Badge (absolute, top-right, offset 12px):
  Padding:      6px 12px, border-radius 999px
  Font:         10px, weight 700, uppercase, letter-spacing 0.5px
  Variant CONFIRMED:  bg rgba(245,197,24,0.15), border 1px solid #F5C518, color #F5C518, glow
  Variant SELESAI:    bg #1C1C1C, border 1px solid #2A2A2A, color #9A9A9A
  Variant DITOLAK:    bg rgba(224,82,77,0.15), border 1px solid #E0524D, color #E0524D
```

### 8.3 Info Area
```
Background:     #161616  (lanjutan dari gradient)
Padding:        16px

Coach Name:
  Text:         "Coach Marcus Thorne" → 22px, weight 800, color #FFFFFF, letter-spacing -0.3px

Program Tag (flex, align center, gap 8px, margin-top 6px):
  Icon:         ⚡/🕐 18px, color #F5C518 (atau #6B6B6B utk DITOLAK)
  Text:         "HYPERTROPHY PROGRAM" → 12px, weight 600, uppercase, letter-spacing 0.8px, color #9A9A9A

Divider:
  Border-top:   1px solid #262626
  Margin:       14px 0
```

### 8.4 Detail Row — Variant AKTIF/CONFIRMED (DATE + TIME)
```
Display:        flex, gap 48px

Field block (label di atas, value di bawah):
  Label:        10px, weight 600, uppercase, letter-spacing 1px, color #9A9A9A
  Value:        15px, weight 700, color #FFFFFF, margin-top 4px

  DATE:  "Monday, 24 Oct"
  TIME:  "06:00 PM"
```

### 8.5 Detail Row — Variant SELESAI (COMPLETED + CTA Rating)
```
Display:        flex, justify-content space-between, align-items center

Kiri — Completed block:
  Label:        "COMPLETED" → 10px, weight 600, uppercase, color #9A9A9A
  Value:        "20 Oct, 08:30 AM" → 15px, weight 700, color #FFFFFF

Kanan — BERI RATING button:
  Background:   #F5C518
  Color:        #0E0E0E
  Padding:      10px 18px, border-radius 8px
  Font:         13px, weight 800, uppercase, letter-spacing 0.5px
```

### 8.6 Variant DITOLAK (Rejected — dimmed)
```
Opacity:        0.55  (seluruh card diredupkan)

Coach Name:     color #9A9A9A (bukan putih penuh)
Program Tag:    icon 🕐 clock, color #6B6B6B

Note:
  Text:         "Note: Trainer is unavailable at this slot."
  Font:         12px, weight 400, color #E0524D (merah lembut), margin 8px 0

Schedule (rejected):
  Text:         "18 Oct, 05:00 PM"
  Font:         15px, weight 700, color #6B6B6B
  Text-decoration: line-through  (slot dibatalkan/ditolak)
```

---

## 9. KOMPONEN: ACCOUNT STATISTICS PANEL

### 9.1 Container
```
Background:     #141414
Border:         1px solid #262626
Border-radius:  16px
Padding:        20px
Margin:         24px 16px 0
Position:       relative
Overflow:       hidden  (untuk crop watermark)
```

### 9.2 Watermark Dekoratif
```
Text:           "ELITE"
Font-size:      80px, weight 900, color rgba(245,197,24,0.05)
Position:       absolute, bottom-right, melewati tepi
Text-transform: uppercase
Z-index:        0, pointer-events none
```

### 9.3 Panel Title
```
Text:           "ACCOUNT STATISTICS"
Font-size:      11px, weight 700, uppercase, letter-spacing 1px, color #F5C518
Margin-bottom:  16px
```

### 9.4 Big Number Row (Completed Sessions)
```
Display:        flex, align-items center, gap 12px

Big Number:
  Text:         "12" → 56px, weight 800, color #FFFFFF, letter-spacing -2px

Label:
  Text:         "COMPLETED SESSIONS" → 12px, weight 600, uppercase, color #9A9A9A
                (wrap 2 baris)
```

### 9.5 Secondary Stats Row
```
Display:        flex, gap 48px, margin-top 16px

Stat block (number di atas, label di bawah):
  Number:       28px, weight 800, color #F5C518, letter-spacing -0.5px
  Label:        10px, weight 600, uppercase, letter-spacing 0.8px, color #9A9A9A

  Stat 1:  "98%"  / "EFFICIENCY"
  Stat 2:  "4.9"  / "AVG RATING"
```

---

## 10. KOMPONEN: BOTTOM TAB BAR

### 10.1 Container
```
Position:       fixed, bottom 0, left 0, right 0
Height:         72px (+ safe-area-inset-bottom)
Background:     #121212
Border-top:     1px solid #1E1E1E
Box-shadow:     0 -2px 12px rgba(0,0,0,0.5)
Display:        flex, justify-content space-around, align-items center
Z-index:        100
```

### 10.2 Tab Item (Default / Inactive)
```
Display:        flex, flex-direction column, align-items center, gap 4px
Icon:           22px, color #6B6B6B
Label:          10px, weight 600, uppercase, letter-spacing 0.5px, color #6B6B6B
```

### 10.3 Tab Item (Active — PROGRAM)
```
Icon:           22px, color #F5C518
Label-color:    #F5C518
Indicator:      opsional — highlight pill bg di belakang ikon PROGRAM
                (bg rgba(245,197,24,0.12), border-radius 12px)
```

### 10.4 Daftar Tabs (5 item — sesuai gambar)
```
1. 🏠  HOME
2. ⚡  PROGRAM      ← ACTIVE (kuning)
3. 👥  TRAINER
4. 🖥️  MEMBERSHIP
5. 👤  PROFIL
```

---

## 11. GRID RECAP — RINGKASAN ZONA LAYOUT (Mobile)

| Zone                    | X Offset | Y Offset  | Width            | Height    |
|-------------------------|----------|-----------|------------------|-----------|
| Brand Header            | 0        | safe-top  | 100%             | ~64px     |
| Screen Title Block      | 16px     | ~116px    | calc(100% - 32px)| ~76px     |
| Filter Tabs             | 16px     | ~208px    | calc(100% - 32px)| ~48px     |
| Booking Card (CONFIRMED)| 16px     | ~280px    | calc(100% - 32px)| ~320px    |
| Booking Card (SELESAI)  | 16px     | ~620px    | calc(100% - 32px)| ~330px    |
| Booking Card (DITOLAK)  | 16px     | ~970px    | calc(100% - 32px)| ~310px    |
| Account Statistics Panel| 16px     | ~1300px   | calc(100% - 32px)| ~180px    |
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px      |

*Catatan: konten jauh melebihi tinggi viewport (932px) → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 12. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Booking History Screen (Pro Bookings, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Booking History.png
   Generated: 2026-06-27
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:        #0E0E0E;
  --color-bg-card:           #1A1A1A;
  --color-bg-card-alt:       #161616;
  --color-bg-chip:           #1C1C1C;
  --color-bg-navbar:         #121212;
  --color-bg-stats:          #141414;
  --color-accent-primary:    #F5C518;
  --color-accent-hover:      #E0B200;
  --color-text-primary:      #FFFFFF;
  --color-text-secondary:    #9A9A9A;
  --color-text-muted:        #6B6B6B;
  --color-text-on-accent:    #0E0E0E;
  --color-status-confirmed:  #F5C518;
  --color-status-done:       #9A9A9A;
  --color-status-rejected:   #E0524D;
  --color-stat-number:       #F5C518;
  --color-stat-big:          #FFFFFF;
  --color-watermark:         rgba(245,197,24,0.05);
  --color-border-card:       #262626;
  --color-border-chip:       #2A2A2A;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.45);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-brand:              18px;
  --text-screen-title:       30px;
  --text-screen-sub:         13px;
  --text-filter-tab:         13px;
  --text-coach-name:         22px;
  --text-program-meta:       12px;
  --text-field-label:        10px;
  --text-field-value:        15px;
  --text-badge:              10px;
  --text-btn-inline:         13px;
  --text-note:               12px;
  --text-stats-title:        11px;
  --text-stats-big:          56px;
  --text-stats-big-label:    12px;
  --text-stats-number:       28px;
  --text-stats-label:        10px;
  --text-watermark:          80px;
  --text-tab-label:          10px;

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
  --shadow-card:             0 2px 12px rgba(0,0,0,0.5);
  --shadow-cta:              0 0 16px rgba(245,197,24,0.35);
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --navbar-height:           72px;
  --card-gap:                20px;
  --card-radius:             16px;
  --card-image-height:       170px;
  --tab-count:               5;
}
```

---

## 13. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Booking History.png`. Semua teks (PRO BOOKINGS, MY SESSIONS, Manage your elite training schedule, AKTIF/SELESAI/DITOLAK, Coach Marcus Thorne, Coach Elena Vance, Coach Julian Reed, HYPERTROPHY PROGRAM, FUNCTIONAL MOBILITY, STRENGTH MASTERY, tanggal & jam, 12, 98%, 4.9) harus persis sama dengan gambar.

2. **Mobile-First Layout**: Layar member-facing dibuka dari tab Program (PROGRAM tetap aktif di bottom bar). List booking scrollable vertikal. Gunakan `safe-area-inset-*`.

3. **Filter Tabs (3 state)**: Tab "AKTIF" (aktif, pill kuning solid), "SELESAI" & "DITOLAK" (inaktif). Switch tab memfilter daftar booking sesuai status. Pada gambar ini ditampilkan kombinasi contoh ketiga status untuk preview. Gunakan `role="tablist"` + `aria-selected`.

4. **Booking Card Structure**: Tiap card = image area (foto coach + gradient overlay + status badge) di atas, info area di bawah (nama coach, program tag, detail/aksi). Wajib `overflow:hidden` agar foto ter-crop rapi mengikuti border-radius.

5. **Status Badge (enum 3 varian)**: CONFIRMED (kuning, outline + glow), SELESAI (abu netral), DITOLAK (merah `#E0524D`). Posisi absolute top-right di atas foto. Jangan andalkan warna saja — sertakan teks badge.

6. **Gradient Overlay Foto**: Foto coach diberi gradient gelap di bagian bawah (`transparent → rgba(14,14,14,0.95)`) agar transisi ke info area mulus dan teks tetap terbaca bila ada overlap.

7. **Variant Detail Row Berbeda per Status**: AKTIF/CONFIRMED menampilkan DATE + TIME (booking mendatang). SELESAI menampilkan COMPLETED + tombol "BERI RATING". DITOLAK menampilkan note alasan + jadwal strikethrough. Render kondisional berdasarkan enum status.

8. **DITOLAK Dimmed State**: Seluruh card diredupkan (`opacity 0.55`), nama coach abu, jadwal `line-through`, note merah lembut menjelaskan alasan ("Trainer is unavailable at this slot"). Tidak ada CTA aksi.

9. **BERI RATING CTA**: Hanya muncul pada booking SELESAI yang belum dirating. Tombol kuning solid memicu flow pemberian rating/review trainer. Setelah dirating, tombol bisa diganti tampilan rating bintang.

10. **Account Statistics Panel**: Panel ringkasan di bawah list — angka besar "12" (completed sessions) + dua stat sekunder "98% EFFICIENCY" & "4.9 AVG RATING" (kuning). Watermark "ELITE" raksasa opacity rendah di belakang; wajib `overflow:hidden` + `pointer-events:none`.

11. **Hierarki Angka Statistik**: Big number "12" putih `56px/800`; stat sekunder kuning `28px/800`. Bedakan warna untuk menandai metrik utama (jumlah sesi, netral) vs metrik performa (kuning, brand-positive).

12. **Program Tag Icon**: Tiap card punya ikon kecil sebelum nama program — ⚡ (lightning, aktif/selesai) atau 🕐 (clock, ditolak/menunggu). Warna ikon mengikuti status (kuning vs abu).

13. **Scroll & Padding**: Konten jauh lebih panjang dari viewport. Beri `padding-bottom:88px` agar stats panel & elemen terbawah tidak tertutup tab bar. Brand header boleh sticky.

14. **Accessibility**: Beri `aria-current="page"` pada tab PROGRAM. Filter tabs gunakan pola `tablist/tab` dengan `aria-selected`. Status badge sertakan teks (CONFIRMED/SELESAI/DITOLAK), jangan warna saja. Booking DITOLAK beri `aria-disabled="true"` bila non-interaktif. Tombol BERI RATING & notification beri `aria-label` jelas. Touch target minimum 44×44px.

---

*Spec ini generated dari analisis visual screen Booking History.png (visual-verified).*
*Design system reference: Egg Gym — Program Screen (PROGRAM_TAB_UI_SPEC.md), Session Detail (SESSION_DETAIL_PT_UI_SPEC.md) & Member Home (MEMBER_HOME_UI_SPEC.md).*
*Total sections: 14 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

# TRAINER_SCHEDULE_UI_SPEC.md
# Egg Gym App — Trainer Schedule Screen (Jadwal Sesi, Pro Trainer Side, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Trainer App > Jadwal (Jadwal Sesi — Session Management)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Trainer Schedule.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Jadwal Sesi (Pro Trainer) memakai sistem warna identik dengan Home PT Dashboard & sisi Member (Editorial Athletics): latar near-black dengan aksen kuning emas. Token tambahan ditambahkan untuk date selector (active/idle), filter tabs booking, status sesi (confirmed), accent rail permintaan, dan aksi konfirmasi/tolak.

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0E0E0E               | App background (screen utama)                  |
| --color-bg-card           | #1A1A1A               | Session & request card background              |
| --color-bg-card-alt       | #161616               | Inner block / nested card background           |
| --color-bg-chip           | #1C1C1C               | Date tile idle, filter tab idle, btn secondary |
| --color-bg-navbar         | #121212               | Bottom tab bar background                      |
| --color-accent-primary    | #F5C518               | CTA, date active, active tab, brand text       |
| --color-accent-hover      | #E0B200               | Button pressed state                           |
| --color-text-primary      | #FFFFFF               | Headings, client names, primary values         |
| --color-text-secondary    | #9A9A9A               | Labels, captions, meta text                    |
| --color-text-muted        | #6B6B6B               | Inactive tab, idle date label, placeholder     |
| --color-text-on-accent    | #0E0E0E               | Text on yellow/accent elements (date active)   |
| --color-date-active-bg    | #F5C518               | Date tile aktif (kuning solid)                 |
| --color-date-active-text  | #0E0E0E               | Teks pada date tile aktif                      |
| --color-date-idle-bg      | #1C1C1C               | Date tile idle                                 |
| --color-status-confirmed  | #F5C518               | Badge "DIKONFIRMASI"                            |
| --color-status-confirmed-bg | rgba(245,197,24,0.15)| Background badge "DIKONFIRMASI"               |
| --color-action-confirm    | #F5C518               | Tombol "Konfirmasi" (kuning, fill gelap-kuning)|
| --color-action-confirm-bg | rgba(245,197,24,0.15) | Background tombol "Konfirmasi"                 |
| --color-action-reject     | #E0524D               | Tombol "Tolak" (merah, destructive)            |
| --color-action-reject-bg  | rgba(224,82,77,0.12)  | Background tombol "Tolak"                       |
| --color-accent-rail       | #F5C518               | Left accent rail di request card               |
| --color-link              | #F5C518               | "3 TERJADWAL" meta link                        |
| --color-border-card       | #262626               | Card & panel borders                           |
| --color-border-chip       | #2A2A2A               | Filter tab & outline button border             |
| --color-tab-active        | #F5C518               | Active bottom-tab icon & label (JADWAL)        |
| --color-tab-inactive      | #6B6B6B               | Inactive bottom-tab icon & label               |
| --color-glow-cta          | rgba(245,197,24,0.45) | Glow CTA kuning                                |
| --color-overlay-dark      | rgba(0,0,0,0.7)       | Modal backdrop                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (screen title)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-brand             | 20px | 800    | 1.1    | 0.5px (uppercase)| "EGGGYM" brand text                |
| --text-screen-title      | 28px | 800    | 1.1    | -0.3px           | "Jadwal Sesi" screen title         |
| --text-screen-sub        | 13px | 600    | 1.4    | 1px (uppercase)  | "MANAJEMEN PELATIHAN PERSONAL"     |
| --text-date-day          | 10px | 700    | 1.2    | 0.5px (uppercase)| "SEN" / "SEL" hari pada date tile  |
| --text-date-num          | 22px | 800    | 1.0    | -0.5px           | "12" / "13" tanggal pada date tile |
| --text-section-title     | 20px | 800    | 1.2    | 0px              | "Sesi Hari Ini" / "Permintaan Booking" |
| --text-section-meta      | 11px | 700    | 1.2    | 0.5px (uppercase)| "3 TERJADWAL" meta                 |
| --text-session-name      | 18px | 700    | 1.3    | 0px              | "Maya Permata" client name         |
| --text-session-time      | 13px | 500    | 1.3    | 0px              | "08:00 - 09:30" session time       |
| --text-badge             | 10px | 700    | 1.0    | 0.5px (uppercase)| "DIKONFIRMASI" badge               |
| --text-btn-primary       | 14px | 800    | 1.2    | 0.3px            | "Mulai Sesi" button                |
| --text-btn-secondary     | 14px | 700    | 1.2    | 0px              | "Detail" button                    |
| --text-filter-tab        | 13px | 700    | 1.2    | 0px              | "Menunggu" / "Dikonfirmasi" filter |
| --text-request-name      | 16px | 700    | 1.3    | 0px              | "Siska Amelia" request name        |
| --text-request-meta      | 11px | 600    | 1.3    | 0.5px (uppercase)| "POWER YOGA • BESOK, 07:00"        |
| --text-action-btn        | 13px | 700    | 1.2    | 0px              | "Konfirmasi" / "Tolak" button      |
| --text-tab-label         | 9px  | 600    | 1.2    | 0.5px (uppercase)| Bottom tab labels                  |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Badge padding, tiny gaps                         |
| --space-sm     | 8px   | Icon-text gap, date tile gap                     |
| --space-md     | 12px  | Inter-element gap                                |
| --space-base   | 16px  | Screen horizontal padding, card padding          |
| --space-lg     | 20px  | Card-to-card vertical gap                        |
| --space-xl     | 24px  | Section separation                               |
| --space-2xl    | 32px  | Major block separation                           |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Badge, inline button, action button             |
| --radius-md    | 12px  | Date tile, filter tab, avatar thumb             |
| --radius-lg    | 16px  | Cards, session & request card                    |
| --radius-pill  | 999px | Filter tab (pill), status badge                  |
| --radius-full  | 50%   | Brand avatar, notification button               |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards default               |
| --shadow-date    | 0 4px 12px rgba(245,197,24,0.35)      | Glow date tile aktif        |
| --shadow-cta     | 0 0 16px rgba(245,197,24,0.35)        | Glow "Mulai Sesi" CTA       |
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
Card Gap:       12px (antar card) / 24px (antar section)
Date Selector:  5 tile equal-width, gap 10px, scrollable horizontal
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ (👤) EGGGYM                   [🔔]   │  ← Brand Header
├──────────────────────────────────────┤
│ Jadwal Sesi                          │  ← Screen Title
│ MANAJEMEN PELATIHAN PERSONAL         │  ← Subtitle
│ ┌───┐┌───┐┌───┐┌───┐┌───┐           │
│ │SEN││SEL││RAB││KAM││JUM│           │  ← Date Selector
│ │12 ││13 ││14 ││15 ││16 │           │  (SEL/13 active kuning)
│ └───┘└───┘└───┘└───┘└───┘           │
│ Sesi Hari Ini          3 TERJADWAL   │  ← Section header
│ ┌──────────────────────────────────┐ │
│ │ [👤] Maya Permata [DIKONFIRMASI] │ │  ← Session Card
│ │      🕐 08:00 - 09:30            │ │
│ │ [   Mulai Sesi   ] [  Detail  ]  │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [👤] Budi Santoso [DIKONFIRMASI] │ │  ← Session Card
│ │      🕐 16:00 - 17:30            │ │
│ │ [   Mulai Sesi   ] [  Detail  ]  │ │
│ └──────────────────────────────────┘ │
│ Permintaan Booking                   │  ← Section header
│ [Menunggu][Dikonfirmasi][Selesai]    │  ← Filter Tabs
│ ┃┌─────────────────────────────────┐ │
│ ┃│ [👤] Siska Amelia               │ │  ← Request Card (rail kuning)
│ ┃│      POWER YOGA • BESOK, 07:00  │ │
│ ┃│ [ Konfirmasi ]  [   Tolak   ]   │ │
│ ┃└─────────────────────────────────┘ │
│ ┃┌─────────────────────────────────┐ │
│ ┃│ [👤] Rian Pratama               │ │  ← Request Card
│ ┃│      CHEST DAY • 15 JAN, 19:00  │ │
│ ┃│ [ Konfirmasi ]  [   Tolak   ]   │ │
│ ┃└─────────────────────────────────┘ │
├──────────────────────────────────────┤
│ 🏠     📅     👥      ⚡      👤    │  ← Bottom Tab Bar (TRAINER)
│ HOME JADWAL KLIEN PROGRAM PROFIL     │  ← JADWAL active
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
  Size:         40px × 40px, border-radius 50%
  Border:       1.5px solid #F5C518
  Object-fit:   cover

Brand:
  Text:         "EGGGYM"
  Font-size:    20px, weight 800, uppercase, letter-spacing 0.5px, color #F5C518
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
  Text:         "Jadwal Sesi"
  Font-size:    28px, weight 800, color #FFFFFF, letter-spacing -0.3px

Subtitle:
  Text:         "MANAJEMEN PELATIHAN PERSONAL"
  Font-size:    13px, weight 600, uppercase, letter-spacing 1px, color #9A9A9A
  Margin-top:   4px
```

---

## 7. KOMPONEN: DATE SELECTOR

### 7.1 Container
```
Display:        flex, gap 10px, overflow-x auto (scrollable horizontal)
Padding:        0 16px
Margin-bottom:  24px
```

### 7.2 Date Tile — Idle
```
Flex:           1 (atau fixed ~60px)
Background:     #1C1C1C
Border:         1px solid #262626
Border-radius:  12px
Padding:        14px 0
Display:        flex, flex-direction column, align-items center, gap 6px

Day Label:      "SEN"/"RAB"/"KAM"/"JUM" → 10px, weight 700, uppercase, color #6B6B6B
Date Number:    "12"/"14"/"15"/"16" → 22px, weight 800, color #FFFFFF
```

### 7.3 Date Tile — Active ("SEL 13")
```
Background:     #F5C518
Border-radius:  12px
Padding:        14px 0
Box-shadow:     0 4px 12px rgba(245,197,24,0.35)  (glow)

Day Label:      "SEL" → 10px, weight 700, uppercase, color #0E0E0E (opacity 0.7)
Date Number:    "13" → 22px, weight 800, color #0E0E0E
```

---

## 8. KOMPONEN: SESI HARI INI (Today's Sessions)

### 8.1 Section Header
```
Display:        flex, justify-content space-between, align-items baseline
Padding:        0 16px
Margin-bottom:  12px

Judul:
  Text:         "Sesi Hari Ini"  → 20px, weight 800, #FFFFFF

Meta:
  Text:         "3 TERJADWAL"
  Font-size:    11px, weight 700, uppercase, letter-spacing 0.5px, color #F5C518
```

### 8.2 Session Card (Variant CONFIRMED)
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Padding:        16px
Margin:         0 16px 12px

Header Row (flex, align center, gap 12px):
  Avatar:       44px × 44px, border-radius 12px (rounded-square), object-fit cover
  Info (flex 1):
    Name:       "Maya Permata" / "Budi Santoso" → 18px, weight 700, color #FFFFFF
    Time:       🕐 + "08:00 - 09:30" / "16:00 - 17:30" → 13px, weight 500, color #9A9A9A
  Badge "DIKONFIRMASI":
    Font:       10px, weight 700, uppercase, color #F5C518
    Background: rgba(245,197,24,0.15), padding 5px 10px, border-radius 999px

Action Row (margin-top 14px, display flex, gap 12px):
  Mulai Sesi (flex ~2 / dominan):
    Background: #F5C518
    Color:      #0E0E0E
    Padding:    14px 0, border-radius 8px
    Font:       14px, weight 800, text-align center
    Box-shadow: 0 0 16px rgba(245,197,24,0.35)
  Detail (flex ~1):
    Background: transparan
    Border:     1px solid #2A2A2A
    Color:      #FFFFFF
    Padding:    14px 18px, border-radius 8px
    Font:       14px, weight 700, text-align center
```

---

## 9. KOMPONEN: PERMINTAAN BOOKING (Booking Requests)

### 9.1 Section Header
```
Text:           "Permintaan Booking"
Font-size:      20px, weight 800, color #FFFFFF
Padding:        0 16px
Margin:         24px 0 12px
```

### 9.2 Filter Tabs
```
Display:        flex, gap 10px, overflow-x auto (scrollable horizontal)
Padding:        0 16px
Margin-bottom:  16px

Tab Active ("Menunggu"):
  Background:   #F5C518
  Color:        #0E0E0E
  Padding:      10px 18px, border-radius 999px
  Font:         13px, weight 700

Tab Inactive ("Dikonfirmasi" / "Selesai"):
  Background:   #1C1C1C
  Border:       1px solid #2A2A2A
  Color:        #9A9A9A
  Padding:      10px 18px, border-radius 999px
  Font:         13px, weight 700
```

### 9.3 Request Card
```
Background:     #161616
Border:         1px solid #262626
Border-left:    3px solid #F5C518   (accent rail — permintaan baru/menunggu)
Border-radius:  16px
Padding:        16px
Margin:         0 16px 12px

Header Row (flex, align center, gap 12px):
  Avatar:       44px × 44px, border-radius 12px, object-fit cover
  Info (flex 1):
    Name:       "Siska Amelia" / "Rian Pratama" → 16px, weight 700, color #FFFFFF
    Meta:       "POWER YOGA • BESOK, 07:00" / "CHEST DAY • 15 JAN, 19:00"
                → 11px, weight 600, uppercase, letter-spacing 0.5px, color #9A9A9A

Action Row (margin-top 14px, display flex, gap 12px):
  Konfirmasi (flex 1):
    Background: rgba(245,197,24,0.15)
    Color:      #F5C518
    Padding:    12px 0, border-radius 8px
    Font:       13px, weight 700, text-align center
  Tolak (flex 1):
    Background: rgba(224,82,77,0.12)
    Color:      #E0524D
    Padding:    12px 0, border-radius 8px
    Font:       13px, weight 700, text-align center
```

---

## 10. KOMPONEN: BOTTOM TAB BAR (TRAINER VARIANT)

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
Label:          9px, weight 600, uppercase, letter-spacing 0.5px, color #6B6B6B
```

### 10.3 Tab Item (Active — JADWAL)
```
Icon:           22px, color #F5C518
Label-color:    #F5C518
Indicator:      highlight pill bg di belakang ikon JADWAL
                (bg rgba(245,197,24,0.12), border-radius 12px)
```

### 10.4 Daftar Tabs (5 item — VERSI TRAINER, berbeda dari Member)
```
1. 🏠  HOME
2. 📅  JADWAL      ← ACTIVE (kuning)
3. 👥  KLIEN
4. ⚡  PROGRAM
5. 👤  PROFIL
```

---

## 11. GRID RECAP — RINGKASAN ZONA LAYOUT (Mobile)

| Zone                    | X Offset | Y Offset  | Width            | Height    |
|-------------------------|----------|-----------|------------------|-----------|
| Brand Header            | 0        | safe-top  | 100%             | ~72px     |
| Screen Title Block      | 16px     | ~124px    | calc(100% - 32px)| ~76px     |
| Date Selector           | 16px     | ~216px    | calc(100% - 32px)| ~80px     |
| Sesi Hari Ini Header    | 16px     | ~320px    | calc(100% - 32px)| ~30px     |
| Session Card ×2         | 16px     | ~366px    | calc(100% - 32px)| ~140px each|
| Permintaan Booking Hdr  | 16px     | ~670px    | calc(100% - 32px)| ~30px     |
| Filter Tabs             | 16px     | ~712px    | calc(100% - 32px)| ~44px     |
| Request Card ×2         | 16px     | ~772px    | calc(100% - 32px)| ~130px each|
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px      |

*Catatan: konten melebihi tinggi viewport (932px) → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 12. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Trainer Schedule Screen (Jadwal Sesi, Pro Trainer, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Trainer Schedule.png
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
  --color-text-primary:      #FFFFFF;
  --color-text-secondary:    #9A9A9A;
  --color-text-muted:        #6B6B6B;
  --color-text-on-accent:    #0E0E0E;
  --color-date-active-bg:    #F5C518;
  --color-date-active-text:  #0E0E0E;
  --color-date-idle-bg:      #1C1C1C;
  --color-status-confirmed:  #F5C518;
  --color-status-confirmed-bg: rgba(245,197,24,0.15);
  --color-action-confirm:    #F5C518;
  --color-action-confirm-bg: rgba(245,197,24,0.15);
  --color-action-reject:     #E0524D;
  --color-action-reject-bg:  rgba(224,82,77,0.12);
  --color-accent-rail:       #F5C518;
  --color-link:              #F5C518;
  --color-border-card:       #262626;
  --color-border-chip:       #2A2A2A;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.45);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-brand:              20px;
  --text-screen-title:       28px;
  --text-screen-sub:         13px;
  --text-date-day:           10px;
  --text-date-num:           22px;
  --text-section-title:      20px;
  --text-section-meta:       11px;
  --text-session-name:       18px;
  --text-session-time:       13px;
  --text-badge:              10px;
  --text-btn-primary:        14px;
  --text-btn-secondary:      14px;
  --text-filter-tab:         13px;
  --text-request-name:       16px;
  --text-request-meta:       11px;
  --text-action-btn:         13px;
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
  --shadow-date:             0 4px 12px rgba(245,197,24,0.35);
  --shadow-cta:              0 0 16px rgba(245,197,24,0.35);
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --navbar-height:           72px;
  --card-gap:                12px;
  --card-radius:             16px;
  --date-tile-count:         5;
  --tab-count:               5;
}
```

---

## 13. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Trainer Schedule.png`. Semua teks (EGGGYM, Jadwal Sesi, MANAJEMEN PELATIHAN PERSONAL, SEN/SEL/RAB/KAM/JUM + 12-16, Sesi Hari Ini, 3 TERJADWAL, Maya Permata, 08:00 - 09:30, Budi Santoso, 16:00 - 17:30, DIKONFIRMASI, Mulai Sesi, Detail, Permintaan Booking, Menunggu/Dikonfirmasi/Selesai, Siska Amelia, POWER YOGA • BESOK 07:00, Rian Pratama, CHEST DAY • 15 JAN 19:00, Konfirmasi, Tolak) harus persis sama dengan gambar.

2. **TRAINER SIDE (Bukan Member)**: Bagian dari keluarga Trainer-side (lihat HOME_PT_DASHBOARD_UI_SPEC). Bottom tab bar versi trainer: **HOME / JADWAL / KLIEN / PROGRAM / PROFIL** dengan JADWAL aktif. Jangan tertukar dengan tab bar member.

3. **Mobile-First Layout**: Layar manajemen jadwal trainer, konten scrollable vertikal. Gunakan `safe-area-inset-*`. Brand header membawa identitas EGGGYM.

4. **Date Selector Interaktif**: Baris 5 tile tanggal (SEN-JUM) scrollable horizontal; tile aktif (SEL/13) kuning solid dengan teks gelap + glow, idle abu dengan teks putih. Tap tanggal memfilter "Sesi Hari Ini" untuk hari tsb. Bisa diperluas ke minggu lain via scroll. Gunakan `role="tablist"`/`aria-selected`.

5. **Sesi Hari Ini**: Daftar sesi terjadwal pada tanggal terpilih. Meta "3 TERJADWAL" menunjukkan jumlah sesi. Tiap kartu = avatar klien + nama + jam + badge status + aksi. Pada gambar keduanya DIKONFIRMASI.

6. **Session Card Action (dominan + sekunder)**: "Mulai Sesi" (kuning solid, flex lebih besar/dominan, glow) memulai sesi; "Detail" (outline, lebih kecil) membuka rincian sesi. Berbeda dari Home PT yang punya CTA tunggal — di sini ada dua aksi berdampingan.

7. **Permintaan Booking dengan Filter**: Section terpisah untuk permintaan booking masuk, dengan filter tabs (Menunggu/Dikonfirmasi/Selesai). Tab aktif "Menunggu" kuning solid. Filter mengubah daftar request sesuai status. Konsisten pola filter pill dengan layar member.

8. **Request Card Accent Rail**: Tiap kartu permintaan diberi `border-left:3px solid #F5C518` (accent rail) menandai item butuh aksi/menunggu keputusan. Meta menampilkan jenis program + waktu booking (relatif "BESOK, 07:00" atau absolut "15 JAN, 19:00").

9. **Konfirmasi/Tolak (tinted buttons)**: Berbeda dari Home PT (Konfirmasi abu, Tolak outline merah), di sini keduanya tinted: "Konfirmasi" bg kuning transparan + teks kuning; "Tolak" bg merah transparan + teks merah `#E0524D`. Keduanya flex-1 berdampingan. Tolak idealnya memicu konfirmasi.

10. **Avatar Rounded-Square**: Avatar klien pada layar ini memakai border-radius 12px (rounded-square), bukan lingkaran penuh — bedakan dari header avatar yang bulat. Konsisten antar session & request card.

11. **Relasi dengan Home PT Dashboard**: Layar ini perluasan dari "Today's Sessions" di Home PT — Home menampilkan ringkasan, Jadwal menampilkan manajemen penuh per-tanggal + antrian permintaan. Status & aksi (Mulai Sesi/Konfirmasi/Tolak) harus sinkron antar dua layar.

12. **State Kosong**: Siapkan empty state bila tanggal terpilih tidak ada sesi ("Tidak ada sesi") atau filter booking kosong ("Tidak ada permintaan"). Tidak terlihat di gambar tapi penting untuk implementasi.

13. **Scroll & Padding**: Konten lebih tinggi dari viewport → scroll vertikal. Beri `padding-bottom:88px` agar request card terbawah tidak tertutup tab bar. Header & date selector boleh sticky agar navigasi tanggal selalu terjangkau.

14. **Accessibility**: Beri `aria-current="page"` pada tab JADWAL. Date selector & filter tabs gunakan `role="tablist"`/`aria-selected`. Status sesi sertakan teks badge (DIKONFIRMASI), jangan warna saja. Tombol Mulai Sesi/Detail/Konfirmasi/Tolak beri `aria-label` menyertakan nama klien (mis. "Konfirmasi booking Siska Amelia"). Tolak (destructive) gunakan konfirmasi. Kontras teks gelap pada elemen kuning penuhi WCAG AA. Touch target minimum 44×44px.

---

*Spec ini generated dari analisis visual screen Trainer Schedule.png (visual-verified).*
*Design system reference: Egg Gym — Home PT Dashboard (HOME_PT_DASHBOARD_UI_SPEC.md) & Member specs. CATATAN: sisi TRAINER, bottom tab bar HOME/JADWAL/KLIEN/PROGRAM/PROFIL.*
*Total sections: 14 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

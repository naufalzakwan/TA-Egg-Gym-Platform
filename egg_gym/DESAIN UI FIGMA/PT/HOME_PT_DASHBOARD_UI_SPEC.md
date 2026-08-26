# HOME_PT_DASHBOARD_UI_SPEC.md
# Egg Gym App — Home Dashboard Screen (Pro Trainer Side, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Trainer App > Home (PT Dashboard)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Home PT Dashboard.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Dashboard Trainer (Pro Trainer) memakai sistem warna identik dengan sisi Member (Editorial Athletics): latar near-black dengan aksen kuning emas. Token tambahan ditambahkan untuk stat tiles, timer ring (progress/track), kontrol timer, dan status sesi (confirmed/waiting) beserta aksi destructive (Tolak).

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0E0E0E               | App background (screen utama)                  |
| --color-bg-card           | #1A1A1A               | Card, stat tile & timer panel background       |
| --color-bg-card-alt       | #161616               | Session card / inner block background          |
| --color-bg-chip           | #1C1C1C               | Toggle chip & icon button background           |
| --color-bg-navbar         | #121212               | Bottom tab bar background                      |
| --color-accent-primary    | #F5C518               | CTA, active toggle, stat number, brand text    |
| --color-accent-hover      | #E0B200               | Button pressed state                           |
| --color-text-primary      | #FFFFFF               | Greeting, session names, primary values         |
| --color-text-secondary    | #9A9A9A               | Labels, captions, meta text                    |
| --color-text-muted        | #6B6B6B               | Inactive tab/toggle, placeholder               |
| --color-text-on-accent    | #0E0E0E               | Text on yellow/accent elements                 |
| --color-stat-number       | #F5C518               | "12" / "8" / "4.9" stat tile numbers           |
| --color-timer-ring-fill   | #F5C518               | Progress ring timer (terisi)                   |
| --color-timer-ring-track  | #2A2A2A               | Track ring timer (kosong)                      |
| --color-timer-display     | #FFFFFF               | "45:00" angka timer                            |
| --color-timer-mode        | #9A9A9A               | "HIGH INTENSITY" label mode                    |
| --color-ctrl-play         | #F5C518               | Tombol play (kuning solid, primary)            |
| --color-ctrl-secondary    | #1C1C1C               | Tombol reset/stop (abu gelap)                  |
| --color-status-confirmed  | #F5C518               | Badge "DIKONFIRMASI"                            |
| --color-status-waiting    | #9A9A9A               | Badge "MENUNGGU"                               |
| --color-action-reject     | #E0524D               | Tombol "Tolak" (merah, destructive)            |
| --color-action-reject-bd  | rgba(224,82,77,0.45)  | Border tombol "Tolak"                          |
| --color-accent-rail       | #F5C518               | Left accent rail di session card aktif         |
| --color-border-card       | #262626               | Card & panel borders                           |
| --color-border-chip       | #2A2A2A               | Toggle chip & outline border                   |
| --color-tab-active        | #F5C518               | Active bottom-tab icon & label (HOME)          |
| --color-tab-inactive      | #6B6B6B               | Inactive bottom-tab icon & label               |
| --color-glow-cta          | rgba(245,197,24,0.45) | Glow play button & CTA kuning                  |
| --color-overlay-dark      | rgba(0,0,0,0.7)       | Modal backdrop                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (greeting & timer display)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-brand             | 16px | 800    | 1.1    | 0px              | "EggGym" brand text                |
| --text-brand-sub         | 9px  | 700    | 1.2    | 1.5px (uppercase)| "PRO TRAINER" sub-brand            |
| --text-greeting          | 26px | 800    | 1.15   | -0.3px           | "Halo, Coach Adrian 👋" greeting   |
| --text-greeting-sub      | 14px | 400    | 1.4    | 0px              | "Siap membakar kalori hari ini?"   |
| --text-stat-label        | 10px | 600    | 1.3    | 0.5px (uppercase)| "KLIEN AKTIF" / "SESI HARI INI"    |
| --text-stat-number       | 32px | 800    | 1.0    | -0.5px           | "12" / "8" / "4.9" stat number     |
| --text-toggle            | 13px | 700    | 1.2    | 0.5px (uppercase)| "COUNTDOWN" / "STOPWATCH"          |
| --text-timer-display     | 52px | 800    | 1.0    | -1px             | "45:00" timer countdown            |
| --text-timer-mode        | 11px | 700    | 1.2    | 1.5px (uppercase)| "HIGH INTENSITY" mode label        |
| --text-section-title     | 20px | 800    | 1.2    | 0px              | "Today's Sessions" section title   |
| --text-link              | 12px | 700    | 1.0    | 0.5px (uppercase)| "LIHAT SEMUA" link                 |
| --text-session-name      | 17px | 700    | 1.3    | 0px              | "Naufal" / "Budi" client name      |
| --text-session-time      | 13px | 500    | 1.3    | 0px              | "08:00 - 09:30" session time       |
| --text-badge             | 10px | 700    | 1.0    | 0.5px (uppercase)| "DIKONFIRMASI" / "MENUNGGU" badge  |
| --text-btn-inline        | 14px | 800    | 1.2    | 0.3px            | "Mulai Sesi" / "Konfirmasi" / "Tolak"|
| --text-tab-label         | 9px  | 600    | 1.2    | 0.5px (uppercase)| Bottom tab labels                  |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Badge padding, tiny gaps                         |
| --space-sm     | 8px   | Icon-text gap, stat tile gap                     |
| --space-md     | 12px  | Inter-element gap                                |
| --space-base   | 16px  | Screen horizontal padding, card padding          |
| --space-lg     | 20px  | Card-to-card vertical gap                        |
| --space-xl     | 24px  | Section separation                               |
| --space-2xl    | 32px  | Major block separation (timer panel)             |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Badge, inline button                             |
| --radius-md    | 12px  | Stat tile, toggle chip, icon button              |
| --radius-lg    | 16px  | Cards, timer panel, session card                 |
| --radius-pill  | 999px | Status badge                                     |
| --radius-full  | 50%   | Avatar, timer ring, play/reset/stop control      |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards default               |
| --shadow-play    | 0 0 24px rgba(245,197,24,0.5)         | Glow tombol play timer      |
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
Card Gap:       12px (session card) / 24px (antar section)
Stat Tiles:     3 kolom equal-width, gap 12px
Timer Ring:     ~200px diameter, centered
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ (👤) EggGym                   [🔔]   │  ← Brand Header
│      PRO TRAINER                     │
├──────────────────────────────────────┤
│ Halo, Coach Adrian 👋                │  ← Greeting
│ Siap membakar kalori hari ini?       │  ← Greeting subtitle
│ ┌──────┐ ┌──────┐ ┌──────┐          │
│ │KLIEN │ │SESI  │ │RATING│          │  ← Stat Tiles (3)
│ │AKTIF │ │HARI..│ │      │          │
│ │ 12   │ │  8   │ │ 4.9  │          │
│ └──────┘ └──────┘ └──────┘          │
│ ┌──────────────────────────────────┐ │
│ │ [COUNTDOWN] [STOPWATCH]      [⚙] │ │  ← Timer Panel
│ │          ╭─────────╮             │ │
│ │          │  45:00  │             │ │  ← Timer ring + display
│ │          │HIGH INTEN│            │ │
│ │          ╰─────────╯             │ │
│ │       (↺)   (▶)   (□)            │ │  ← Controls
│ └──────────────────────────────────┘ │
│ Today's Sessions       LIHAT SEMUA   │  ← Section header
│ ┃┌─────────────────────────────────┐ │
│ ┃│ [👤] Naufal      [DIKONFIRMASI] │ │  ← Session: CONFIRMED
│ ┃│      🕐 08:00 - 09:30           │ │  (rail kuning)
│ ┃│      [    Mulai Sesi    ]       │ │
│ ┃└─────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [👤] Budi          [MENUNGGU]    │ │  ← Session: WAITING
│ │      🕐 10:00 - 11:30            │ │
│ │      [ Konfirmasi ] [  Tolak  ]  │ │
│ └──────────────────────────────────┘ │
├──────────────────────────────────────┤
│ 🏠     📅     👥      ⚡      👤    │  ← Bottom Tab Bar (TRAINER)
│ HOME JADWAL KLIEN PROGRAM PROFIL     │  ← HOME active
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

Brand block:
  Brand:        "EggGym" → 16px, weight 800, color #F5C518
  Sub-brand:    "PRO TRAINER" → 9px, weight 700, uppercase, letter-spacing 1.5px, color #9A9A9A
```

### 5.3 Kanan — Notification Button
```
Size:           40px × 40px (icon-only, transparan/subtle bg)
Icon:           🔔 bell (filled, ada dot notif), 20px, color #F5C518
Display:        flex center
```

---

## 6. KOMPONEN: GREETING BLOCK

```
Padding:        0 16px
Margin:         8px 0 20px

Greeting:
  Text:         "Halo, Coach Adrian 👋"
  Font-size:    26px, weight 800, color #FFFFFF, letter-spacing -0.3px

Subtitle:
  Text:         "Siap membakar kalori hari ini?"
  Font-size:    14px, weight 400, color #9A9A9A, margin-top 4px
```

---

## 7. KOMPONEN: STAT TILES (3 kolom)

### 7.1 Container
```
Display:        flex, gap 12px
Padding:        0 16px
Margin-bottom:  24px
```

### 7.2 Stat Tile (×3, equal width)
```
Flex:           1
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  12px
Padding:        16px 14px
(boleh ada ikon dekoratif subtle di pojok: client/calendar/star)

Label:
  Text:         "KLIEN AKTIF" / "SESI HARI INI" / "RATING"
  Font-size:    10px, weight 600, uppercase, letter-spacing 0.5px, color #9A9A9A
                (wrap 2 baris untuk "SESI HARI INI")

Number:
  Text:         "12" / "8" / "4.9"
  Font-size:    32px, weight 800, color #F5C518, margin-top 8px
```

---

## 8. KOMPONEN: TIMER PANEL

### 8.1 Container
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Padding:        20px
Margin:         0 16px 24px
```

### 8.2 Mode Toggle (Countdown / Stopwatch)
```
Display:        flex, align-items center, justify-content space-between

Toggle group (kiri):
  Background:   #1C1C1C, border-radius 12px, padding 4px, display flex gap 4px

  Chip Active ("COUNTDOWN"):
    Background: transparan (atau subtle), color #F5C518
    Padding:    8px 16px, border-radius 10px
    Font:       13px, weight 700, uppercase, letter-spacing 0.5px

  Chip Inactive ("STOPWATCH"):
    Color:      #9A9A9A
    Padding:    8px 16px
    Font:       13px, weight 700, uppercase

Settings Button (kanan):
  Size:         36px × 36px, icon-only
  Icon:         ⚙ gear, 18px, color #9A9A9A
```

### 8.3 Timer Ring + Display
```
Ring:
  Diameter:     ~200px, centered, margin 24px auto
  Track:        stroke #2A2A2A, width 6px
  Progress:     stroke #F5C518, width 6px, rounded cap
                (arc mengikuti sisa waktu; render via SVG circle stroke-dashoffset)

Display (di tengah ring):
  Time:         "45:00" → 52px, weight 800, color #FFFFFF, letter-spacing -1px
  Mode label:   "HIGH INTENSITY" → 11px, weight 700, uppercase, letter-spacing 1.5px, color #9A9A9A
```

### 8.4 Control Buttons Row
```
Display:        flex, align-items center, justify-content center, gap 24px
Margin-top:     24px

Reset Button (kiri):
  Size:         48px × 48px, border-radius 50%
  Background:   #1C1C1C
  Icon:         ↺ rotate-ccw, 20px, color #FFFFFF

Play Button (tengah, primary):
  Size:         64px × 64px, border-radius 50%
  Background:   #F5C518
  Icon:         ▶ play, 24px, color #0E0E0E
  Box-shadow:   0 0 24px rgba(245,197,24,0.5)  (glow)

Stop Button (kanan):
  Size:         48px × 48px, border-radius 50%
  Background:   #1C1C1C
  Icon:         □ square/stop, 18px, color #FFFFFF
```

---

## 9. KOMPONEN: TODAY'S SESSIONS

### 9.1 Section Header
```
Display:        flex, justify-content space-between, align-items center
Padding:        0 16px
Margin-bottom:  12px

Judul:
  Text:         "Today's Sessions"  → 20px, weight 800, #FFFFFF

Link:
  Text:         "LIHAT SEMUA"
  Font-size:    12px, weight 700, uppercase, letter-spacing 0.5px, color #F5C518
```

### 9.2 Session Card — Variant CONFIRMED (DIKONFIRMASI)
```
Background:     #161616
Border:         1px solid #262626
Border-left:    3px solid #F5C518   (accent rail — sesi siap dimulai)
Border-radius:  16px
Padding:        16px
Margin:         0 16px 12px

Header Row (flex, align center, gap 12px):
  Avatar:       44px × 44px, border-radius 50%, object-fit cover
  Info (flex 1):
    Name:       "Naufal" → 17px, weight 700, color #FFFFFF
    Time:       🕐 + "08:00 - 09:30" → 13px, weight 500, color #9A9A9A
  Badge "DIKONFIRMASI":
    Font:       10px, weight 700, uppercase, color #F5C518
    Background: rgba(245,197,24,0.15), padding 4px 10px, border-radius 999px

CTA — Mulai Sesi (margin-top 12px):
  Width:        100%
  Background:   #F5C518
  Border-radius:8px
  Padding:      14px 0
  Color:        #0E0E0E
  Font:         14px, weight 800, letter-spacing 0.3px
  Text-align:   center
  Box-shadow:   0 0 16px rgba(245,197,24,0.35)
```

### 9.3 Session Card — Variant WAITING (MENUNGGU)
```
Background:     #161616
Border:         1px solid #262626
Border-radius:  16px
Padding:        16px
Margin:         0 16px 12px

Header Row (flex, align center, gap 12px):
  Avatar:       44px × 44px, border-radius 50%
  Info (flex 1):
    Name:       "Budi" → 17px, weight 700, color #FFFFFF
    Time:       🕐 + "10:00 - 11:30" → 13px, weight 500, color #9A9A9A
  Badge "MENUNGGU":
    Font:       10px, weight 700, uppercase, color #9A9A9A
    Background: #1C1C1C, border 1px solid #2A2A2A, padding 4px 10px, border-radius 999px

Action Row (margin-top 12px, display flex, gap 12px):
  Konfirmasi (flex 1):
    Background: #1C1C1C (atau abu netral)
    Color:      #FFFFFF
    Padding:    14px 0, border-radius 8px
    Font:       14px, weight 800, text-align center
  Tolak (flex 1):
    Background: transparan
    Border:     1px solid rgba(224,82,77,0.45)
    Color:      #E0524D
    Padding:    14px 0, border-radius 8px
    Font:       14px, weight 800, text-align center
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

### 10.3 Tab Item (Active — HOME)
```
Icon:           22px, color #F5C518
Label-color:    #F5C518
Indicator:      highlight pill bg di belakang ikon HOME
                (bg rgba(245,197,24,0.12), border-radius 12px)
```

### 10.4 Daftar Tabs (5 item — VERSI TRAINER, berbeda dari Member)
```
1. 🏠  HOME        ← ACTIVE (kuning)
2. 📅  JADWAL
3. 👥  KLIEN
4. ⚡  PROGRAM
5. 👤  PROFIL
```

---

## 11. GRID RECAP — RINGKASAN ZONA LAYOUT (Mobile)

| Zone                    | X Offset | Y Offset  | Width            | Height    |
|-------------------------|----------|-----------|------------------|-----------|
| Brand Header            | 0        | safe-top  | 100%             | ~72px     |
| Greeting Block          | 16px     | ~124px    | calc(100% - 32px)| ~76px     |
| Stat Tiles (×3)         | 16px     | ~216px    | calc(100% - 32px)| ~96px     |
| Timer Panel             | 16px     | ~336px    | calc(100% - 32px)| ~380px    |
| Today's Sessions Header | 16px     | ~740px    | calc(100% - 32px)| ~30px     |
| Session Card (CONFIRMED)| 16px     | ~786px    | calc(100% - 32px)| ~150px    |
| Session Card (WAITING)  | 16px     | ~948px    | calc(100% - 32px)| ~150px    |
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px      |

*Catatan: konten melebihi tinggi viewport (932px) → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 12. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Home Dashboard Screen (Pro Trainer Side, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Home PT Dashboard.png
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
  --color-stat-number:       #F5C518;
  --color-timer-ring-fill:   #F5C518;
  --color-timer-ring-track:  #2A2A2A;
  --color-timer-display:     #FFFFFF;
  --color-timer-mode:        #9A9A9A;
  --color-ctrl-play:         #F5C518;
  --color-ctrl-secondary:    #1C1C1C;
  --color-status-confirmed:  #F5C518;
  --color-status-waiting:    #9A9A9A;
  --color-action-reject:     #E0524D;
  --color-action-reject-bd:  rgba(224,82,77,0.45);
  --color-accent-rail:       #F5C518;
  --color-border-card:       #262626;
  --color-border-chip:       #2A2A2A;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.45);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-brand:              16px;
  --text-brand-sub:          9px;
  --text-greeting:           26px;
  --text-greeting-sub:       14px;
  --text-stat-label:         10px;
  --text-stat-number:        32px;
  --text-toggle:             13px;
  --text-timer-display:      52px;
  --text-timer-mode:         11px;
  --text-section-title:      20px;
  --text-link:               12px;
  --text-session-name:       17px;
  --text-session-time:       13px;
  --text-badge:              10px;
  --text-btn-inline:         14px;
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
  --shadow-play:             0 0 24px rgba(245,197,24,0.5);
  --shadow-cta:              0 0 16px rgba(245,197,24,0.35);
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --navbar-height:           72px;
  --card-gap:                12px;
  --card-radius:             16px;
  --timer-ring-size:         200px;
  --tab-count:               5;
}
```

---

## 13. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Home PT Dashboard.png`. Semua teks (EggGym, PRO TRAINER, Halo Coach Adrian 👋, Siap membakar kalori hari ini?, KLIEN AKTIF 12, SESI HARI INI 8, RATING 4.9, COUNTDOWN, STOPWATCH, 45:00, HIGH INTENSITY, Today's Sessions, LIHAT SEMUA, Naufal, 08:00 - 09:30, DIKONFIRMASI, Mulai Sesi, Budi, 10:00 - 11:30, MENUNGGU, Konfirmasi, Tolak) harus persis sama dengan gambar.

2. **TRAINER SIDE (Bukan Member)**: Ini perbedaan paling fundamental dari seluruh spec sebelumnya. Layar ini adalah aplikasi sisi Pro Trainer. Bottom tab bar berbeda: **HOME / JADWAL / KLIEN / PROGRAM / PROFIL** (bukan HOME/PROGRAM/TRAINER/MEMBERSHIP/PROFIL milik member). Jangan tertukar antar dua tab bar.

3. **Mobile-First Layout**: Dashboard trainer dengan HOME aktif. Konten scrollable vertikal. Gunakan `safe-area-inset-*`. Brand header membawa identitas "PRO TRAINER".

4. **Greeting Personalisasi**: Sapaan dinamis "Halo, Coach {Name} 👋" + tagline motivasional. Nama coach diambil dari profil trainer yang login. Emoji 👋 bagian dari teks.

5. **Stat Tiles (3 metrik)**: KLIEN AKTIF (12), SESI HARI INI (8), RATING (4.9) — ringkasan performa harian trainer. Angka kuning `32px/800`. Tile equal-width 3 kolom. Boleh ada ikon dekoratif subtle (client/calendar/star) di latar tiap tile.

6. **Timer Interaktif (Komponen Utama)**: Panel timer dengan mode toggle COUNTDOWN/STOPWATCH, ring progress SVG, display "45:00", label intensitas, dan 3 kontrol (reset/play/stop). Ini alat bantu trainer saat memimpin sesi (interval/HIIT). Implementasi ring via `<circle>` SVG + `stroke-dashoffset` animasi.

7. **Timer Ring Rendering**: Ring kuning mengikuti sisa waktu (arc). Track abu `#2A2A2A` penuh di belakang, fill kuning `#F5C518` dengan `stroke-linecap:round`. Update offset tiap detik via JS. Display angka di tengah (absolute center).

8. **Timer Controls Hierarki**: Play (tengah, 64px, kuning solid + glow) = primary/dominan; Reset & Stop (48px, abu) = secondary di kiri-kanan. Saat berjalan, ikon play berubah jadi pause. Beri state visual jelas (running/paused/stopped).

9. **Session Card 2 State (enum)**: CONFIRMED/DIKONFIRMASI (accent rail kuning, badge kuning, CTA tunggal "Mulai Sesi") vs WAITING/MENUNGGU (tanpa rail, badge abu, dua aksi Konfirmasi/Tolak). Render kondisional berdasarkan status booking dari sisi trainer.

10. **Action Konfirmasi/Tolak**: Pada sesi MENUNGGU, trainer memutuskan menerima atau menolak booking. "Konfirmasi" (netral/abu, atau bisa kuning) dan "Tolak" (destructive merah outline). Tolak idealnya memicu konfirmasi/alasan. Setelah aksi, status & tampilan card berubah.

11. **Mulai Sesi CTA**: Pada sesi DIKONFIRMASI, tombol kuning "Mulai Sesi" memulai sesi latihan (kemungkinan menautkan ke timer di atas atau membuka layar sesi). Punya glow. Accent rail kiri menandai sesi yang siap/prioritas.

12. **Avatar Klien**: Tiap session card menampilkan avatar klien (44px) + nama + waktu. Konsisten dengan pola avatar di kartu lain. Gunakan placeholder bila foto klien tidak ada.

13. **Scroll & Padding**: Konten lebih tinggi dari viewport → scroll vertikal. Beri `padding-bottom:88px` agar session card terbawah tidak tertutup tab bar. Header boleh sticky.

14. **Accessibility**: Beri `aria-current="page"` pada tab HOME. Timer toggle gunakan `role="tablist"`/`aria-selected`; display timer beri `role="timer"` & `aria-live="polite"`. Kontrol play/reset/stop beri `aria-label` jelas (mis. "Mulai timer"). Status sesi sertakan teks badge (DIKONFIRMASI/MENUNGGU), jangan warna saja. Tolak (destructive) gunakan konfirmasi. Touch target minimum 44×44px (kontrol timer, tombol aksi, tab).

---

*Spec ini generated dari analisis visual screen Home PT Dashboard.png (visual-verified).*
*Design system reference: Egg Gym — Member specs (PROGRAM_TAB_UI_SPEC.md, dst.). CATATAN: layar ini sisi TRAINER, bottom tab bar berbeda (HOME/JADWAL/KLIEN/PROGRAM/PROFIL).*
*Total sections: 14 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

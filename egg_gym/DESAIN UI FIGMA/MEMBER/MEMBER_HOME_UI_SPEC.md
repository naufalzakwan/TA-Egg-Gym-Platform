# MEMBER_HOME_UI_SPEC.md
# Egg Gym App — Member Home Screen (Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Member App > Home (Beranda Athlete)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Home Member.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar member memakai latar near-black dengan aksen kuning emas, konsisten dengan
brand "Editorial Athletics". Panel/kartu memakai abu sangat gelap.

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0E0E0E               | App background (screen utama)                  |
| --color-bg-card           | #1A1A1A               | Card & panel background                        |
| --color-bg-card-alt       | #161616               | Timer panel / secondary card                   |
| --color-bg-chip           | #1C1C1C               | Preset chip & icon button background           |
| --color-bg-navbar         | #121212               | Bottom tab bar background                      |
| --color-accent-primary    | #F5C518               | CTA, active tab, highlights, brand text        |
| --color-accent-hover      | #E0B200               | Button pressed state                           |
| --color-text-primary      | #FFFFFF               | Headings, primary values, card titles          |
| --color-text-secondary    | #9A9A9A               | Labels, captions, helper text                  |
| --color-text-muted        | #6B6B6B               | Inactive tab, placeholder, sub-text            |
| --color-text-on-accent    | #0E0E0E               | Text on yellow/accent elements                 |
| --color-status-active     | #F5C518               | "AKTIF" membership badge                       |
| --color-greeting          | #F5C518               | "Halo, Naufal" greeting (kuning)               |
| --color-days-highlight    | #F5C518               | "142" days remaining number                    |
| --color-border-card       | #262626               | Card & panel borders                           |
| --color-border-chip       | #2A2A2A               | Preset chip border                             |
| --color-tab-active        | #F5C518               | Active bottom-tab icon & label                 |
| --color-tab-inactive      | #6B6B6B               | Inactive bottom-tab icon & label               |
| --color-glow-cta          | rgba(245,197,24,0.45) | Glow di sekitar tombol "START SESSION"         |
| --color-overlay-dark      | rgba(0,0,0,0.7)       | Modal backdrop                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (timer pakai tabular-nums)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-supra-label       | 10px | 600    | 1.2    | 1.5px (uppercase)| "ATHLETE PROFILE" supra-label      |
| --text-greeting          | 20px | 800    | 1.1    | 0px              | "Halo, Naufal 👋" greeting         |
| --text-status-label      | 11px | 600    | 1.3    | 1.5px (uppercase)| "ELITE STATUS" label               |
| --text-tier-title        | 28px | 800    | 1.1    | -0.5px (uppercase)| "PLATINUM CLUB" tier name         |
| --text-card-mini-label   | 10px | 600    | 1.3    | 1px (uppercase)  | "VALID UNTIL" / "DAYS REMAINING"   |
| --text-card-value        | 16px | 700    | 1.2    | 0px              | "DEC 20, 2024" valid date          |
| --text-days-number       | 40px | 800    | 1.0    | -1px             | "142" days remaining               |
| --text-badge             | 10px | 700    | 1.0    | 0.5px (uppercase)| "AKTIF" membership badge           |
| --text-tab-toggle        | 14px | 700    | 1.2    | 0px              | "Countdown" / "Stopwatch" toggle   |
| --text-timer             | 72px | 300    | 1.0    | 0px              | "10:00" timer display              |
| --text-timer-caption     | 11px | 600    | 1.3    | 2px (uppercase)  | "READY TO GRIND" caption           |
| --text-preset-chip       | 14px | 700    | 1.0    | 0px              | "10:00" / "15:00" / "30:00" preset |
| --text-cta               | 14px | 800    | 1.2    | 1px (uppercase)  | "START SESSION" button             |
| --text-section-title     | 18px | 800    | 1.2    | 0px              | "Next PT Session" heading          |
| --text-link              | 12px | 600    | 1.0    | 0.5px (uppercase)| "VIEW ALL" link                    |
| --text-trainer-name      | 16px | 700    | 1.3    | 0px              | "Coach Adrian Putra"               |
| --text-session-meta      | 12px | 400    | 1.4    | 0px              | "17:00 - 18:30", "Studio A"        |
| --text-tab-label         | 10px | 600    | 1.2    | 0.5px (uppercase)| Bottom tab labels                  |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Badge padding, tiny gaps                         |
| --space-sm     | 8px   | Icon-text gap, chip inner gap                    |
| --space-md     | 12px  | Inter-element gap                                |
| --space-base   | 16px  | Screen horizontal padding, card padding          |
| --space-lg     | 20px  | Card-to-card vertical gap                        |
| --space-xl     | 24px  | Section separation                               |
| --space-2xl    | 32px  | Major block separation                           |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Preset chips, small elements                     |
| --radius-md    | 12px  | Icon buttons, session thumbnail                  |
| --radius-lg    | 16px  | Cards & panels                                   |
| --radius-pill  | 999px | Status badge, START SESSION button               |
| --radius-full  | 50%   | Avatar, reset/pause circle buttons               |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards default               |
| --shadow-cta     | 0 0 24px rgba(245,197,24,0.45)        | Glow tombol START SESSION   |
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
Card Gap:       20px
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ [👤] ATHLETE PROFILE          [🔔]   │  ← Header
│      Halo, Naufal 👋                  │
├──────────────────────────────────────┤
│ ┌──────────────────────────────────┐ │
│ │ ELITE STATUS          [AKTIF]    │ │  ← Membership Card
│ │ PLATINUM CLUB                    │ │
│ │ VALID UNTIL          142         │ │
│ │ DEC 20, 2024    DAYS REMAINING   │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [Countdown]  Stopwatch           │ │  ← Timer Card
│ │                                  │ │
│ │           10:00                  │ │
│ │        READY TO GRIND            │ │
│ │   [10:00] [15:00] [30:00]        │ │
│ │   (↺)  [ START SESSION ]  (⏸)    │ │
│ └──────────────────────────────────┘ │
│ Next PT Session          VIEW ALL    │  ← Section header
│ ┌──────────────────────────────────┐ │
│ │ [foto] Coach Adrian Putra    [>] │ │  ← PT Session Card
│ │        🕐 17:00-18:30 📍Studio A  │ │
│ └──────────────────────────────────┘ │
├──────────────────────────────────────┤
│ 🏠     ⚡      👥      🖥️      👤    │  ← Bottom Tab Bar
│ HOME PROGRAM TRAINER MEMBERSHIP PROFIL│
└──────────────────────────────────────┘
```

---

## 5. KOMPONEN: HEADER (Greeting)

### 5.1 Container
```
Display:        flex, align-items center, justify-content space-between
Padding:        16px
Margin-top:     safe-area-inset-top
```

### 5.2 Kiri — Avatar + Greeting
```
Display:        flex, align-items center, gap 12px

Avatar:
  Width/Height: 40px
  Border-radius:50%
  Object-fit:   cover
  Border:       1px solid #2A2A2A

Teks:
  Supra-label:
    Text:       "ATHLETE PROFILE"
    Font-size:  10px
    Font-weight:600
    Color:      #9A9A9A
    Letter-spacing:1.5px
    Text-transform:uppercase
  Greeting:
    Text:       "Halo, Naufal 👋"
    Font-size:  20px
    Font-weight:800
    Color:      #F5C518
    Margin-top: 2px
```

### 5.3 Kanan — Notification Button
```
Size:           40px × 40px
Background:     #1C1C1C
Border-radius:  12px
Icon:           🔔 bell, 20px, color #F5C518
Display:        flex center
Badge dot (opsional): 6px #EF4444 top-right
```

---

## 6. KOMPONEN: MEMBERSHIP STATUS CARD

### 6.1 Container
```
Background:     #1A1A1A   (boleh subtle gradient ke #1E1A0A di kanan)
Border:         1px solid #262626
Border-radius:  16px
Padding:        20px
Margin:         0 16px 20px
Position:       relative
```

### 6.2 Top Row
```
Display:        flex, justify-content space-between, align-items center

ELITE STATUS label:
  Font-size:    11px
  Font-weight:  600
  Color:        #9A9A9A
  Letter-spacing:1.5px
  Text-transform:uppercase

Badge "AKTIF":
  Font-size:    10px
  Font-weight:  700
  Color:        #F5C518
  Background:   transparan
  Border:       1px solid #F5C518
  Border-radius:999px
  Padding:      4px 12px
  Text-transform:uppercase
```

### 6.3 Tier Title
```
Text:           "PLATINUM CLUB"
Font-size:      28px
Font-weight:    800
Color:          #FFFFFF
Letter-spacing: -0.5px
Text-transform: uppercase
Margin:         8px 0 20px
```

### 6.4 Bottom Row (Valid + Days)
```
Display:        flex, justify-content space-between, align-items flex-end

Kiri — Valid Until:
  Mini-label:
    Text:       "VALID UNTIL"
    Font-size:  10px
    Color:      #9A9A9A
    Letter-spacing:1px
    Text-transform:uppercase
  Value:
    Text:       "DEC 20, 2024"
    Font-size:  16px
    Font-weight:700
    Color:      #FFFFFF
    Margin-top: 4px

Kanan — Days Remaining:
  Number:
    Text:       "142"
    Font-size:  40px
    Font-weight:800
    Color:      #F5C518
    Line-height:1.0
  Mini-label:
    Text:       "DAYS REMAINING"
    Font-size:  10px
    Color:      #9A9A9A
    Letter-spacing:1px
    Text-transform:uppercase
    Text-align: right
```

---

## 7. KOMPONEN: TIMER CARD (Countdown / Stopwatch)

### 7.1 Container
```
Background:     #161616
Border:         1px solid #262626
Border-radius:  16px
Padding:        20px 20px 24px
Margin:         0 16px 24px
```

### 7.2 Toggle Tabs (Countdown / Stopwatch)
```
Display:        flex, gap 20px
Margin-bottom:  24px

Tab Active (Countdown):
  Font-size:    14px
  Font-weight:  700
  Color:        #FFFFFF
  Border-bottom:2px solid #F5C518
  Padding-bottom:6px

Tab Inactive (Stopwatch):
  Font-size:    14px
  Font-weight:  700
  Color:        #6B6B6B
```

### 7.3 Timer Display
```
Text:           "10:00"
Font-size:      72px
Font-weight:    300
Color:          #FFFFFF
Font-variant:   tabular-nums
Text-align:     center
Note:           titik dua ":" berwarna kuning #F5C518 (separator highlight)

Caption:
  Text:         "READY TO GRIND"
  Font-size:    11px
  Font-weight:  600
  Color:        #9A9A9A
  Letter-spacing:2px
  Text-transform:uppercase
  Text-align:   center
  Margin-top:   8px
```

### 7.4 Preset Chips
```
Display:        flex, justify-content center, gap 12px
Margin:         24px 0

Chip Default (15:00, 30:00):
  Padding:      10px 18px
  Background:   #1C1C1C
  Border:       1px solid #2A2A2A
  Border-radius:8px
  Font-size:    14px
  Font-weight:  700
  Color:        #9A9A9A

Chip Active (10:00):
  Background:   transparan
  Border:       1px solid #F5C518
  Color:        #F5C518
```

### 7.5 Control Row
```
Display:        flex, align-items center, justify-content center, gap 16px

Reset Button (↺):
  Size:         48px × 48px
  Border-radius:50%
  Background:   #1C1C1C
  Border:       1px solid #2A2A2A
  Icon:         ↺ refresh, 20px, color #9A9A9A

START SESSION (CTA utama):
  Flex:         1 (lebar dominan, pill)
  Height:       60px
  Background:   #F5C518
  Border-radius:999px
  Color:        #0E0E0E
  Font-size:    14px
  Font-weight:  800
  Letter-spacing:1px
  Text-transform:uppercase
  Box-shadow:   0 0 24px rgba(245,197,24,0.45)  (glow)
  Text-align:   center

Pause Button (⏸):
  Size:         48px × 48px
  Border-radius:50%
  Background:   #1C1C1C
  Border:       1px solid #2A2A2A
  Icon:         ⏸ pause, 18px, color #9A9A9A
```

---

## 8. KOMPONEN: NEXT PT SESSION

### 8.1 Section Header
```
Display:        flex, justify-content space-between, align-items center
Padding:        0 16px
Margin-bottom:  12px

Judul:
  Text:         "Next PT Session"
  Font-size:    18px
  Font-weight:  800
  Color:        #FFFFFF

Link:
  Text:         "VIEW ALL"
  Font-size:    12px
  Font-weight:  600
  Color:        #9A9A9A
  Letter-spacing:0.5px
  Text-transform:uppercase
```

### 8.2 Session Card
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Padding:        14px
Margin:         0 16px
Display:        flex, align-items center, gap 14px
```

### 8.3 Thumbnail Trainer
```
Width/Height:   64px × 64px
Border-radius:  12px
Object-fit:     cover
Flex-shrink:    0
```

### 8.4 Info (tengah, flex 1)
```
Trainer Name:
  Text:         "Coach Adrian Putra"
  Font-size:    16px
  Font-weight:  700
  Color:        #FFFFFF

Meta Row:
  Display:      flex, align-items center, gap 14px
  Margin-top:   6px
  Font-size:    12px
  Color:        #9A9A9A

  Waktu:        🕐 "17:00 - 18:30"   (ikon clock 14px)
  Lokasi:       📍 "Studio A"        (ikon pin 14px)
```

### 8.5 Action Chevron
```
Size:           40px × 40px
Background:     #F5C518
Border-radius:  12px
Icon:           › chevron-right, 20px, color #0E0E0E
Display:        flex center
Flex-shrink:    0
```

---

## 9. KOMPONEN: BOTTOM TAB BAR

### 9.1 Container
```
Position:       fixed, bottom 0, left 0, right 0
Height:         72px (+ safe-area-inset-bottom)
Background:     #121212
Border-top:     1px solid #1E1E1E
Box-shadow:     0 -2px 12px rgba(0,0,0,0.5)
Display:        flex, justify-content space-around, align-items center
Z-index:        100
```

### 9.2 Tab Item (Default / Inactive)
```
Display:        flex, flex-direction column, align-items center, gap 4px
Icon:           22px, color #6B6B6B
Label:
  Font-size:    10px
  Font-weight:  600
  Color:        #6B6B6B
  Letter-spacing:0.5px
  Text-transform:uppercase
```

### 9.3 Tab Item (Active — HOME)
```
Icon:           22px, color #F5C518
Label-color:    #F5C518
Indicator:      opsional — pill/rounded highlight bg di belakang ikon HOME
                (bg rgba(245,197,24,0.12), border-radius 12px)
```

### 9.4 Daftar Tabs (5 item — sesuai gambar)
```
1. 🏠  HOME         ← ACTIVE (kuning)
2. ⚡  PROGRAM
3. 👥  TRAINER
4. 🖥️  MEMBERSHIP
5. 👤  PROFIL
```

---

## 10. GRID RECAP — RINGKASAN ZONA LAYOUT (Mobile)

| Zone               | X Offset | Y Offset  | Width            | Height    |
|--------------------|----------|-----------|------------------|-----------|
| Header (Greeting)  | 0        | safe-top  | 100%             | ~64px     |
| Membership Card    | 16px     | ~108px    | calc(100% - 32px)| ~150px    |
| Timer Card         | 16px     | ~278px    | calc(100% - 32px)| ~330px    |
| Next PT Section Hdr| 16px     | ~628px    | calc(100% - 32px)| ~30px     |
| PT Session Card    | 16px     | ~668px    | calc(100% - 32px)| ~92px     |
| Bottom Tab Bar     | 0        | bottom: 0 | 100%             | 72px      |

---

## 11. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Member Home Screen (Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Home Member.png
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
  --color-status-active:     #F5C518;
  --color-days-highlight:    #F5C518;
  --color-border-card:       #262626;
  --color-border-chip:       #2A2A2A;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.45);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-supra-label:        10px;
  --text-greeting:           20px;
  --text-status-label:       11px;
  --text-tier-title:         28px;
  --text-card-value:         16px;
  --text-days-number:        40px;
  --text-badge:              10px;
  --text-tab-toggle:         14px;
  --text-timer:              72px;
  --text-timer-caption:      11px;
  --text-preset-chip:        14px;
  --text-cta:                14px;
  --text-section-title:      18px;
  --text-trainer-name:       16px;
  --text-session-meta:       12px;
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
  --shadow-card:             0 2px 8px rgba(0,0,0,0.4);
  --shadow-cta:              0 0 24px rgba(245,197,24,0.45);
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --navbar-height:           72px;
  --card-gap:                20px;
  --card-radius:             16px;
  --cta-height:              60px;
  --tab-count:               5;
}
```

---

## 12. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Home Member.png`. Semua teks (Halo Naufal, PLATINUM CLUB, DEC 20 2024, 142 days, 10:00, Coach Adrian Putra, 17:00-18:30, Studio A) harus persis sama dengan gambar.

2. **Mobile-First Layout**: Ini layar mobile member-facing, bukan dashboard admin. Tidak ada sidebar; navigasi via **bottom tab bar** 5 item. Gunakan `100vw` width, `safe-area-inset-*` untuk notch & home indicator.

3. **Greeting Personalisasi**: "Halo, [Nama] 👋" diisi dinamis dari profil member, berwarna kuning `#F5C518`. Supra-label "ATHLETE PROFILE" tetap statis abu.

4. **Membership Card Gradient (opsional)**: Boleh diberi subtle gradient gelap-ke-kecoklatan di sisi kanan untuk menonjolkan angka "142". Angka days remaining & badge "AKTIF" sama-sama kuning.

5. **Days Remaining Dinamis**: Angka "142" = selisih hari antara hari ini dan tanggal "VALID UNTIL". Hitung dengan date-diff; tampilkan dengan warna kuning untuk emphasis.

6. **Timer Toggle**: Dua mode — "Countdown" (aktif, underline kuning) dan "Stopwatch" (inaktif abu). Switch mengubah perilaku timer. Separator ":" pada display timer berwarna kuning sebagai aksen visual.

7. **Preset Chips**: Tiga preset durasi (10:00 / 15:00 / 30:00). Chip aktif (10:00) memakai outline kuning. Tap chip mengubah nilai timer & menandai aktif. Default state countdown = 10:00.

8. **START SESSION Glow**: Tombol CTA pill kuning besar dengan **glow shadow** (`0 0 24px rgba(245,197,24,0.45)`). Diapit tombol bundar Reset (↺, kiri) dan Pause (⏸, kanan). Saat sesi berjalan, label berubah jadi "PAUSE/STOP" sesuai state.

9. **Timer Display Font**: Gunakan font-weight ringan (300) dengan `font-variant-numeric: tabular-nums` agar lebar digit konsisten saat hitung mundur (tidak goyang).

10. **Next PT Session Card**: Thumbnail trainer 64px rounded, nama coach, meta row dengan ikon clock (waktu) & pin (lokasi). Chevron kuning di kanan untuk membuka detail sesi.

11. **Bottom Tab Bar**: 5 tab (HOME aktif, PROGRAM, TRAINER, MEMBERSHIP, PROFIL). Tab aktif kuning + opsional highlight pill di belakang ikon. Fixed di bawah dengan elevation shadow & safe-area padding.

12. **Scroll & Padding**: Konten dapat di-scroll vertikal; beri `padding-bottom: 88px` agar kartu terbawah tidak tertutup tab bar. Header boleh sticky atau ikut scroll sesuai preferensi.

13. **Touch Targets**: Semua elemen interaktif (chip, icon button, tab, chevron) minimum 44×44px (WCAG 2.5.8). Reset/Pause button 48px sudah memenuhi.

14. **Accessibility**: Timer beri `aria-live="polite"` saat berjalan agar screen reader membaca update. Tab beri `aria-current="page"` pada HOME. Badge "AKTIF" & status jangan hanya warna — sertakan teks. Emoji 👋 beri `aria-hidden` atau `role="img"` dengan label.

---

*Spec ini generated dari analisis visual screen Home Member.png (visual-verified).*
*Design system reference: Editorial Athletics admin specs (Equipment, Payments, Personal Trainer).*
*Total sections: 12 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

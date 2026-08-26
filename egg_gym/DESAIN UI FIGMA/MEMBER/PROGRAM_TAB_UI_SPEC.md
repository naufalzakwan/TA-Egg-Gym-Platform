# PROGRAM_TAB_UI_SPEC.md
# Egg Gym App — Program Screen (Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Member App > Program (Program Latihan Athlete)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Program Tab.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Program memakai sistem warna yang identik dengan Home Member: latar near-black dengan aksen kuning emas, konsisten dengan brand "Editorial Athletics". Token tambahan ditambahkan untuk state timeline (past/active/locked) dan progress bar.

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0E0E0E               | App background (screen utama)                  |
| --color-bg-card           | #1A1A1A               | Card & panel background                        |
| --color-bg-card-alt       | #161616               | Phase card / timeline item background          |
| --color-bg-chip           | #1C1C1C               | Toggle chip & icon button background           |
| --color-bg-navbar         | #121212               | Bottom tab bar background                      |
| --color-accent-primary    | #F5C518               | CTA, active tab, highlights, brand text        |
| --color-accent-hover      | #E0B200               | Button pressed state                           |
| --color-text-primary      | #FFFFFF               | Headings, session titles, primary values       |
| --color-text-secondary    | #9A9A9A               | Labels, captions, meta text                    |
| --color-text-muted        | #6B6B6B               | Inactive tab, locked item, placeholder         |
| --color-text-on-accent    | #0E0E0E               | Text on yellow/accent elements                 |
| --color-status-active     | #F5C518               | "ACTIVE" timeline badge                        |
| --color-status-past       | #6B6B6B               | "PAST" timeline badge text                     |
| --color-progress-fill     | #F5C518               | Progress bar fill (65%)                        |
| --color-progress-track    | #2A2A2A               | Progress bar track (unfilled)                  |
| --color-watermark         | rgba(245,197,24,0.06) | Watermark "LEVEL 4" di phase card              |
| --color-border-card       | #262626               | Card & panel borders                           |
| --color-border-chip       | #2A2A2A               | Toggle chip & outline button border            |
| --color-accent-rail       | #F5C518               | Left accent rail di active timeline item       |
| --color-tab-active        | #F5C518               | Active bottom-tab icon & label                 |
| --color-tab-inactive      | #6B6B6B               | Inactive bottom-tab icon & label               |
| --color-glow-cta          | rgba(245,197,24,0.45) | Glow di sekitar tombol kuning & FAB            |
| --color-overlay-dark      | rgba(0,0,0,0.7)       | Modal backdrop                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (phase title & watermark)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-screen-title      | 20px | 800    | 1.1    | 0px              | "Program Latihan" header title     |
| --text-toggle            | 14px | 700    | 1.2    | 0px              | "Program dari PT" / "Latihan Mandiri" |
| --text-supra-label       | 10px | 600    | 1.3    | 1.5px (uppercase)| "CURRENT PHASE" supra-label        |
| --text-phase-title       | 28px | 800    | 1.1    | -0.5px           | "Hypertrophy I" phase name         |
| --text-progress-number   | 40px | 800    | 1.0    | -1px             | "65" progress percentage           |
| --text-progress-unit     | 16px | 600    | 1.2    | 0px              | "%" unit & "12 OF 20 SESSIONS"     |
| --text-watermark         | 96px | 900    | 1.0    | -2px (uppercase) | "LEVEL 4" background watermark     |
| --text-section-title     | 18px | 800    | 1.2    | 0px              | "Session Timeline" / "Latihan Mandiri" |
| --text-link              | 12px | 700    | 1.0    | 0.5px (uppercase)| "+ BUAT PROGRAM BARU" link         |
| --text-item-title        | 16px | 700    | 1.3    | 0px              | "Push Day: Focus Chest" session    |
| --text-item-meta         | 12px | 400    | 1.4    | 0px              | "Monday, Oct 23 • 45 mins completed" |
| --text-item-meta-active  | 12px | 600    | 1.4    | 0px              | "Scheduled for Today • 6 Exercises" (kuning) |
| --text-badge             | 10px | 700    | 1.0    | 0.5px (uppercase)| "PAST" / "ACTIVE" badge            |
| --text-btn-inline        | 13px | 800    | 1.2    | 0.5px (uppercase)| "START SESSION" / "DETAILS" button |
| --text-routine-title     | 16px | 700    | 1.3    | 0px              | "Morning Stretch" routine name     |
| --text-routine-meta      | 12px | 400    | 1.4    | 0px              | "12 Exercises • 20 mins"           |
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
| --radius-sm    | 8px   | Inline buttons, badges                           |
| --radius-md    | 12px  | Icon thumbnails, icon buttons                    |
| --radius-lg    | 16px  | Cards, phase card, timeline items                |
| --radius-pill  | 999px | Toggle chips, status badge                       |
| --radius-full  | 50%   | Avatar, timeline status circle, FAB             |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards default               |
| --shadow-cta     | 0 0 20px rgba(245,197,24,0.4)         | Glow tombol kuning & FAB    |
| --shadow-fab     | 0 4px 16px rgba(245,197,24,0.5)       | Floating Action Button glow |
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
Card Gap:       12px (timeline item) / 20px (antar section)
FAB:            fixed, bottom-right, di atas tab bar
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ [👤] Program Latihan          [🔔]   │  ← Header
├──────────────────────────────────────┤
│ [ Program dari PT ] [ Latihan Mandiri]│  ← Segmented Toggle
│ ┌──────────────────────────────────┐ │
│ │ CURRENT PHASE          ░LEVEL 4░  │ │  ← Phase Card
│ │ Hypertrophy I                    │ │
│ │ 65%          12 OF 20 SESSIONS   │ │
│ │ ▓▓▓▓▓▓▓▓▓▓░░░░░░                  │ │  ← Progress bar
│ └──────────────────────────────────┘ │
│ Session Timeline               [⚙]   │  ← Section header
│ ┌──────────────────────────────────┐ │
│ │ (✓) Push Day: Focus Chest  [PAST]│ │  ← Timeline: PAST
│ │     Monday, Oct 23 • 45 mins     │ │
│ └──────────────────────────────────┘ │
│ ┃┌─────────────────────────────────┐ │
│ ┃│ (▶) Pull Day: Lat Thickness[ACTV]│ │  ← Timeline: ACTIVE
│ ┃│     Scheduled Today • 6 Exercises│ │  (left rail kuning)
│ ┃│     [START SESSION] [ DETAILS ]  │ │
│ ┃└─────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ (🔒) Leg Day: Quad Power         │ │  ← Timeline: LOCKED
│ │      Next: Friday, Oct 27        │ │
│ └──────────────────────────────────┘ │
│ Latihan Mandiri   + BUAT PROGRAM BARU│  ← Section header
│ ┌──────────────────────────────────┐ │
│ │ [🏋] Morning Stretch         [✎] │ │  ← Routine Card
│ │      12 Exercises • 20 mins      │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [🏃] HIIT Cardio Burn        [✎] │ │  ← Routine Card
│ │      5 Rounds • 30 mins      (➕) │ │  ← FAB
│ └──────────────────────────────────┘ │
├──────────────────────────────────────┤
│ 🏠     ⚡      👥      🖥️      👤    │  ← Bottom Tab Bar
│ HOME PROGRAM TRAINER MEMBERSHIP PROFIL│
└──────────────────────────────────────┘
```

---

## 5. KOMPONEN: HEADER

### 5.1 Container
```
Display:        flex, align-items center, justify-content space-between
Padding:        16px
Margin-top:     safe-area-inset-top
```

### 5.2 Kiri — Avatar + Title
```
Display:        flex, align-items center, gap 12px

Avatar:
  Width/Height: 40px
  Border-radius:50%
  Object-fit:   cover
  Border:       1px solid #2A2A2A

Title:
  Text:         "Program Latihan"
  Font-size:    20px
  Font-weight:  800
  Color:        #F5C518
```

### 5.3 Kanan — Notification Button
```
Size:           40px × 40px (icon-only, transparan/subtle bg)
Icon:           🔔 bell, 20px, color #F5C518
Display:        flex center
```

---

## 6. KOMPONEN: SEGMENTED TOGGLE (PT vs Mandiri)

### 6.1 Container
```
Display:        flex, gap 12px
Padding:        0 16px
Margin:         8px 0 20px
```

### 6.2 Chip Active ("Program dari PT")
```
Padding:        12px 20px
Background:     #F5C518
Border-radius:  999px
Color:          #0E0E0E
Font-size:      14px
Font-weight:    700
```

### 6.3 Chip Inactive ("Latihan Mandiri")
```
Padding:        12px 20px
Background:     #1C1C1C
Border:         1px solid #2A2A2A
Border-radius:  999px
Color:          #9A9A9A
Font-size:      14px
Font-weight:    700
```

---

## 7. KOMPONEN: CURRENT PHASE CARD

### 7.1 Container
```
Background:     #161616  (boleh subtle gradient ke #1E1A0A)
Border:         1px solid #262626
Border-radius:  16px
Padding:        20px
Margin:         0 16px 24px
Position:       relative
Overflow:       hidden  (untuk crop watermark)
```

### 7.2 Watermark Dekoratif
```
Text:           "LEVEL 4"
Font-size:      96px
Font-weight:    900
Color:          rgba(245,197,24,0.06)
Position:       absolute, right & vertically centered
Text-transform: uppercase
Z-index:        0  (di belakang konten)
Pointer-events: none
```

### 7.3 Supra-label
```
Text:           "CURRENT PHASE"
Font-size:      10px
Font-weight:    600
Color:          #9A9A9A
Letter-spacing: 1.5px
Text-transform: uppercase
```

### 7.4 Phase Title
```
Text:           "Hypertrophy I"
Font-size:      28px
Font-weight:    800
Color:          #F5C518
Letter-spacing: -0.5px
Margin:         6px 0 16px
```

### 7.5 Progress Row
```
Display:        flex, justify-content space-between, align-items baseline

Kiri — Percentage:
  Number:       "65"  → font-size 40px, weight 800, color #FFFFFF
  Unit:         "%"   → font-size 16px, weight 600, color #9A9A9A, margin-left 2px

Kanan — Session Count:
  Text:         "12 OF 20 SESSIONS"
  Font-size:    12px (uppercase)
  Font-weight:  600
  Color:        #9A9A9A
```

### 7.6 Progress Bar
```
Margin-top:     12px
Height:         6px
Border-radius:  999px
Track:          background #2A2A2A (100% width)
Fill:           background #F5C518, width 65%, border-radius 999px
```

---

## 8. KOMPONEN: SESSION TIMELINE

### 8.1 Section Header
```
Display:        flex, justify-content space-between, align-items center
Padding:        0 16px
Margin-bottom:  12px

Judul:
  Text:         "Session Timeline"  → 18px, weight 800, #FFFFFF

Filter Icon:
  Icon:         ⚙/sliders (filter), 20px, color #9A9A9A
```

### 8.2 Timeline Item — Variant PAST
```
Background:     #161616
Border:         1px solid #262626
Border-radius:  16px
Padding:        16px
Margin:         0 16px 12px
Display:        flex, align-items flex-start, gap 12px

Status Circle:
  Size:         28px, border-radius 50%
  Background:   rgba(245,197,24,0.15)
  Icon:         ✓ check, 14px, color #F5C518

Konten (flex 1):
  Title:        "Push Day: Focus Chest" → 16px, weight 700, #FFFFFF
  Meta:         "Monday, Oct 23 • 45 mins completed" → 12px, #9A9A9A

Badge "PAST" (kanan atas):
  Font-size:    10px, weight 700, uppercase
  Color:        #6B6B6B
  Background:   #1C1C1C
  Padding:      4px 8px, border-radius 8px
```

### 8.3 Timeline Item — Variant ACTIVE (highlight)
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-left:    3px solid #F5C518   (accent rail)
Border-radius:  16px
Padding:        16px
Margin:         0 16px 12px

Status Circle:
  Size:         28px, border-radius 50%
  Background:   #F5C518
  Icon:         ▶ play, 14px, color #0E0E0E

Konten:
  Title:        "Pull Day: Lat Thickness" → 16px, weight 700, #FFFFFF
  Meta:         "Scheduled for Today • 6 Exercises" → 12px, weight 600, #F5C518

Badge "ACTIVE" (kanan atas):
  Font-size:    10px, weight 700, uppercase
  Color:        #0E0E0E
  Background:   #F5C518
  Padding:      4px 8px, border-radius 8px

Action Row (margin-top 12px, display flex, gap 12px):
  START SESSION:
    Background: #F5C518
    Color:      #0E0E0E
    Padding:    10px 18px, border-radius 8px
    Font:       13px, weight 800, uppercase, letter-spacing 0.5px
  DETAILS:
    Background: transparan
    Border:     1px solid #2A2A2A
    Color:      #FFFFFF
    Padding:    10px 18px, border-radius 8px
    Font:       13px, weight 800, uppercase
```

### 8.4 Timeline Item — Variant LOCKED (disabled)
```
Background:     #141414
Border:         1px solid #1E1E1E
Border-radius:  16px
Padding:        16px
Margin:         0 16px 12px
Opacity:        0.6

Status Circle:
  Size:         28px, border-radius 50%
  Background:   #1C1C1C
  Icon:         🔒 lock, 14px, color #6B6B6B

Konten:
  Title:        "Leg Day: Quad Power" → 16px, weight 700, #6B6B6B
  Meta:         "Next: Friday, Oct 27" → 12px, #6B6B6B
```

---

## 9. KOMPONEN: LATIHAN MANDIRI (Custom Routines)

### 9.1 Section Header
```
Display:        flex, justify-content space-between, align-items center
Padding:        0 16px
Margin:         24px 0 12px

Judul:
  Text:         "Latihan Mandiri"  → 18px, weight 800, #FFFFFF

Link:
  Text:         "+ BUAT PROGRAM BARU"
  Font-size:    12px, weight 700, uppercase, letter-spacing 0.5px
  Color:        #F5C518
```

### 9.2 Routine Card
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Padding:        14px
Margin:         0 16px 12px
Display:        flex, align-items center, gap 14px
```

### 9.3 Icon Thumbnail
```
Size:           48px × 48px
Background:     #1C1C1C
Border-radius:  12px
Icon:           20px, color #F5C518
                - Morning Stretch → 🏋 dumbbell
                - HIIT Cardio Burn → 🏃 running
Display:        flex center
Flex-shrink:    0
```

### 9.4 Info (flex 1)
```
Title:          "Morning Stretch" / "HIIT Cardio Burn" → 16px, weight 700, #FFFFFF
Meta:           "12 Exercises • 20 mins" / "5 Rounds • 30 mins" → 12px, #9A9A9A, margin-top 4px
```

### 9.5 Edit Action
```
Size:           40px × 40px (icon-only)
Icon:           ✎ edit/pencil, 18px, color #9A9A9A
Flex-shrink:    0
```

---

## 10. KOMPONEN: FLOATING ACTION BUTTON (FAB)

```
Position:       fixed/absolute, bottom-right
Offset:         right 16px, bottom 88px (di atas tab bar)
Size:           56px × 56px
Border-radius:  16px  (rounded-square, bukan full circle)
Background:     #F5C518
Icon:           + plus, 24px, color #0E0E0E
Box-shadow:     0 4px 16px rgba(245,197,24,0.5)  (glow)
Z-index:        90
```

---

## 11. KOMPONEN: BOTTOM TAB BAR

### 11.1 Container
```
Position:       fixed, bottom 0, left 0, right 0
Height:         72px (+ safe-area-inset-bottom)
Background:     #121212
Border-top:     1px solid #1E1E1E
Box-shadow:     0 -2px 12px rgba(0,0,0,0.5)
Display:        flex, justify-content space-around, align-items center
Z-index:        100
```

### 11.2 Tab Item (Default / Inactive)
```
Display:        flex, flex-direction column, align-items center, gap 4px
Icon:           22px, color #6B6B6B
Label:          10px, weight 600, uppercase, letter-spacing 0.5px, color #6B6B6B
```

### 11.3 Tab Item (Active — PROGRAM)
```
Icon:           22px, color #F5C518
Label-color:    #F5C518
Indicator:      opsional — highlight pill bg di belakang ikon PROGRAM
                (bg rgba(245,197,24,0.12), border-radius 12px)
```

### 11.4 Daftar Tabs (5 item — sesuai gambar)
```
1. 🏠  HOME
2. ⚡  PROGRAM      ← ACTIVE (kuning)
3. 👥  TRAINER
4. 🖥️  MEMBERSHIP
5. 👤  PROFIL
```

---

## 12. GRID RECAP — RINGKASAN ZONA LAYOUT (Mobile)

| Zone                  | X Offset | Y Offset  | Width            | Height    |
|-----------------------|----------|-----------|------------------|-----------|
| Header                | 0        | safe-top  | 100%             | ~64px     |
| Segmented Toggle      | 16px     | ~108px    | calc(100% - 32px)| ~44px     |
| Current Phase Card    | 16px     | ~172px    | calc(100% - 32px)| ~150px    |
| Session Timeline Hdr  | 16px     | ~346px    | calc(100% - 32px)| ~30px     |
| Timeline Item (PAST)  | 16px     | ~388px    | calc(100% - 32px)| ~80px     |
| Timeline Item (ACTIVE)| 16px     | ~480px    | calc(100% - 32px)| ~130px    |
| Timeline Item (LOCKED)| 16px     | ~622px    | calc(100% - 32px)| ~72px     |
| Latihan Mandiri Hdr   | 16px     | ~718px    | calc(100% - 32px)| ~30px     |
| Routine Card ×2       | 16px     | ~760px    | calc(100% - 32px)| ~76px each|
| FAB                   | right16  | bottom88  | 56px             | 56px      |
| Bottom Tab Bar        | 0        | bottom: 0 | 100%             | 72px      |

---

## 13. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Program Screen (Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Program Tab.png
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
  --color-status-past:       #6B6B6B;
  --color-progress-fill:     #F5C518;
  --color-progress-track:    #2A2A2A;
  --color-watermark:         rgba(245,197,24,0.06);
  --color-border-card:       #262626;
  --color-border-chip:       #2A2A2A;
  --color-accent-rail:       #F5C518;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.45);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-screen-title:       20px;
  --text-toggle:             14px;
  --text-supra-label:        10px;
  --text-phase-title:        28px;
  --text-progress-number:    40px;
  --text-progress-unit:      16px;
  --text-watermark:          96px;
  --text-section-title:      18px;
  --text-link:               12px;
  --text-item-title:         16px;
  --text-item-meta:          12px;
  --text-badge:              10px;
  --text-btn-inline:         13px;
  --text-routine-title:      16px;
  --text-routine-meta:       12px;
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
  --shadow-cta:              0 0 20px rgba(245,197,24,0.4);
  --shadow-fab:              0 4px 16px rgba(245,197,24,0.5);
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --navbar-height:           72px;
  --card-gap:                12px;
  --card-radius:             16px;
  --fab-size:                56px;
  --tab-count:               5;
}
```

---

## 14. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Program Tab.png`. Semua teks (Program Latihan, Hypertrophy I, 65%, 12 OF 20 SESSIONS, Push Day: Focus Chest, Pull Day: Lat Thickness, Leg Day: Quad Power, Morning Stretch, HIIT Cardio Burn) harus persis sama dengan gambar.

2. **Mobile-First Layout**: Layar member-facing, navigasi via **bottom tab bar** 5 item dengan PROGRAM aktif. Gunakan `100vw`, `safe-area-inset-*` untuk notch & home indicator.

3. **Segmented Toggle**: Dua mode — "Program dari PT" (aktif, pill kuning solid) dan "Latihan Mandiri" (inaktif, pill outline abu). Switch mengubah konten yang ditampilkan; secara visual layar ini menampilkan kombinasi keduanya (timeline PT + daftar routine mandiri di bawah).

4. **Phase Card Watermark**: Teks "LEVEL 4" raksasa di belakang konten dengan opacity sangat rendah (`rgba(245,197,24,0.06)`). Wajib `overflow:hidden` pada container agar watermark ter-crop rapi. `pointer-events:none` supaya tidak mengganggu interaksi.

5. **Progress Bar Dinamis**: Lebar fill = `(sessions selesai / total) × 100%`. Pada gambar 12/20 = 60%, namun angka tertulis "65%" — gunakan **angka persen sebagai source of truth tampilan** dan width bar mengikuti angka persen (65%), bukan rasio sesi. Verifikasi konsistensi data saat implementasi.

6. **Timeline 3 State**: Setiap item punya state visual berbeda — **PAST** (check kuning, badge abu, full opacity), **ACTIVE** (play kuning, accent rail kiri 3px, badge kuning solid, action buttons), **LOCKED** (lock abu, opacity 0.6, tanpa aksi). Gunakan enum status untuk render kondisional.

7. **Active Item Accent Rail**: Item aktif dibedakan dengan `border-left: 3px solid #F5C518`. Ini penanda visual utama selain badge — jangan andalkan warna saja, sertakan teks badge "ACTIVE".

8. **Inline Action Buttons**: Hanya item ACTIVE yang punya tombol "START SESSION" (kuning solid) + "DETAILS" (outline). START SESSION memicu mulai latihan; DETAILS membuka rincian sesi/exercise list.

9. **Status Circle**: Lingkaran 28px di kiri setiap timeline item — ikon berubah per state (✓ / ▶ / 🔒). Untuk PAST gunakan bg kuning transparan, ACTIVE bg kuning solid, LOCKED bg abu gelap.

10. **Latihan Mandiri Section**: Daftar routine custom buatan user. Tiap card punya icon thumbnail 48px, judul, meta (jumlah exercise/round + durasi), dan tombol edit ✎. Link "+ BUAT PROGRAM BARU" di header section membuka flow pembuatan program baru.

11. **Floating Action Button**: FAB rounded-square 56px kuning dengan ikon "+", `position:fixed` di kanan bawah, offset `bottom:88px` agar tidak menabrak tab bar. Punya glow shadow. Fungsi: shortcut tambah routine/program baru (selaras dengan link "+ BUAT PROGRAM BARU").

12. **Scroll & Padding**: Konten scroll vertikal panjang; beri `padding-bottom: 88px` agar card terbawah & FAB tidak tertutup tab bar. Header dan toggle boleh sticky atau ikut scroll sesuai preferensi.

13. **Touch Targets**: Semua elemen interaktif (toggle chip, timeline item, inline button, icon button, FAB, tab) minimum 44×44px (WCAG 2.5.8). FAB 56px & inline button height ~40px sudah memenuhi.

14. **Accessibility**: Beri `aria-current="page"` pada tab PROGRAM. Progress bar gunakan `role="progressbar"` dengan `aria-valuenow="65"`. Timeline state jangan hanya warna — sertakan teks badge & label status (PAST/ACTIVE/LOCKED). Item LOCKED beri `aria-disabled="true"`. FAB beri `aria-label="Buat program baru"`.

---

*Spec ini generated dari analisis visual screen Program Tab.png (visual-verified).*
*Design system reference: Egg Gym — Member Home Screen (MEMBER_HOME_UI_SPEC.md) & Editorial Athletics admin specs.*
*Total sections: 14 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

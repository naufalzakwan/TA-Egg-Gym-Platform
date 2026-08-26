# SESSION_DETAIL_PT_UI_SPEC.md
# Egg Gym App — Session Detail Screen (PT-Controlled, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Member App > Program > Session Detail (PT)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Session Detail (PT).png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Session Detail mewarisi sistem warna identik dengan Program & Home Member: latar near-black dengan aksen kuning emas. Token tambahan ditambahkan untuk state exercise (completed/active/locked), info banner PT, strikethrough completed, dan kartu supervising trainer.

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0E0E0E               | App background (screen utama)                  |
| --color-bg-card           | #1A1A1A               | Card & panel background                        |
| --color-bg-card-alt       | #161616               | Focus card / exercise item background          |
| --color-bg-chip           | #1C1C1C               | Read-Only pill & icon button background        |
| --color-bg-navbar         | #121212               | Bottom tab bar background                      |
| --color-bg-banner         | rgba(245,197,24,0.08) | Info banner PT background (kuning transparan)  |
| --color-accent-primary    | #F5C518               | CTA, active state, highlights, brand text      |
| --color-accent-hover      | #E0B200               | Pressed state                                  |
| --color-text-primary      | #FFFFFF               | Headings, exercise titles, primary values       |
| --color-text-secondary    | #9A9A9A               | Labels, captions, meta text                    |
| --color-text-muted        | #6B6B6B               | Inactive tab, locked item, placeholder         |
| --color-text-on-accent    | #0E0E0E               | Text on yellow/accent elements                 |
| --color-status-completed  | #F5C518               | Check circle + "COMPLETED" label               |
| --color-status-active     | #F5C518               | Active exercise title & dot indicator          |
| --color-status-locked     | #6B6B6B               | Lock icon & locked exercise text               |
| --color-progress-fill     | #F5C518               | Session progress bar fill (75%)                |
| --color-progress-track    | #2A2A2A               | Progress bar track (unfilled)                  |
| --color-watermark         | rgba(245,197,24,0.05) | Watermark "POWER" di focus card                |
| --color-strikethrough     | #6B6B6B               | Garis coret judul exercise completed           |
| --color-border-card       | #262626               | Card & panel borders                           |
| --color-border-banner     | rgba(245,197,24,0.30) | Border info banner PT                          |
| --color-border-active     | #F5C518               | Border kartu exercise aktif (highlight)        |
| --color-accent-rail       | #F5C518               | Left accent rail di focus card                 |
| --color-tab-active        | #F5C518               | Active bottom-tab icon & label (PROGRAM)       |
| --color-tab-inactive      | #6B6B6B               | Inactive bottom-tab icon & label               |
| --color-glow-cta          | rgba(245,197,24,0.45) | Glow di sekitar elemen kuning                  |
| --color-overlay-dark      | rgba(0,0,0,0.7)       | Modal backdrop                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (focus title & watermark)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-screen-title      | 20px | 800    | 1.1    | 0px              | "Session Detail" header title      |
| --text-supra-label       | 10px | 600    | 1.3    | 1.5px (uppercase)| "CURRENT FOCUS" / "SUPERVISING TRAINER" |
| --text-focus-title       | 26px | 800    | 1.15   | -0.5px           | "Upper Body Hypertrophy" focus name |
| --text-progress-label    | 14px | 600    | 1.2    | 0px              | "Session Progress" label           |
| --text-progress-number   | 22px | 800    | 1.0    | -0.5px           | "75%" progress percentage          |
| --text-progress-meta     | 11px | 600    | 1.3    | 0.5px (uppercase)| "6 OF 8 EXERCISES" / "45M ELAPSED" |
| --text-watermark         | 88px | 900    | 1.0    | -2px (uppercase) | "POWER" background watermark       |
| --text-banner            | 13px | 500    | 1.5    | 0px              | Teks info banner PT                |
| --text-section-title     | 18px | 800    | 1.2    | 0px              | "Workout Plan" section title       |
| --text-pill-badge        | 11px | 600    | 1.0    | 0px              | "Read-Only" pill                   |
| --text-exercise-title    | 16px | 700    | 1.3    | 0px              | "Barbell Bench Press" exercise name |
| --text-exercise-active   | 18px | 800    | 1.25   | -0.3px           | "Overhead Press" judul exercise aktif (kuning) |
| --text-status-label      | 10px | 700    | 1.0    | 0.5px (uppercase)| "COMPLETED" label exercise         |
| --text-exercise-desc     | 12px | 400    | 1.5    | 0px              | Deskripsi cue exercise aktif       |
| --text-stat-label        | 9px  | 600    | 1.2    | 0.8px (uppercase)| "SETS" / "TARGET REPS" / "WEIGHT"  |
| --text-stat-value        | 20px | 800    | 1.0    | -0.5px           | "4", "8-10", "80" stat value       |
| --text-stat-unit         | 12px | 600    | 1.2    | 0px              | "/ 4" denominator & "kg" unit      |
| --text-locked-meta       | 11px | 500    | 1.3    | 0px              | "4 SETS • 8 REPS" locked meta      |
| --text-trainer-name      | 16px | 700    | 1.2    | 0px              | "Coach Marcus Vane" trainer name   |
| --text-trainer-role      | 12px | 600    | 1.3    | 0px              | "Level 3 Senior PT" (kuning)       |
| --text-tab-label         | 10px | 600    | 1.2    | 0.5px (uppercase)| Bottom tab labels                  |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Badge padding, tiny gaps                         |
| --space-sm     | 8px   | Icon-text gap, stat inner gap                    |
| --space-md     | 12px  | Inter-element gap, status circle ke kartu        |
| --space-base   | 16px  | Screen horizontal padding, card padding          |
| --space-lg     | 20px  | Card-to-card vertical gap, focus card padding    |
| --space-xl     | 24px  | Section separation                               |
| --space-2xl    | 32px  | Major block separation                           |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Badge, status label                              |
| --radius-md    | 12px  | Info banner, exercise cards                      |
| --radius-lg    | 16px  | Focus card, trainer card                         |
| --radius-pill  | 999px | Read-Only pill                                   |
| --radius-full  | 50%   | Avatar, status circle, chat icon button         |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards default               |
| --shadow-active  | 0 0 16px rgba(245,197,24,0.18)        | Glow kartu exercise aktif   |
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
Card Gap:       12px (exercise item) / 24px (antar section)
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ [←] Session Detail            [⤴]    │  ← Header (back + share)
├──────────────────────────────────────┤
│ ┃ CURRENT FOCUS         ░░POWER░░    │ │
│ ┃ Upper Body                         │ │  ← Focus Card (rail kuning)
│ ┃ Hypertrophy                        │ │
│ ┃ Session Progress          75%      │ │
│ ┃ ▓▓▓▓▓▓▓▓▓▓▓▓░░░░                   │ │  ← Progress bar
│ ┃ 6 OF 8 EXERCISES    45M ELAPSED    │ │
│ ┌──────────────────────────────────┐ │
│ │ (i) Pelatih Anda mengontrol...    │ │  ← Info Banner PT
│ └──────────────────────────────────┘ │
│ WORKOUT PLAN              [Read-Only] │  ← Section header + pill
│ (✓)┌─────────────────────────────────┐│
│    │ ~Barbell Bench Press~ COMPLETED ││  ← Exercise: COMPLETED
│    │ SETS 4/4  TGT 8-10  WEIGHT 80kg ││
│    └─────────────────────────────────┘│
│ (✓)┌─────────────────────────────────┐│
│    │ ~Incline DB Fly~      COMPLETED ││  ← Exercise: COMPLETED
│    │ SETS 3/3   TARGET REPS 12       ││
│    └─────────────────────────────────┘│
│ (○)┌─────────────────────────────────┐│
│    │ Overhead Press               •  ││  ← Exercise: ACTIVE
│    │ Focus on full lock out...       ││  (judul kuning, border kuning)
│    │ SETS 2/4   TARGET REPS 10       ││
│    └─────────────────────────────────┘│
│ (🔒)┌────────────────────────────────┐│
│    │ Weighted Dips                   ││  ← Exercise: LOCKED
│    │ 4 SETS • 8 REPS                 ││
│    └─────────────────────────────────┘│
│ SUPERVISING TRAINER                   │  ← Section header
│ ┌──────────────────────────────────┐ │
│ │ [👤] Coach Marcus Vane       [💬]│ │  ← Trainer Card
│ │      Level 3 Senior PT           │ │
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

### 5.2 Kiri — Back + Title
```
Display:        flex, align-items center, gap 12px

Back Button:
  Icon:         ← arrow-left, 22px, color #F5C518
  Size:         40px × 40px touch target

Title:
  Text:         "Session Detail"
  Font-size:    20px
  Font-weight:  800
  Color:        #F5C518
```

### 5.3 Kanan — Share Button
```
Size:           40px × 40px (icon-only, transparan/subtle bg)
Icon:           ⤴ share/network, 20px, color #F5C518
Display:        flex center
```

---

## 6. KOMPONEN: CURRENT FOCUS CARD

### 6.1 Container
```
Background:     #161616  (boleh subtle gradient ke #1E1A0A)
Border:         1px solid #262626
Border-left:    3px solid #F5C518   (accent rail)
Border-radius:  16px
Padding:        20px
Margin:         8px 16px 20px
Position:       relative
Overflow:       hidden  (untuk crop watermark)
```

### 6.2 Watermark Dekoratif
```
Text:           "POWER"
Font-size:      88px
Font-weight:    900
Color:          rgba(245,197,24,0.05)
Position:       absolute, top-right, melewati tepi kanan card
Text-transform: uppercase
Z-index:        0
Pointer-events: none
```

### 6.3 Supra-label
```
Text:           "CURRENT FOCUS"
Font-size:      10px, weight 600, color #9A9A9A
Letter-spacing: 1.5px, uppercase
```

### 6.4 Focus Title
```
Text:           "Upper Body Hypertrophy"  (wrap 2 baris)
Font-size:      26px, weight 800, color #FFFFFF
Letter-spacing: -0.5px
Margin:         6px 0 18px
```

### 6.5 Progress Row (label + percentage)
```
Display:        flex, justify-content space-between, align-items baseline

Kiri — Label:
  Text:         "Session Progress" → 14px, weight 600, color #9A9A9A

Kanan — Percentage:
  Text:         "75%" → 22px, weight 800, color #F5C518
```

### 6.6 Progress Bar
```
Margin:         10px 0 10px
Height:         6px
Border-radius:  999px
Track:          background #2A2A2A (100% width)
Fill:           background #F5C518, width 75%, border-radius 999px
```

### 6.7 Meta Row
```
Display:        flex, justify-content space-between
Font-size:      11px, weight 600, color #9A9A9A, uppercase, letter-spacing 0.5px
Kiri:           "6 OF 8 EXERCISES"
Kanan:          "45M ELAPSED"
```

---

## 7. KOMPONEN: INFO BANNER (PT CONTROL NOTICE)

```
Background:     rgba(245,197,24,0.08)
Border:         1px solid rgba(245,197,24,0.30)
Border-radius:  12px
Padding:        14px 16px
Margin:         0 16px 24px
Display:        flex, align-items flex-start, gap 12px

Icon:
  Icon:         (i) info-circle, 18px, color #F5C518
  Flex-shrink:  0

Teks:
  Text:         "Pelatih Anda mengontrol daftar periksa ini. Status latihan
                 akan diperbarui secara otomatis saat pelatih memberikan verifikasi."
  Font-size:    13px, weight 500, color #D6C58A (kuning pucat), line-height 1.5
```

---

## 8. KOMPONEN: WORKOUT PLAN

### 8.1 Section Header
```
Display:        flex, justify-content space-between, align-items center
Padding:        0 16px
Margin-bottom:  16px

Judul:
  Text:         "Workout Plan"  → 18px, weight 800, #FFFFFF

Read-Only Pill:
  Text:         "Read-Only"  → 11px, weight 600, color #9A9A9A
  Background:   #1C1C1C
  Border:       1px solid #2A2A2A
  Padding:      6px 12px, border-radius 999px
```

### 8.2 Exercise Item — Variant COMPLETED
```
Layout:         status circle (kiri, di luar card) + card (flex 1)
Margin:         0 16px 12px
Display:        flex, align-items flex-start, gap 12px

Status Circle:
  Size:         24px, border-radius 50%
  Background:   #F5C518
  Icon:         ✓ check, 13px, color #0E0E0E

Card:
  Background:   #161616
  Border:       1px solid #262626
  Border-radius:12px
  Padding:      16px

  Header Row (flex, space-between, align center):
    Title:      "Barbell Bench Press" / "Incline DB Fly"
                → 16px, weight 700, color #6B6B6B, text-decoration line-through
    Label:      "COMPLETED" → 10px, weight 700, uppercase, color #F5C518

  Stats Row (flex, gap 24px, margin-top 12px):
    Stat block (label di atas, value di bawah):
      Label:    9px, weight 600, uppercase, letter-spacing 0.8px, color #9A9A9A
      Value:    20px, weight 800, color #FFFFFF
      Denom/Unit: 12px, weight 600, color #9A9A9A  (mis. "/ 4", "kg")
    Item 1 (Barbell): SETS 4/4 • TARGET REPS 8-10 • WEIGHT 80kg
    Item 2 (Incline): SETS 3/3 • TARGET REPS 12
```

### 8.3 Exercise Item — Variant ACTIVE (highlight)
```
Status Circle:
  Size:         24px, border-radius 50%
  Background:   transparan
  Border:       2px solid #9A9A9A  (outline kosong, belum selesai)

Card:
  Background:   #1A1A1A
  Border:       1px solid #F5C518   (highlight border kuning penuh)
  Border-radius:12px
  Padding:      18px 16px
  Box-shadow:   0 0 16px rgba(245,197,24,0.18)  (glow halus)

  Header Row (flex, space-between, align center):
    Title:      "Overhead Press" → 18px, weight 800, color #F5C518
    Dot:        • 8px circle, background #F5C518 (indikator "now active")

  Description:
    Text:       "Focus on full lock out and controlled eccentric movement.
                 Keep core tight."
    Font:       12px, weight 400, color #9A9A9A, line-height 1.5
    Margin:     8px 0 14px

  Stats Row (flex, gap 24px):
    SETS 2/4 • TARGET REPS 10  (format sama seperti 8.2)
```

### 8.4 Exercise Item — Variant LOCKED (disabled)
```
Status Circle:
  Size:         24px, border-radius 50%
  Background:   #1C1C1C
  Icon:         🔒 lock, 13px, color #6B6B6B

Card:
  Background:   #141414
  Border:       1px solid #1E1E1E
  Border-radius:12px
  Padding:      16px
  Opacity:      0.6

  Title:        "Weighted Dips" → 16px, weight 700, color #6B6B6B
  Meta:         "4 SETS • 8 REPS" → 11px, weight 500, color #6B6B6B, uppercase
```

---

## 9. KOMPONEN: SUPERVISING TRAINER

### 9.1 Section Header (Supra-label)
```
Text:           "SUPERVISING TRAINER"
Font-size:      10px, weight 600, uppercase, letter-spacing 1.5px
Color:          #6B6B6B
Padding:        0 16px
Margin:         24px 0 12px
```

### 9.2 Trainer Card
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Padding:        14px 16px
Margin:         0 16px
Display:        flex, align-items center, gap 14px
```

### 9.3 Avatar
```
Size:           48px × 48px
Border-radius:  50%
Object-fit:     cover
Border:         1px solid #2A2A2A
Flex-shrink:    0
```

### 9.4 Info (flex 1)
```
Name:           "Coach Marcus Vane" → 16px, weight 700, color #FFFFFF
Role:           "Level 3 Senior PT" → 12px, weight 600, color #F5C518, margin-top 2px
```

### 9.5 Chat Action
```
Size:           44px × 44px
Background:     #1C1C1C
Border-radius:  50%  (atau 12px rounded-square)
Icon:           💬 chat-bubble, 18px, color #FFFFFF
Flex-shrink:    0
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
| Header                  | 0        | safe-top  | 100%             | ~64px     |
| Current Focus Card      | 16px     | ~116px    | calc(100% - 32px)| ~200px    |
| Info Banner PT          | 16px     | ~332px    | calc(100% - 32px)| ~76px     |
| Workout Plan Header     | 16px     | ~432px    | calc(100% - 32px)| ~30px     |
| Exercise (COMPLETED ×2) | 16px     | ~478px    | calc(100% - 32px)| ~92px each|
| Exercise (ACTIVE)       | 16px     | ~674px    | calc(100% - 32px)| ~150px    |
| Exercise (LOCKED)       | 16px     | ~836px    | calc(100% - 32px)| ~72px     |
| Supervising Trainer Hdr | 16px     | ~932px    | calc(100% - 32px)| ~30px     |
| Trainer Card            | 16px     | ~974px    | calc(100% - 32px)| ~76px     |
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px      |

*Catatan: konten melebihi tinggi viewport (932px) → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 12. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Session Detail Screen (PT-Controlled, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Session Detail (PT).png
   Generated: 2026-06-27
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:        #0E0E0E;
  --color-bg-card:           #1A1A1A;
  --color-bg-card-alt:       #161616;
  --color-bg-chip:           #1C1C1C;
  --color-bg-navbar:         #121212;
  --color-bg-banner:         rgba(245,197,24,0.08);
  --color-accent-primary:    #F5C518;
  --color-accent-hover:      #E0B200;
  --color-text-primary:      #FFFFFF;
  --color-text-secondary:    #9A9A9A;
  --color-text-muted:        #6B6B6B;
  --color-text-on-accent:    #0E0E0E;
  --color-status-completed:  #F5C518;
  --color-status-active:     #F5C518;
  --color-status-locked:     #6B6B6B;
  --color-progress-fill:     #F5C518;
  --color-progress-track:    #2A2A2A;
  --color-watermark:         rgba(245,197,24,0.05);
  --color-strikethrough:     #6B6B6B;
  --color-border-card:       #262626;
  --color-border-banner:     rgba(245,197,24,0.30);
  --color-border-active:     #F5C518;
  --color-accent-rail:       #F5C518;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.45);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-screen-title:       20px;
  --text-supra-label:        10px;
  --text-focus-title:        26px;
  --text-progress-label:     14px;
  --text-progress-number:    22px;
  --text-progress-meta:      11px;
  --text-watermark:          88px;
  --text-banner:             13px;
  --text-section-title:      18px;
  --text-pill-badge:         11px;
  --text-exercise-title:     16px;
  --text-exercise-active:    18px;
  --text-status-label:       10px;
  --text-exercise-desc:      12px;
  --text-stat-label:         9px;
  --text-stat-value:         20px;
  --text-stat-unit:          12px;
  --text-locked-meta:        11px;
  --text-trainer-name:       16px;
  --text-trainer-role:       12px;
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
  --shadow-active:           0 0 16px rgba(245,197,24,0.18);
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --navbar-height:           72px;
  --card-gap:                12px;
  --card-radius:             16px;
  --tab-count:               5;
}
```

---

## 13. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Session Detail (PT).png`. Semua teks (Session Detail, Upper Body Hypertrophy, 75%, 6 OF 8 EXERCISES, 45M ELAPSED, Barbell Bench Press, Incline DB Fly, Overhead Press, Weighted Dips, Coach Marcus Vane, Level 3 Senior PT) harus persis sama dengan gambar.

2. **Mobile-First Layout**: Layar member-facing yang dibuka dari tab Program → konteks PT. Navigasi via header back button (kembali ke Session Timeline) dan bottom tab bar 5 item dengan PROGRAM tetap aktif. Gunakan `safe-area-inset-*`.

3. **PT-Controlled / Read-Only**: Ini state kunci layar. Seluruh `Workout Plan` bersifat read-only bagi member (badge "Read-Only"). Member TIDAK bisa mencentang/mengubah status; verifikasi datang dari trainer. Disable semua kontrol edit dan komunikasikan via info banner.

4. **Info Banner Semantik**: Banner kuning transparan menjelaskan kontrol PT. Gunakan `role="status"` agar dibacakan screen reader. Jangan jadikan dismissible bila status read-only masih berlaku.

5. **Focus Card Watermark**: Teks "POWER" raksasa di belakang konten, opacity sangat rendah (`rgba(245,197,24,0.05)`). Wajib `overflow:hidden` pada container agar ter-crop di tepi kanan. `pointer-events:none`.

6. **Progress = Session-level**: Progress bar di focus card adalah progres sesi keseluruhan (75%), bukan per-exercise. Width fill mengikuti angka persen. Meta "6 OF 8 EXERCISES" dan "45M ELAPSED" bersifat informatif/live (timer berjalan).

7. **Exercise 3 State (enum)**: Setiap exercise punya state visual berbeda — COMPLETED (circle check kuning, judul strikethrough abu, label "COMPLETED", full data), ACTIVE (circle outline kosong, border kartu kuning + glow, judul kuning + dot, ada deskripsi cue), LOCKED (circle lock, opacity 0.6, hanya meta ringkas). Gunakan enum status untuk render kondisional.

8. **Status Circle di Luar Card**: Berbeda dari Program Tab, lingkaran status (24px) diletakkan di kiri di luar kartu exercise (gaya checklist/timeline), bukan di dalam. Jaga alignment `flex-start` agar circle sejajar baris judul.

9. **Active Exercise Highlight**: Item aktif dibedakan via `border:1px solid #F5C518` + glow + judul kuning + dot indicator + deskripsi cue. Jangan andalkan warna saja; circle outline kosong menandakan "belum selesai / sedang berjalan".

10. **Stat Block Layout**: Tiap exercise menampilkan baris stat (SETS, TARGET REPS, WEIGHT). Format value besar (`20px/800`) dengan denominator/unit kecil abu (`/ 4`, `kg`). Jumlah kolom stat bisa berbeda per exercise (Barbell punya WEIGHT, Incline tidak) — render dinamis dari data, sembunyikan kolom kosong.

11. **Strikethrough Completed**: Judul exercise selesai diberi `text-decoration:line-through` + warna `#6B6B6B`. Pastikan kontras tetap terbaca; jangan turunkan opacity seluruh kartu COMPLETED (berbeda dengan LOCKED yang opacity 0.6).

12. **Supervising Trainer Card**: Menampilkan PT yang mengawasi sesi — avatar, nama, role/level, dan tombol chat. Tombol chat membuka thread komunikasi member↔trainer. Beri `aria-label="Chat dengan Coach Marcus Vane"`.

13. **Scroll & Padding**: Konten lebih tinggi dari viewport → scroll vertikal. Beri `padding-bottom:88px` agar trainer card & elemen terbawah tidak tertutup tab bar. Header boleh sticky agar back button selalu terjangkau.

14. **Accessibility**: Beri `aria-current="page"` pada tab PROGRAM. Progress bar gunakan `role="progressbar"` dengan `aria-valuenow="75"`. State exercise jangan hanya warna — sertakan label teks (COMPLETED) dan status semantik (`aria-checked`/`aria-disabled`). Item LOCKED beri `aria-disabled="true"`. Touch target minimum 44×44px untuk back, share, chat, dan tab.

---

*Spec ini generated dari analisis visual screen Session Detail (PT).png (visual-verified).*
*Design system reference: Egg Gym — Program Screen (PROGRAM_TAB_UI_SPEC.md) & Member Home (MEMBER_HOME_UI_SPEC.md).*
*Total sections: 14 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

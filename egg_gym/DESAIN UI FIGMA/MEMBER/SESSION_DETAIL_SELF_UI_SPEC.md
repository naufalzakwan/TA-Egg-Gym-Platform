# SESSION_DETAIL_SELF_UI_SPEC.md
# Egg Gym App — Session Detail Screen (Self / Latihan Mandiri, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Member App > Program > Latihan Mandiri > Session Detail (Self-managed)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Session Detail (Self).png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Session Detail (Self) mewarisi sistem warna identik dengan Program & Session Detail (PT): latar near-black dengan aksen kuning emas. Berbeda dari versi PT, layar ini bersifat editable, sehingga ditambahkan token untuk checkbox interaktif (checked/unchecked), stat chip editable, dashed add-button, dan selection menu (Edit/Delete).

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0E0E0E               | App background (screen utama)                  |
| --color-bg-card           | #1A1A1A               | Movement card & panel background               |
| --color-bg-card-alt       | #161616               | Focus card / inner block background            |
| --color-bg-chip           | #1C1C1C               | Stat chip & icon button background             |
| --color-bg-chip-active    | #2A2410               | Stat chip pada movement aktif (kuning gelap)   |
| --color-bg-navbar         | #121212               | Bottom tab bar background                      |
| --color-accent-primary    | #F5C518               | CTA, checkbox checked, active state, brand text|
| --color-accent-hover      | #E0B200               | Pressed state                                  |
| --color-text-primary      | #FFFFFF               | Headings, movement titles, primary values       |
| --color-text-secondary    | #9A9A9A               | Labels, captions, meta text                    |
| --color-text-muted        | #6B6B6B               | Inactive tab, placeholder, dashed border text  |
| --color-text-on-accent    | #0E0E0E               | Text on yellow/accent elements                 |
| --color-checkbox-on       | #F5C518               | Checkbox checked background                    |
| --color-checkbox-off      | #3A3A3A               | Checkbox unchecked border                      |
| --color-stat-value        | #F5C518               | Nilai stat pada movement aktif (8-10, 85kg)    |
| --color-stat-value-idle   | #FFFFFF               | Nilai stat pada movement idle                  |
| --color-watermark         | rgba(245,197,24,0.05) | Watermark "ELITE" di focus card                |
| --color-border-card       | #262626               | Card & panel borders                           |
| --color-border-active     | #F5C518               | Border + accent rail movement aktif (highlight)|
| --color-border-dashed     | #4A4220               | Dashed border "Tambah Gerakan"                 |
| --color-accent-rail       | #F5C518               | Left accent rail di focus card & movement aktif|
| --color-tab-active        | #F5C518               | Active bottom-tab icon & label (PROGRAM)       |
| --color-tab-inactive      | #6B6B6B               | Inactive bottom-tab icon & label               |
| --color-glow-cta          | rgba(245,197,24,0.45) | Glow di sekitar FAB & elemen kuning            |
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
| --text-screen-title      | 20px | 800    | 1.1    | 0.5px (uppercase)| "LATIHAN MANDIRI" header title     |
| --text-supra-label       | 10px | 600    | 1.3    | 1.5px (uppercase)| "CURRENT FOCUS" supra-label        |
| --text-focus-title       | 34px | 800    | 1.1    | -0.5px           | "Hypertrophy A1 Session" focus name |
| --text-focus-number      | 28px | 800    | 1.0    | -0.5px           | "45" / "8" angka metrik focus      |
| --text-focus-unit        | 13px | 700    | 1.2    | 0.5px (uppercase)| "MIN" / "EXE" unit                 |
| --text-focus-meta        | 10px | 600    | 1.3    | 0.8px (uppercase)| "EST. DURATION" / "MOVEMENTS"      |
| --text-watermark         | 88px | 900    | 1.0    | -2px (uppercase) | "ELITE" background watermark       |
| --text-section-title     | 18px | 800    | 1.2    | 0px              | "Movement Checklist" section title |
| --text-link              | 11px | 700    | 1.0    | 0.8px (uppercase)| "HOLD TO EDIT" link                |
| --text-movement-title    | 16px | 700    | 1.3    | 0px              | "Barbell Back Squat" movement name |
| --text-movement-meta     | 12px | 400    | 1.4    | 0px              | "Compound • Quadriceps" meta       |
| --text-stat-label        | 8px  | 600    | 1.2    | 0.8px (uppercase)| "SETS" / "REPS" / "LOAD" chip label|
| --text-stat-value        | 15px | 800    | 1.0    | 0px              | "4" / "8-10" / "85kg" chip value   |
| --text-add-btn           | 14px | 700    | 1.2    | 0px              | "Tambah Gerakan" button            |
| --text-menu-label        | 10px | 600    | 1.3    | 0.8px (uppercase)| "ACTIVE SELECTION MENU"            |
| --text-menu-btn          | 14px | 700    | 1.2    | 0px              | "Edit" / "Delete" button           |
| --text-tab-label         | 10px | 600    | 1.2    | 0.5px (uppercase)| Bottom tab labels                  |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Chip padding, tiny gaps                          |
| --space-sm     | 8px   | Icon-text gap, chip inner gap                    |
| --space-md     | 12px  | Inter-element gap, checkbox ke konten            |
| --space-base   | 16px  | Screen horizontal padding, card padding          |
| --space-lg     | 20px  | Card-to-card vertical gap, focus card padding    |
| --space-xl     | 24px  | Section separation                               |
| --space-2xl    | 32px  | Major block separation                           |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Stat chip, checkbox, menu button                 |
| --radius-md    | 12px  | Thumbnail movement, icon buttons                 |
| --radius-lg    | 16px  | Focus card, movement cards, selection menu       |
| --radius-pill  | 999px | (jika ada pill)                                  |
| --radius-full  | 50%   | Add-icon circle, FAB                             |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards default               |
| --shadow-active  | 0 0 16px rgba(245,197,24,0.18)        | Glow movement aktif         |
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
Card Gap:       12px (movement card) / 24px (antar section)
FAB:            fixed, bottom-right, di atas tab bar
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ [←] LATIHAN MANDIRI            [⋮]   │  ← Header (back + overflow)
├──────────────────────────────────────┤
│ ┃ CURRENT FOCUS         ░░ELITE░░    │ │
│ ┃ Hypertrophy                        │ │  ← Focus Card (rail kuning)
│ ┃ A1 Session                         │ │
│ ┃ 45 MIN        8 EXE                │ │
│ ┃ EST.DURATION  MOVEMENTS            │ │
│ Movement Checklist        HOLD TO EDIT│  ← Section header + link
│ ┃[✓]┌────────────────────────────────┐│
│ ┃   │ Barbell Back Squat       [img] ││  ← Movement: CHECKED/ACTIVE
│ ┃   │ Compound • Quadriceps          ││  (rail kuning, border kuning)
│ ┃   │ [SETS 4][REPS 8-10][LOAD 85kg] ││
│ ┃   └────────────────────────────────┘│
│  [ ]┌────────────────────────────────┐│
│     │ Dumbbell Romanian        [img] ││  ← Movement: UNCHECKED
│     │ Deadlift                       ││
│     │ Isolation • Hamstrings         ││
│     │ [SETS 3][REPS 12][LOAD 24kg]   ││
│     └────────────────────────────────┘│
│  [ ]┌────────────────────────────────┐│
│     │ Leg Extensions           [img] ││  ← Movement: UNCHECKED
│     │ Machine • Quadriceps           ││
│     │ [SETS 4][REPS 15][LOAD 45kg]   ││
│     └────────────────────────────────┘│
│ ┌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌┐ │
│ ╎       (+) Tambah Gerakan          ╎ │  ← Add Movement (dashed)
│ └╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌┘ │
│ ┌──────────────────────────────────┐ │
│ │ (i) ACTIVE SELECTION MENU         │ │  ← Selection Menu
│ │ [ ✎ Edit ]      [ 🗑 Delete ]    │ │            (▶)│ ← FAB
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
  Text:         "LATIHAN MANDIRI"
  Font-size:    20px, weight 800, uppercase, letter-spacing 0.5px
  Color:        #F5C518
```

### 5.3 Kanan — Overflow Menu
```
Size:           40px × 40px (icon-only, transparan/subtle bg)
Icon:           ⋮ vertical-dots, 20px, color #9A9A9A
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
Margin:         8px 16px 24px
Position:       relative
Overflow:       hidden  (untuk crop watermark)
```

### 6.2 Watermark Dekoratif
```
Text:           "ELITE"
Font-size:      88px, weight 900, color rgba(245,197,24,0.05)
Position:       absolute, bottom-right / vertically centered, melewati tepi
Text-transform: uppercase
Z-index:        0, pointer-events none
```

### 6.3 Supra-label
```
Text:           "CURRENT FOCUS"
Font-size:      10px, weight 600, color #9A9A9A
Letter-spacing: 1.5px, uppercase
```

### 6.4 Focus Title
```
Text:           "Hypertrophy A1 Session"  (wrap 2 baris)
Font-size:      34px, weight 800, color #FFFFFF, letter-spacing -0.5px
Margin:         8px 0 20px
```

### 6.5 Metrics Row
```
Display:        flex, gap 40px

Metric block (number+unit di atas, meta di bawah):
  Number:       28px, weight 800, color #F5C518
  Unit:         13px, weight 700, uppercase, color #9A9A9A, margin-left 4px
  Meta:         10px, weight 600, uppercase, letter-spacing 0.8px, color #6B6B6B

  Metric 1:  "45 MIN"  / "EST. DURATION"
  Metric 2:  "8 EXE"   / "MOVEMENTS"
```

---

## 7. KOMPONEN: MOVEMENT CHECKLIST — SECTION HEADER

```
Display:        flex, justify-content space-between, align-items center
Padding:        0 16px
Margin-bottom:  16px

Judul:
  Text:         "Movement Checklist"  → 18px, weight 800, #FFFFFF

Link:
  Text:         "HOLD TO EDIT"
  Font-size:    11px, weight 700, uppercase, letter-spacing 0.8px
  Color:        #F5C518
```

---

## 8. KOMPONEN: MOVEMENT CARD

### 8.1 Layout Base
```
Layout:         checkbox (kiri, di luar card) + card (flex 1)
Margin:         0 16px 12px
Display:        flex, align-items flex-start, gap 12px
```

### 8.2 Checkbox
```
Size:           24px × 24px, border-radius 8px

Variant CHECKED:
  Background:   #F5C518
  Icon:         ✓ check, 14px, color #0E0E0E

Variant UNCHECKED:
  Background:   transparan
  Border:       2px solid #3A3A3A
```

### 8.3 Movement Card — Variant ACTIVE/CHECKED (highlight)
```
Background:     #1A1A1A
Border:         1px solid #F5C518   (highlight border kuning)
Border-left:    3px solid #F5C518   (accent rail)
Border-radius:  16px
Padding:        16px
Box-shadow:     0 0 16px rgba(245,197,24,0.18)  (glow halus)
Display:        flex, align-items flex-start, gap 12px

Konten (flex 1):
  Title:        "Barbell Back Squat" → 16px, weight 700, color #FFFFFF
  Meta:         "Compound • Quadriceps" → 12px, weight 400, color #9A9A9A, margin-top 4px

  Stat Chips Row (flex, gap 8px, margin-top 12px):
    Chip:       bg #2A2410, border-radius 8px, padding 6px 10px
      Label:    8px, weight 600, uppercase, letter-spacing 0.8px, color #9A9A9A
      Value:    15px, weight 800, color #F5C518
    Chips:  SETS 4 • REPS 8-10 • LOAD 85kg

Thumbnail (kanan, 56×56px):
  Border-radius:12px
  Background:   #1C1C1C
  Object-fit:   cover (ilustrasi gerakan, tint kuning subtle)
  Flex-shrink:  0
```

### 8.4 Movement Card — Variant IDLE/UNCHECKED
```
Background:     #161616
Border:         1px solid #262626
Border-radius:  16px
Padding:        16px

Konten:
  Title:        "Dumbbell Romanian Deadlift" / "Leg Extensions"
                → 16px, weight 700, color #FFFFFF (wrap multi-baris bila perlu)
  Meta:         "Isolation • Hamstrings" / "Machine • Quadriceps" → 12px, color #9A9A9A

  Stat Chips Row:
    Chip:       bg #1C1C1C, border 1px solid #262626, border-radius 8px, padding 6px 10px
      Label:    8px, weight 600, uppercase, color #9A9A9A
      Value:    15px, weight 800, color #FFFFFF
    Chips:  (Romanian) SETS 3 • REPS 12 • LOAD 24kg
            (Leg Ext)  SETS 4 • REPS 15 • LOAD 45kg

Thumbnail (kanan, 56×56px):
  Border-radius:12px, bg #1C1C1C, opacity sedikit diturunkan (idle)
```

---

## 9. KOMPONEN: TAMBAH GERAKAN (Add Movement)

```
Display:        flex, align-items center, justify-content center, gap 10px
Background:     transparan
Border:         1.5px dashed #4A4220  (kuning gelap)
Border-radius:  16px
Padding:        18px
Margin:         12px 16px 24px

Icon:
  Icon:         (+) plus-circle, 20px, color #F5C518

Text:
  Text:         "Tambah Gerakan"
  Font-size:    14px, weight 700, color #FFFFFF
```

---

## 10. KOMPONEN: ACTIVE SELECTION MENU

### 10.1 Container
```
Background:     #161616
Border:         1px solid #262626
Border-radius:  16px
Padding:        16px
Margin:         0 16px
```

### 10.2 Menu Label
```
Display:        flex, align-items center, gap 8px
Icon:           (i) info-circle, 14px, color #F5C518
Text:           "ACTIVE SELECTION MENU"
Font-size:      10px, weight 600, uppercase, letter-spacing 0.8px, color #9A9A9A
Margin-bottom:  12px
```

### 10.3 Action Buttons Row
```
Display:        flex, gap 12px

Edit Button (flex 1):
  Background:   #1C1C1C
  Border:       1px solid #2A2A2A
  Border-radius:8px
  Padding:      12px 0
  Display:      flex center, gap 8px
  Icon:         ✎ pencil, 16px, color #FFFFFF
  Text:         "Edit" → 14px, weight 700, color #FFFFFF

Delete Button (flex 1):
  Background:   #1C1C1C
  Border:       1px solid #2A2A2A
  Border-radius:8px
  Padding:      12px 0
  Display:      flex center, gap 8px
  Icon:         🗑 trash, 16px, color #FFFFFF (boleh tint merah #E0524D)
  Text:         "Delete" → 14px, weight 700, color #FFFFFF
```

---

## 11. KOMPONEN: FLOATING ACTION BUTTON (FAB — Start Session)

```
Position:       fixed/absolute, bottom-right
Offset:         right 16px, bottom 88px (di atas tab bar)
Size:           56px × 56px
Border-radius:  50%  (full circle)
Background:     #F5C518
Icon:           ▶ play, 22px, color #0E0E0E
Box-shadow:     0 4px 16px rgba(245,197,24,0.5)  (glow)
Z-index:        90
Fungsi:         Mulai sesi latihan mandiri (start workout)
```

---

## 12. KOMPONEN: BOTTOM TAB BAR

### 12.1 Container
```
Position:       fixed, bottom 0, left 0, right 0
Height:         72px (+ safe-area-inset-bottom)
Background:     #121212
Border-top:     1px solid #1E1E1E
Box-shadow:     0 -2px 12px rgba(0,0,0,0.5)
Display:        flex, justify-content space-around, align-items center
Z-index:        100
```

### 12.2 Tab Item (Default / Inactive)
```
Display:        flex, flex-direction column, align-items center, gap 4px
Icon:           22px, color #6B6B6B
Label:          10px, weight 600, uppercase, letter-spacing 0.5px, color #6B6B6B
```

### 12.3 Tab Item (Active — PROGRAM)
```
Icon:           22px, color #F5C518
Label-color:    #F5C518
Indicator:      opsional — highlight pill bg di belakang ikon PROGRAM
                (bg rgba(245,197,24,0.12), border-radius 12px)
```

### 12.4 Daftar Tabs (5 item — sesuai gambar)
```
1. 🏠  HOME
2. ⚡  PROGRAM      ← ACTIVE (kuning)
3. 👥  TRAINER
4. 🖥️  MEMBERSHIP
5. 👤  PROFIL
```

---

## 13. GRID RECAP — RINGKASAN ZONA LAYOUT (Mobile)

| Zone                    | X Offset | Y Offset  | Width            | Height    |
|-------------------------|----------|-----------|------------------|-----------|
| Header                  | 0        | safe-top  | 100%             | ~64px     |
| Current Focus Card      | 16px     | ~116px    | calc(100% - 32px)| ~230px    |
| Movement Checklist Hdr  | 16px     | ~378px    | calc(100% - 32px)| ~30px     |
| Movement (ACTIVE)       | 16px     | ~424px    | calc(100% - 32px)| ~120px    |
| Movement (IDLE ×2)      | 16px     | ~556px    | calc(100% - 32px)| ~150px each|
| Tambah Gerakan          | 16px     | ~880px    | calc(100% - 32px)| ~60px     |
| Active Selection Menu   | 16px     | ~964px    | calc(100% - 32px)| ~110px    |
| FAB                     | right16  | bottom88  | 56px             | 56px      |
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px      |

*Catatan: konten melebihi tinggi viewport (932px) → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 14. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Session Detail Screen (Self / Latihan Mandiri, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Session Detail (Self).png
   Generated: 2026-06-27
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:        #0E0E0E;
  --color-bg-card:           #1A1A1A;
  --color-bg-card-alt:       #161616;
  --color-bg-chip:           #1C1C1C;
  --color-bg-chip-active:    #2A2410;
  --color-bg-navbar:         #121212;
  --color-accent-primary:    #F5C518;
  --color-accent-hover:      #E0B200;
  --color-text-primary:      #FFFFFF;
  --color-text-secondary:    #9A9A9A;
  --color-text-muted:        #6B6B6B;
  --color-text-on-accent:    #0E0E0E;
  --color-checkbox-on:       #F5C518;
  --color-checkbox-off:      #3A3A3A;
  --color-stat-value:        #F5C518;
  --color-stat-value-idle:   #FFFFFF;
  --color-watermark:         rgba(245,197,24,0.05);
  --color-border-card:       #262626;
  --color-border-active:     #F5C518;
  --color-border-dashed:     #4A4220;
  --color-accent-rail:       #F5C518;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.45);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-screen-title:       20px;
  --text-supra-label:        10px;
  --text-focus-title:        34px;
  --text-focus-number:       28px;
  --text-focus-unit:         13px;
  --text-focus-meta:         10px;
  --text-watermark:          88px;
  --text-section-title:      18px;
  --text-link:               11px;
  --text-movement-title:     16px;
  --text-movement-meta:      12px;
  --text-stat-label:         8px;
  --text-stat-value:         15px;
  --text-add-btn:            14px;
  --text-menu-label:         10px;
  --text-menu-btn:           14px;
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

## 15. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Session Detail (Self).png`. Semua teks (LATIHAN MANDIRI, CURRENT FOCUS, Hypertrophy A1 Session, 45 MIN, 8 EXE, EST. DURATION, MOVEMENTS, Movement Checklist, HOLD TO EDIT, Barbell Back Squat, Dumbbell Romanian Deadlift, Leg Extensions, Compound • Quadriceps, dst., SETS/REPS/LOAD beserta nilainya, Tambah Gerakan, ACTIVE SELECTION MENU, Edit, Delete) harus persis sama dengan gambar.

2. **Self-Managed / Editable**: Ini perbedaan kunci dari Session Detail (PT). Layar ini sepenuhnya dikelola member — checklist interaktif, stat editable, bisa tambah/edit/hapus gerakan. TIDAK ada badge "Read-Only" maupun info banner kontrol PT. Aktifkan seluruh kontrol edit.

3. **Mobile-First Layout**: Dibuka dari tab Program → section "Latihan Mandiri" (selaras dengan PROGRAM_TAB_UI_SPEC). Navigasi via header back + overflow menu (⋮), serta bottom tab bar 5 item dengan PROGRAM aktif. Gunakan `safe-area-inset-*`.

4. **Focus Card Watermark**: Teks "ELITE" raksasa di belakang konten, opacity sangat rendah (`rgba(245,197,24,0.05)`). Wajib `overflow:hidden` agar ter-crop. `pointer-events:none`.

5. **Focus Metrics (bukan progress)**: Berbeda dari versi PT yang menampilkan progress bar 75%, versi Self menampilkan metrik estimasi: "45 MIN / EST. DURATION" dan "8 EXE / MOVEMENTS". Ini info pra-sesi (belum dimulai), bukan progres berjalan.

6. **Checkbox Interaktif**: Tiap movement punya checkbox 24px di kiri (di luar card). CHECKED = kuning solid + check hitam; UNCHECKED = outline abu kosong. Member men-tap untuk menandai gerakan selesai. Gunakan `role="checkbox"` + `aria-checked`.

7. **Movement Active Highlight**: Movement pertama (Barbell Back Squat) dalam state aktif/checked — border kuning penuh + accent rail kiri 3px + glow + stat value kuning. Movement idle pakai border abu + stat value putih. Bedakan via enum state.

8. **Stat Chips Editable**: Tiap movement menampilkan 3 chip (SETS, REPS, LOAD). Pada movement aktif, chip bg lebih hangat (`#2A2410`) dengan value kuning; pada idle, bg `#1C1C1C` dengan value putih. Chip ini editable (tap → ubah nilai) saat mode edit aktif.

9. **Thumbnail Gerakan**: Tiap card punya thumbnail 56px di kanan (ilustrasi gerakan). Movement aktif tampil terang; idle sedikit diredupkan. Gunakan `object-fit:cover` + `flex-shrink:0` agar tidak gepeng.

10. **Tambah Gerakan (Dashed)**: Tombol dashed-border kuning gelap dengan ikon (+) untuk menambah movement baru ke checklist. Membuka picker/library gerakan. Beri `aria-label="Tambah gerakan baru"`.

11. **Active Selection Menu**: Panel kontekstual berisi tombol Edit & Delete untuk movement yang sedang dipilih. Muncul saat user memilih item (selaras dengan "HOLD TO EDIT"). Delete sebaiknya memicu konfirmasi sebelum menghapus.

12. **FAB Start Session**: FAB bundar 56px kuning dengan ikon ▶ play di kanan bawah (offset bottom 88px agar tidak menabrak tab bar). Fungsi: memulai sesi latihan mandiri. Punya glow shadow. Beri `aria-label="Mulai sesi"`.

13. **Scroll & Padding**: Konten lebih tinggi dari viewport → scroll vertikal. Beri `padding-bottom:88px` agar selection menu, FAB, & elemen terbawah tidak tertutup tab bar. Header boleh sticky.

14. **Accessibility**: Beri `aria-current="page"` pada tab PROGRAM. Checkbox movement gunakan `role="checkbox"` + `aria-checked`. State movement jangan hanya warna — sertakan status checkbox & highlight. Tombol Edit/Delete/Tambah/FAB beri `aria-label` jelas; Delete idealnya `aria-haspopup="dialog"` untuk konfirmasi. Touch target minimum 44×44px (checkbox, chip, FAB, tab).

---

*Spec ini generated dari analisis visual screen Session Detail (Self).png (visual-verified).*
*Design system reference: Egg Gym — Program (PROGRAM_TAB_UI_SPEC.md), Session Detail PT (SESSION_DETAIL_PT_UI_SPEC.md) & Booking History (BOOKING_HISTORY_UI_SPEC.md).*
*Total sections: 15 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

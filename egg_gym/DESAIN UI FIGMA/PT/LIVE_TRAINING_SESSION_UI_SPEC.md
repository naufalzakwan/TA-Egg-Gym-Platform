# LIVE_TRAINING_SESSION_UI_SPEC.md
# Egg Gym App — Live Training Session Screen (Sesi Latihan Berlangsung, Pro Trainer Side, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Trainer App > Program > Progress > Live Session (Active Workout Execution)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Live Training Session.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Live Training Session (Pro Trainer) memakai sistem warna identik dengan Home PT Dashboard, Jadwal Sesi, Buat Program, Buat Sesi & Program Progress: latar near-black dengan aksen kuning emas. Token tambahan ditambahkan untuk live indicator, progress block + watermark, trainer validator bar, exercise checklist (checked/active/idle), tag muscle group, dan CTA selesaikan sesi.

| Token Name                  | HEX Value             | Usage                                            |
|-----------------------------|-----------------------|--------------------------------------------------|
| --color-bg-primary          | #0E0E0E               | App background (screen utama)                    |
| --color-bg-card             | #1A1A1A               | Progress block & validator bar background         |
| --color-bg-card-alt         | #161616               | Exercise list item idle background                |
| --color-bg-chip             | #1C1C1C               | Muscle tag bg, secondary surface                  |
| --color-bg-navbar           | #121212               | Bottom tab bar background                         |
| --color-accent-primary      | #F5C518               | CTA, persen, checkbox checked, live dot, brand    |
| --color-accent-hover        | #E0B200               | Button pressed state                              |
| --color-text-primary        | #FFFFFF               | Screen title, exercise name (active/checked)      |
| --color-text-secondary      | #9A9A9A               | Sub-meta, sets/reps, captions                     |
| --color-text-muted          | #6B6B6B               | Idle exercise text, drag handle, inactive tab     |
| --color-text-on-accent      | #0E0E0E               | Text on yellow elements (CTA, checkbox tick)      |
| --color-live-label          | #F5C518               | "LIVE SESSION" + "AKTIF" indicator text           |
| --color-live-dot            | #F5C518               | Live status dot (pulsing)                         |
| --color-progress-label      | #9A9A9A               | "PROGRESS SESI" / "WAKTU MULAI" label             |
| --color-percent-big         | #F5C518               | Angka besar "65" persen progress                  |
| --color-percent-unit        | #FFFFFF               | "%" unit di samping angka                         |
| --color-time-value          | #FFFFFF               | "08:15 AM" waktu mulai value                      |
| --color-progress-track      | #2A2A2A               | Track progress bar (kosong)                       |
| --color-progress-fill       | #F5C518               | Fill progress bar (terisi 65%)                    |
| --color-progress-rail       | #F5C518               | Left accent rail di progress block                |
| --color-watermark           | rgba(255,255,255,0.03)| Watermark dumbbell di belakang progress block     |
| --color-validator-status    | #F5C518               | Status "TERVERIFIKASI" text                       |
| --color-validator-label     | #6B6B6B               | "TRAINER VALIDATOR" / "STATUS" label              |
| --color-checkbox-checked-bg | #F5C518               | Checkbox tercentang (kuning solid + ✓)            |
| --color-checkbox-checked-tick | #0E0E0E             | Tanda centang ✓ pada checkbox checked             |
| --color-checkbox-active     | #F5C518               | Border checkbox sesi aktif (kosong, outline kuning)|
| --color-checkbox-idle       | #2A2A2A               | Checkbox idle (kotak gelap, belum dikerjakan)     |
| --color-tag-muscle          | #F5C518               | Tag otot "CHEST"/"BACK"/"SHOULDERS"/"TRICEPS" text |
| --color-tag-muscle-bg       | rgba(245,197,24,0.12) | Background tag otot                               |
| --color-drag-handle         | #6B6B6B               | Drag handle (⠿) reorder exercise                  |
| --color-item-active-rail    | #F5C518               | Left accent rail item exercise aktif              |
| --color-border-card         | #262626               | Card & list item borders                          |
| --color-cta-bg              | #F5C518               | Background tombol "Selesaikan Sesi"               |
| --color-sync-note           | #6B6B6B               | Teks "DATA AKAN DISINKRONISASI..." di bawah CTA   |
| --color-tab-active          | #F5C518               | Active bottom-tab icon & label (PROGRAM)          |
| --color-tab-inactive        | #6B6B6B               | Inactive bottom-tab icon & label                  |
| --color-glow-cta            | rgba(245,197,24,0.45) | Glow CTA kuning                                   |
| --color-overlay-dark        | rgba(0,0,0,0.7)       | Modal backdrop (konfirmasi selesai)               |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (screen title & big percent)
```

### Skala Tipografi Lengkap
| Token                   | Size | Weight | Line-H | Letter-Sp         | Usage                                  |
|-------------------------|------|--------|--------|-------------------|----------------------------------------|
| --text-screen-title     | 22px | 800    | 1.2    | -0.3px            | "Upper Body Hypertrophy" title         |
| --text-screen-sub       | 13px | 500    | 1.3    | 0px               | "Naufal - Sesi 19/24" subtitle         |
| --text-live-label       | 10px | 700    | 1.2    | 1px (uppercase)   | "LIVE SESSION" + "AKTIF" indicator     |
| --text-progress-label   | 11px | 700    | 1.3    | 0.8px (uppercase) | "PROGRESS SESI" / "WAKTU MULAI"        |
| --text-percent-big      | 44px | 800    | 1.0    | -1px              | "65" angka besar progress              |
| --text-percent-unit     | 18px | 700    | 1.0    | 0px               | "%" unit                                |
| --text-time-value       | 22px | 800    | 1.1    | 0px               | "08:15 AM" waktu mulai                  |
| --text-validator-label  | 10px | 700    | 1.2    | 0.8px (uppercase) | "TRAINER VALIDATOR" / "STATUS"         |
| --text-validator-name   | 16px | 700    | 1.3    | 0px               | "Coach Reyhan W." validator name       |
| --text-validator-status | 12px | 700    | 1.2    | 0.5px (uppercase) | "TERVERIFIKASI" status                  |
| --text-section-title    | 22px | 800    | 1.2    | 0px               | "Daftar Latihan" section heading       |
| --text-section-action   | 12px | 700    | 1.2    | 0.5px (uppercase) | "≡ REORDER" action                      |
| --text-exercise-name    | 16px | 700    | 1.3    | 0px               | "Incline Dumbbell Press" exercise name |
| --text-exercise-meta    | 12px | 500    | 1.3    | 0px               | "4 Sets • 10-12 Reps" meta             |
| --text-muscle-tag       | 9px  | 800    | 1.2    | 0.5px (uppercase) | "CHEST"/"BACK"/"SHOULDERS"/"TRICEPS"   |
| --text-cta              | 17px | 800    | 1.2    | 0.3px             | "Selesaikan Sesi" button                |
| --text-sync-note        | 10px | 600    | 1.4    | 0.5px (uppercase) | "DATA AKAN DISINKRONISASI..." note     |
| --text-tab-label        | 9px  | 600    | 1.2    | 0.5px (uppercase) | Bottom tab labels                       |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Badge padding, tiny gaps                          |
| --space-sm     | 8px   | Icon-text gap, checkbox-text gap                  |
| --space-md     | 12px  | Inter-element gap, list item gap                  |
| --space-base   | 16px  | Screen horizontal padding, card padding           |
| --space-lg     | 20px  | Block-to-block vertical gap                       |
| --space-xl     | 24px  | Section separation                                |
| --space-2xl    | 32px  | Major block separation (list → CTA)               |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Checkbox, muscle tag, small element              |
| --radius-md    | 12px  | Exercise list item, validator bar                |
| --radius-lg    | 16px  | Progress block, CTA button                        |
| --radius-pill  | 999px | Progress bar, live indicator pill                 |
| --radius-full  | 50%   | Avatar (back btn circle, validator avatar)        |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards & list items          |
| --shadow-cta     | 0 0 22px rgba(245,197,24,0.45)        | Glow "Selesaikan Sesi" CTA  |
| --shadow-active  | 0 0 0 1px rgba(245,197,24,0.4)        | Highlight item aktif        |
| --shadow-navbar  | 0 -2px 12px rgba(0,0,0,0.5)           | Bottom tab bar elevation    |

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Design Canvas:  430 × 932 px (mobile portrait)
Screen Padding: 16px horizontal
Safe Area Top:  ~44px (status bar device)
Header:         100% width × ~96px (back circle + title block + live indicator)
Bottom Tab Bar: 100% width × 72px (fixed bottom, + safe-area-inset-bottom)
Content Scroll: vertical, padding-bottom 88px (ruang untuk tab bar)
Exercise List:  full-width list item, gap 12px, drag-reorderable (mode REORDER)
CTA:            full-width, akhir konten + sync note
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ (←) Upper Body Hypertrophy   LIVE     │  ← Header
│     Naufal - Sesi 19/24    SESSION    │
│                            ● AKTIF    │  ← Live Indicator
├──────────────────────────────────────┤
│ ┃ PROGRESS SESI       WAKTU MULAI    │ │  ← Progress Block (rail kuning)
│ ┃ 65%                 08:15 AM       │ │
│ ┃ ▓▓▓▓▓▓▓▓▓▓▓▓▓░░░░░░░               │ │  ← Progress Bar 65%
│ ┌──────────────────────────────────┐ │
│ │ [👤] TRAINER VALIDATOR    STATUS │ │  ← Validator Bar
│ │      Coach Reyhan W. TERVERIFIKASI│ │
│ └──────────────────────────────────┘ │
│ Daftar Latihan          ≡ REORDER    │  ← Section header
│ ┌──────────────────────────────────┐ │
│ │ [✓] CHEST Incline Dumbbell   ⠿  │ │  ← Exercise (CHECKED)
│ │     4 Sets • 10-12 Reps          │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [✓] BACK Weighted Pull Ups   ⠿  │ │  ← Exercise (CHECKED)
│ │     3 Sets • 8 Reps              │ │
│ └──────────────────────────────────┘ │
│ ┃┌─────────────────────────────────┐ │
│ ┃│ [ ] SHOULDERS Lateral Raises ⠿ │ │  ← Exercise (ACTIVE, outline)
│ ┃│     4 Sets • 15 Reps            │ │
│ ┃└─────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [▪] TRICEPS Skull Crushers   ⠿  │ │  ← Exercise (IDLE, muted)
│ │     3 Sets • 12 Reps             │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │     Selesaikan Sesi  ⊙           │ │  ← Primary CTA (kuning)
│ └──────────────────────────────────┘ │
│  DATA AKAN DISINKRONISASI KE          │  ← Sync Note
│  DASHBOARD TRAINER                    │
├──────────────────────────────────────┤
│ 🏠     📅     👥      ⚡      👤    │  ← Bottom Tab Bar (TRAINER)
│ HOME JADWAL KLIEN PROGRAM PROFIL     │  ← PROGRAM active
└──────────────────────────────────────┘
```

---

## 5. KOMPONEN: HEADER

### 5.1 Container
```
Display:        flex, align-items flex-start, justify-content space-between
Padding:        16px
Margin-top:     safe-area-inset-top
```

### 5.2 Kiri — Back + Title Block
```
Display:        flex, align-items flex-start, gap 12px

Back Button:
  Size:         40px × 40px, border-radius 50%, background #1C1C1C
  Icon:         ← arrow, 20px, color #FFFFFF

Title Block:
  Title:        "Upper Body Hypertrophy" → 22px, weight 800, color #FFFFFF, letter-spacing -0.3px
  Subtitle:     "Naufal - Sesi 19/24" → 13px, weight 500, color #9A9A9A, margin-top 4px
```

### 5.3 Kanan — Live Indicator
```
Display:        flex, flex-direction column, align-items flex-end, gap 4px
Label:          "LIVE SESSION" → 10px, weight 700, uppercase, letter-spacing 1px, color #F5C518
Status:         ● dot (#F5C518, pulsing animation) + "AKTIF"
                → 10px, weight 700, uppercase, color #F5C518
Animation:      dot pulse 1.5s ease-in-out infinite (opacity/scale)
```

---

## 6. KOMPONEN: PROGRESS BLOCK

```
Background:     #1A1A1A
Border:         1px solid #262626
Border-left:    4px solid #F5C518   (accent rail)
Border-radius:  16px
Padding:        20px
Margin:         8px 16px 20px
Position:       relative, overflow hidden (untuk watermark dumbbell)

Top Row (flex, justify-content space-between, align-items flex-start):
  Kiri:
    Label:      "PROGRESS SESI" → 11px, weight 700, uppercase, letter-spacing 0.8px, color #9A9A9A
    Percent:    "65" → 44px, weight 800, color #F5C518 + "%" → 18px, weight 700, color #FFFFFF
  Kanan:
    Label:      "WAKTU MULAI" → 11px, weight 700, uppercase, letter-spacing 0.8px, color #9A9A9A
    Value:      "08:15 AM" → 22px, weight 800, color #FFFFFF

Watermark:      ikon dumbbell besar, color rgba(255,255,255,0.03), absolute kanan-bawah, z-index 0

Progress Bar (margin-top 16px):
  Track:        height 8px, background #2A2A2A, border-radius 999px
  Fill:         width 65%, background #F5C518, border-radius 999px
```

---

## 7. KOMPONEN: TRAINER VALIDATOR BAR

```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  12px
Padding:        14px 16px
Margin:         0 16px 24px
Display:        flex, align-items center, gap 12px

Avatar:         44px × 44px, border-radius 12px (rounded-square), object-fit cover

Info (flex 1):
  Label:        "TRAINER VALIDATOR" → 10px, weight 700, uppercase, letter-spacing 0.8px, color #6B6B6B
  Name:         "Coach Reyhan W." → 16px, weight 700, color #FFFFFF, margin-top 2px

Status (kanan):
  Label:        "STATUS" → 10px, weight 700, uppercase, letter-spacing 0.8px, color #6B6B6B
  Value:        "TERVERIFIKASI" → 12px, weight 700, uppercase, color #F5C518, margin-top 2px
```

---

## 8. KOMPONEN: DAFTAR LATIHAN (Exercise Checklist)

### 8.1 Section Header
```
Display:        flex, justify-content space-between, align-items center
Padding:        0 16px
Margin-bottom:  12px

Judul:
  Text:         "Daftar Latihan" → 22px, weight 800, color #FFFFFF

Action:
  Icon+Text:    "≡ REORDER"
  Icon:         ≡ list/hamburger, 16px, color #9A9A9A
  Text:         12px, weight 700, uppercase, letter-spacing 0.5px, color #9A9A9A
  Behavior:     toggle mode reorder (drag handle aktif)
```

### 8.2 Exercise List Item — Anatomy Umum
```
Border-radius:  12px
Padding:        14px 16px
Margin:         0 16px 12px
Display:        flex, align-items center, gap 12px

Checkbox (kiri):  28px × 28px (lihat state di bawah)
Info (flex 1):
  Top Row:        Muscle Tag + Exercise Name (inline, gap 8px)
    Muscle Tag:   "CHEST"/"BACK"/"SHOULDERS"/"TRICEPS"
                  → 9px, weight 800, uppercase, color #F5C518,
                    bg rgba(245,197,24,0.12), padding 3px 7px, border-radius 8px
    Name:         16px, weight 700 (warna ikut state)
  Meta:           "4 Sets • 10-12 Reps" → 12px, weight 500, color #9A9A9A, margin-top 4px
Drag Handle (kanan): ⠿ (6-dot), 16px, color #6B6B6B (aktif saat mode REORDER)
```

### 8.3 State — CHECKED (Incline Dumbbell Press, Weighted Pull Ups)
```
Background:     #161616
Checkbox:       28px × 28px, background #F5C518, border-radius 8px, ikon ✓ color #0E0E0E
Name:           color #FFFFFF (opsional strikethrough subtle / opacity 0.85)
Catatan:        gerakan sudah diselesaikan
```

### 8.4 State — ACTIVE (Lateral Raises — sesi berjalan)
```
Background:     #161616
Border-left:    3px solid #F5C518   (accent rail penanda gerakan aktif)
Checkbox:       28px × 28px, background transparan, border 2px solid #F5C518, border-radius 8px (kosong)
Name:           color #FFFFFF
Box-shadow:     0 0 0 1px rgba(245,197,24,0.4) (highlight subtle)
Catatan:        gerakan yang sedang dikerjakan saat ini
```

### 8.5 State — IDLE (Skull Crushers — belum dikerjakan)
```
Background:     #141414 (lebih gelap / dim)
Checkbox:       28px × 28px, background #2A2A2A, border-radius 8px (kotak gelap kosong)
Name:           color #6B6B6B (muted)
Meta:           color #6B6B6B
Catatan:        gerakan belum tiba gilirannya
```

---

## 9. KOMPONEN: PRIMARY CTA — SELESAIKAN SESI

```
Width:          calc(100% - 32px)
Margin:         16px 16px 8px
Background:     #F5C518
Color:          #0E0E0E
Padding:        18px 0
Border-radius:  16px
Display:        flex, align-items center, justify-content center, gap 10px
Label:          "Selesaikan Sesi" → 17px, weight 800, letter-spacing 0.3px
Icon:           ⊙ check-circle, 20px, color #0E0E0E (kanan)
Box-shadow:     0 0 22px rgba(245,197,24,0.45)  (glow)
Behavior:       tap → konfirmasi → finalisasi sesi & sinkronisasi data ke dashboard trainer

Sync Note (di bawah CTA, margin-top 12px):
  Text:         "DATA AKAN DISINKRONISASI KE DASHBOARD TRAINER"
  Font:         10px, weight 600, uppercase, letter-spacing 0.5px, color #6B6B6B, text-align center
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

### 10.3 Tab Item (Active — PROGRAM)
```
Icon:           22px, color #F5C518
Label-color:    #F5C518
Indicator:      highlight pill bg di belakang ikon PROGRAM
                (bg rgba(245,197,24,0.12), border-radius 12px)
```

### 10.4 Daftar Tabs (5 item — VERSI TRAINER)
```
1. 🏠  HOME
2. 📅  JADWAL
3. 👥  KLIEN
4. ⚡  PROGRAM    ← ACTIVE (kuning)
5. 👤  PROFIL
```

---

## 11. GRID RECAP — RINGKASAN ZONA LAYOUT (Mobile)

| Zone                    | X Offset | Y Offset  | Width            | Height     |
|-------------------------|----------|-----------|------------------|------------|
| Header                  | 0        | safe-top  | 100%             | ~96px      |
| Progress Block          | 16px     | ~140px    | calc(100% - 32px)| ~140px     |
| Trainer Validator Bar   | 16px     | ~300px    | calc(100% - 32px)| ~76px      |
| Daftar Latihan Header   | 16px     | ~400px    | calc(100% - 32px)| ~30px      |
| Exercise Item ×4        | 16px     | ~446px    | calc(100% - 32px)| ~80px each |
| CTA Selesaikan Sesi     | 16px     | ~790px    | calc(100% - 32px)| ~62px      |
| Sync Note               | 16px     | ~864px    | calc(100% - 32px)| ~30px      |
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px       |

*Catatan: konten melebihi tinggi viewport (932px) → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 12. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Live Training Session Screen (Sesi Latihan Berlangsung, Pro Trainer, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Live Training Session.png
   Generated: 2026-06-27
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:           #0E0E0E;
  --color-bg-card:              #1A1A1A;
  --color-bg-card-alt:          #161616;
  --color-bg-chip:              #1C1C1C;
  --color-bg-navbar:            #121212;
  --color-accent-primary:       #F5C518;
  --color-accent-hover:         #E0B200;
  --color-text-primary:         #FFFFFF;
  --color-text-secondary:       #9A9A9A;
  --color-text-muted:           #6B6B6B;
  --color-text-on-accent:       #0E0E0E;
  --color-live-label:           #F5C518;
  --color-live-dot:             #F5C518;
  --color-progress-label:       #9A9A9A;
  --color-percent-big:          #F5C518;
  --color-percent-unit:         #FFFFFF;
  --color-time-value:           #FFFFFF;
  --color-progress-track:       #2A2A2A;
  --color-progress-fill:        #F5C518;
  --color-progress-rail:        #F5C518;
  --color-watermark:            rgba(255,255,255,0.03);
  --color-validator-status:     #F5C518;
  --color-validator-label:      #6B6B6B;
  --color-checkbox-checked-bg:  #F5C518;
  --color-checkbox-checked-tick:#0E0E0E;
  --color-checkbox-active:      #F5C518;
  --color-checkbox-idle:        #2A2A2A;
  --color-tag-muscle:           #F5C518;
  --color-tag-muscle-bg:        rgba(245,197,24,0.12);
  --color-drag-handle:          #6B6B6B;
  --color-item-active-rail:     #F5C518;
  --color-border-card:          #262626;
  --color-cta-bg:               #F5C518;
  --color-sync-note:            #6B6B6B;
  --color-tab-active:           #F5C518;
  --color-tab-inactive:         #6B6B6B;
  --color-glow-cta:             rgba(245,197,24,0.45);
  --color-overlay-dark:         rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:        "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-screen-title:          22px;
  --text-screen-sub:            13px;
  --text-live-label:            10px;
  --text-progress-label:        11px;
  --text-percent-big:           44px;
  --text-percent-unit:          18px;
  --text-time-value:            22px;
  --text-validator-label:       10px;
  --text-validator-name:        16px;
  --text-validator-status:      12px;
  --text-section-title:         22px;
  --text-section-action:        12px;
  --text-exercise-name:         16px;
  --text-exercise-meta:         12px;
  --text-muscle-tag:            9px;
  --text-cta:                   17px;
  --text-sync-note:             10px;
  --text-tab-label:             9px;

  /* ── SPACING ── */
  --space-xs:                   4px;
  --space-sm:                   8px;
  --space-md:                   12px;
  --space-base:                 16px;
  --space-lg:                   20px;
  --space-xl:                   24px;
  --space-2xl:                  32px;

  /* ── BORDER RADIUS ── */
  --radius-sm:                  8px;
  --radius-md:                  12px;
  --radius-lg:                  16px;
  --radius-pill:                999px;
  --radius-full:                50%;

  /* ── SHADOWS ── */
  --shadow-card:                0 2px 8px rgba(0,0,0,0.4);
  --shadow-cta:                 0 0 22px rgba(245,197,24,0.45);
  --shadow-active:              0 0 0 1px rgba(245,197,24,0.4);
  --shadow-navbar:              0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:             16px;
  --header-height:              96px;
  --navbar-height:              72px;
  --list-item-gap:              12px;
  --checkbox-size:              28px;
  --card-radius:                16px;
  --tab-count:                  5;
}
```

---

## 13. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Live Training Session.png`. Semua teks (Upper Body Hypertrophy, Naufal - Sesi 19/24, LIVE SESSION, AKTIF, PROGRESS SESI, 65%, WAKTU MULAI, 08:15 AM, TRAINER VALIDATOR, Coach Reyhan W., STATUS, TERVERIFIKASI, Daftar Latihan, REORDER, CHEST, Incline Dumbbell Press, 4 Sets • 10-12 Reps, BACK, Weighted Pull Ups, 3 Sets • 8 Reps, SHOULDERS, Lateral Raises, 4 Sets • 15 Reps, TRICEPS, Skull Crushers, 3 Sets • 12 Reps, Selesaikan Sesi, DATA AKAN DISINKRONISASI KE DASHBOARD TRAINER) harus persis sama dengan gambar.

2. **TRAINER SIDE (Bukan Member)**: Bagian dari keluarga Trainer-side (lihat HOME_PT_DASHBOARD, TRAINER_SCHEDULE, CREATE_PROGRAM_FORM, EDIT_TRAINING_SESSION & PROGRESSIVE_UNLOCK_TIMELINE specs). Bottom tab bar versi trainer: **HOME / JADWAL / KLIEN / PROGRAM / PROFIL** dengan **PROGRAM aktif**. Jangan tertukar dengan tab bar member.

3. **Relasi dengan Progressive Unlock Timeline**: Layar ini adalah hasil tap CTA "Lanjutkan Latihan" di sesi AKTIF pada PROGRESSIVE_UNLOCK_TIMELINE. Progress "65%" di sini sinkron dengan "SESI BERLANGSUNG 65%" di timeline. Saat "Selesaikan Sesi" ditekan, sesi naik ke 100% → status timeline berubah jadi SELESAI dan sesi berikutnya unlock.

4. **Mobile-First Layout**: Layar eksekusi workout live, konten scrollable vertikal. Gunakan `safe-area-inset-*`. Header membawa nama program + identitas klien (Naufal) + nomor sesi (19/24).

5. **Live Session Indicator**: "LIVE SESSION" + dot kuning + "AKTIF" menandai sesi sedang berjalan real-time. Dot sebaiknya animasi pulse. Status ini penting — bedakan dari sesi terjadwal yang belum dimulai.

6. **Progress Block real-time**: Persen besar (65%) = progres penyelesaian sesi saat ini, dihitung dari rasio gerakan tercentang (mis. 2 dari ~beberapa langkah). "WAKTU MULAI 08:15 AM" mencatat kapan sesi dimulai. Progress bar update otomatis tiap checkbox dicentang. Watermark dumbbell dekoratif opacity sangat rendah.

7. **Trainer Validator Bar**: Menampilkan trainer yang memvalidasi/mengawasi sesi (Coach Reyhan W.) dengan status "TERVERIFIKASI" kuning. Ini lapisan akuntabilitas — sesi divalidasi oleh trainer. Avatar rounded-square konsisten dengan session card di spec lain.

8. **Exercise Checklist 3-State**: Inti layar. CHECKED (kuning solid + ✓, sudah selesai), ACTIVE (checkbox outline kuning + accent rail kiri, sedang dikerjakan), IDLE (kotak gelap, muted, belum giliran). Tap checkbox menandai gerakan selesai → mengupdate progress sesi & memajukan state ACTIVE ke item berikutnya.

9. **Muscle Tag inline**: Tag otot (CHEST/BACK/SHOULDERS/TRICEPS) kuning tinted inline sebelum nama exercise. Berasal dari metadata exercise (konsisten dengan EDIT_TRAINING_SESSION yang punya tag QUADRICEPS/HAMSTRINGS). Di sini tag dibuat lebih kecil & inline.

10. **Reorder Mode**: Action "≡ REORDER" mengaktifkan drag handle (⠿) di kanan tiap item untuk mengubah urutan latihan saat live. Gunakan sortable list beraksesibilitas. Pertimbangkan apakah gerakan CHECKED boleh di-reorder atau dikunci.

11. **Primary CTA — Selesaikan Sesi**: Tombol kuning solid full-width + ikon check-circle + glow. Tap → konfirmasi (modal overlay) → finalisasi sesi. Sync note di bawahnya menegaskan data sesi akan disinkronkan ke dashboard trainer (Home PT Dashboard). Idealnya beri peringatan bila masih ada gerakan belum tercentang.

12. **Data Sync**: Setelah sesi selesai, data (gerakan selesai, durasi, progres) disinkron ke dashboard trainer & memperbarui PROGRESSIVE_UNLOCK_TIMELINE (sesi → SELESAI). Tampilkan state loading/sukses sinkronisasi.

13. **Scroll & Padding**: Konten (header + progress + validator + 4 latihan + CTA) bisa melebihi viewport → scroll vertikal. Beri `padding-bottom:88px` agar CTA & sync note tidak tertutup tab bar. Header & progress block boleh sticky agar progres selalu terlihat saat scroll.

14. **Accessibility**: Beri `aria-current="page"` pada tab PROGRAM. Live indicator beri `aria-live="polite"`. Checkbox gunakan `role="checkbox"` + `aria-checked` + `aria-label` menyertakan nama gerakan (mis. "Tandai selesai Lateral Raises"). Progress bar gunakan `role="progressbar"` + `aria-valuenow="65"`. Status item jangan andalkan warna saja — sertakan state teks/aria. CTA "Selesaikan Sesi" beri konfirmasi. Kontras teks gelap pada elemen kuning penuhi WCAG AA. Touch target minimum 44×44px.

---

*Spec ini generated dari analisis visual screen Live Training Session.png (visual-verified).*
*Design system reference: Egg Gym — Home PT Dashboard, Trainer Schedule (TRAINER_SCHEDULE_UI_SPEC.md), Create Program Form (CREATE_PROGRAM_FORM_UI_SPEC.md), Edit Training Session (EDIT_TRAINING_SESSION_UI_SPEC.md), Progressive Unlock Timeline (PROGRESSIVE_UNLOCK_TIMELINE_UI_SPEC.md) & Member specs. CATATAN: sisi TRAINER, bottom tab bar HOME/JADWAL/KLIEN/PROGRAM/PROFIL, PROGRAM aktif. Layar ini eksekusi live dari sesi aktif (drill-down dari CTA "Lanjutkan Latihan").*
*Total sections: 13 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

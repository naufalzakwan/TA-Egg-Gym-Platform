# PROGRESSIVE_UNLOCK_TIMELINE_UI_SPEC.md
# Egg Gym App — Program Progress Screen (Progressive Unlock Timeline, Pro Trainer Side, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Trainer App > Program > Program Progress (Progressive Unlock Session Timeline)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Progressive Unlock Timeline.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Program Progress (Pro Trainer) memakai sistem warna identik dengan Home PT Dashboard, Jadwal Sesi, Buat Program & Buat Sesi: latar near-black dengan aksen kuning emas. Token tambahan ditambahkan untuk completion status block + watermark, info banner accent rail, timeline node 3-status (selesai/aktif/terkunci), status badge, progress bar sesi, dan CTA lanjutkan.

| Token Name                  | HEX Value             | Usage                                            |
|-----------------------------|-----------------------|--------------------------------------------------|
| --color-bg-primary          | #0E0E0E               | App background (screen utama)                    |
| --color-bg-card             | #141414               | Completion status block & active session card     |
| --color-bg-card-alt         | #1A1A1A               | Inner block / date pill / banner background       |
| --color-bg-banner           | #161616               | Info banner background                            |
| --color-bg-chip             | #1C1C1C               | Date pill, status badge bg (locked)               |
| --color-bg-navbar           | #121212               | Bottom tab bar background                         |
| --color-accent-primary      | #F5C518               | CTA, persen, node aktif, progress fill, brand     |
| --color-accent-hover        | #E0B200               | Button pressed state                              |
| --color-text-primary        | #FFFFFF               | Headings, session title (done/active)             |
| --color-text-secondary      | #9A9A9A               | Description, meta text                             |
| --color-text-muted          | #6B6B6B               | Locked session text, captions, inactive tab       |
| --color-text-on-accent      | #0E0E0E               | Text on yellow elements (CTA, node aktif)         |
| --color-status-label        | #B0B0B0               | "COMPLETION STATUS" label                         |
| --color-percent-big         | #F5C518               | Angka besar "40" persen completion                |
| --color-percent-unit        | #6B6B6B               | "%" unit di samping angka                         |
| --color-watermark           | rgba(245,197,24,0.06) | Teks watermark "UNLK" di belakang progress        |
| --color-progress-track      | #2A2A2A               | Track progress bar (kosong)                       |
| --color-progress-fill       | #F5C518               | Fill progress bar (terisi)                        |
| --color-info-icon           | #F5C518               | Ikon (i) pada info banner                         |
| --color-info-rail           | #F5C518               | Left accent rail info banner                      |
| --color-node-done           | #2EBD85               | Node sesi SELESAI (hijau, ✓)                       |
| --color-node-done-bg        | rgba(46,189,133,0.15) | Background ring node selesai                       |
| --color-node-active         | #F5C518               | Node sesi AKTIF (kuning, ▶ play)                  |
| --color-node-active-glow    | rgba(245,197,24,0.45) | Glow node aktif                                   |
| --color-node-locked         | #3A3A3A               | Node sesi TERKUNCI (abu, 🔒)                       |
| --color-node-locked-icon    | #6B6B6B               | Ikon gembok pada node terkunci                    |
| --color-timeline-line       | #2A2A2A               | Garis konektor vertikal timeline                  |
| --color-badge-done          | #2EBD85               | Badge "SELESAI" (teks hijau)                      |
| --color-badge-done-bg       | rgba(46,189,133,0.15) | Background badge "SELESAI"                         |
| --color-badge-active        | #0E0E0E               | Badge "AKTIF" teks (di atas kuning solid)         |
| --color-badge-active-bg     | #F5C518               | Background badge "AKTIF" (kuning solid)            |
| --color-badge-locked        | #6B6B6B               | Badge "TERKUNCI" (teks abu)                       |
| --color-badge-locked-bg     | #1C1C1C               | Background badge "TERKUNCI"                        |
| --color-border-card         | #262626               | Card & panel borders                              |
| --color-border-active-card  | #F5C518               | Border kartu sesi aktif (highlight kuning subtle) |
| --color-cta-bg              | #F5C518               | Background tombol "Lanjutkan Latihan"             |
| --color-tab-active          | #F5C518               | Active bottom-tab icon & label (PROGRAM)          |
| --color-tab-inactive        | #6B6B6B               | Inactive bottom-tab icon & label                  |
| --color-glow-cta            | rgba(245,197,24,0.35) | Glow CTA kuning                                   |
| --color-overlay-dark        | rgba(0,0,0,0.7)       | Modal backdrop                                    |

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
| --text-topbar-title     | 20px | 800    | 1.1    | 0px               | "Program Progress" judul top bar       |
| --text-status-label     | 12px | 700    | 1.3    | 2px (uppercase)   | "COMPLETION STATUS" label              |
| --text-percent-big      | 56px | 800    | 1.0    | -1px              | "40" angka besar completion            |
| --text-percent-unit     | 20px | 700    | 1.0    | 0px               | "%" unit                                |
| --text-watermark        | 64px | 800    | 1.0    | 2px (uppercase)   | "UNLK" watermark di belakang           |
| --text-info-banner      | 13px | 500    | 1.5    | 0px               | Teks info banner (terbuka setelah...)  |
| --text-session-title    | 20px | 800    | 1.2    | 0px               | "Session 1: Introduction" title        |
| --text-session-desc     | 13px | 500    | 1.4    | 0px               | Deskripsi sesi (Evaluasi postur...)    |
| --text-status-badge     | 10px | 700    | 1.0    | 0.5px (uppercase) | "SELESAI"/"AKTIF"/"TERKUNCI" badge     |
| --text-date-pill        | 12px | 600    | 1.2    | 0px               | "12 Okt 2023" date pill                |
| --text-progress-label   | 11px | 700    | 1.2    | 0.5px (uppercase) | "SESI BERLANGSUNG" progress label      |
| --text-progress-pct     | 12px | 700    | 1.2    | 0px               | "65%" progress percentage              |
| --text-cta              | 15px | 800    | 1.2    | 0.3px             | "Lanjutkan Latihan" button              |
| --text-tab-label        | 9px  | 600    | 1.2    | 0.5px (uppercase) | Bottom tab labels                       |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Badge padding, tiny gaps                          |
| --space-sm     | 8px   | Icon-text gap, label gap                          |
| --space-md     | 12px  | Inter-element gap                                 |
| --space-base   | 16px  | Screen horizontal padding, card padding           |
| --space-lg     | 20px  | Node-to-content gap, banner padding               |
| --space-xl     | 24px  | Section / timeline item separation                |
| --space-2xl    | 32px  | Major block separation                            |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 6px   | Status badge, date pill                          |
| --radius-md    | 12px  | Progress card inner, date pill                   |
| --radius-lg    | 16px  | Completion block, active session card, info banner|
| --radius-pill  | 999px | Badge pill, progress bar, CTA                     |
| --radius-full  | 50%   | Timeline node, avatar top bar                     |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards default               |
| --shadow-node    | 0 0 16px rgba(245,197,24,0.45)        | Glow node aktif (play)      |
| --shadow-cta     | 0 0 18px rgba(245,197,24,0.35)        | Glow "Lanjutkan Latihan"    |
| --shadow-navbar  | 0 -2px 12px rgba(0,0,0,0.5)           | Bottom tab bar elevation    |

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Design Canvas:  430 × 932 px (mobile portrait)
Screen Padding: 16px horizontal
Safe Area Top:  ~44px (status bar device)
Top Bar:        100% width × ~64px (back + title + avatar)
Bottom Tab Bar: 100% width × 72px (fixed bottom, + safe-area-inset-bottom)
Content Scroll: vertical, padding-bottom 88px (ruang untuk tab bar)
Timeline:       node kolom kiri (~56px) + garis konektor + konten kanan (flex 1)
Node Size:      48px diameter, garis konektor 2px center-aligned
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ (←) Program Progress           (👤)   │  ← Top Bar
├──────────────────────────────────────┤
│ ┌──────────────────────────────────┐ │
│ │ COMPLETION STATUS                │ │  ← Completion Block
│ │ 40%                               │ │
│ │ ▓▓▓▓▓▓░░░░░░░░░░░░░░░░░░          │ │  ← Progress Bar 40%
│ └──────────────────────────────────┘ │
│ ┃ (i) Sesi berikutnya terbuka       │ │  ← Info Banner (rail kuning)
│ ┃     setelah sesi aktif selesai... │ │
│  ●─┐                                  │
│ (✓)│ Session 1: Introduction [SELESAI]│  ← Timeline: DONE (hijau)
│  │ │ Evaluasi postur & pernapasan    │
│  │ │ [📅 12 Okt 2023]                │
│  │                                    │
│ (▶)│ Session 2: Core Found.  [AKTIF] │  ← Timeline: ACTIVE (kuning play)
│  │ │ Penguatan otot inti...          │
│  │ │ ┌──────────────────────────┐    │
│  │ │ │ SESI BERLANGSUNG    65%  │    │  ← Active Session Card
│  │ │ │ ▓▓▓▓▓▓▓▓▓▓▓▓░░░░░░       │    │
│  │ │ │ [ Lanjutkan Latihan → ]  │    │  ← CTA
│  │ │ └──────────────────────────┘    │
│  │                                    │
│ (🔒)│ Session 3: Power & Force[TERKUNCI]│ ← Timeline: LOCKED (abu)
│  │ │ Explosive movements...          │
│  │                                    │
│ (🔒)│ Session 4: Final Peak [TERKUNCI]│  ← Timeline: LOCKED (abu)
│     │ Max intensity & assessment     │
├──────────────────────────────────────┤
│ 🏠     📅     👥      ⚡      👤    │  ← Bottom Tab Bar (TRAINER)
│ HOME JADWAL KLIEN PROGRAM PROFIL     │  ← PROGRAM active
└──────────────────────────────────────┘
```

---

## 5. KOMPONEN: TOP BAR

### 5.1 Container
```
Display:        flex, align-items center, justify-content space-between
Padding:        16px
Margin-top:     safe-area-inset-top
Height:         ~64px
```

### 5.2 Kiri — Back + Title
```
Display:        flex, align-items center, gap 12px
Back Icon:      ← arrow, 22px, color #FFFFFF
Title:          "Program Progress" → 20px, weight 800, color #FFFFFF
```

### 5.3 Kanan — Avatar
```
Avatar:         36px × 36px, border-radius 50%, border 1.5px solid #F5C518, object-fit cover
```

---

## 6. KOMPONEN: COMPLETION STATUS BLOCK

```
Background:     #141414
Border:         1px solid #262626
Border-radius:  16px
Padding:        24px 20px
Margin:         8px 16px 20px
Position:       relative (untuk watermark absolute)
Overflow:       hidden

Label:
  Text:         "COMPLETION STATUS" → 12px, weight 700, uppercase, letter-spacing 2px, color #B0B0B0

Percent (margin-top 8px, baseline align):
  Big:          "40" → 56px, weight 800, color #F5C518, letter-spacing -1px
  Unit:         "%" → 20px, weight 700, color #6B6B6B (margin-left 4px)

Watermark "UNLK":
  Position:     absolute, right 0, vertically centered (di belakang)
  Text:         "UNLK" → 64px, weight 800, uppercase, color rgba(245,197,24,0.06)
  Z-index:      0 (di belakang teks persen & progress)

Progress Bar (margin-top 16px):
  Track:        height 6px, background #2A2A2A, border-radius 999px
  Fill:         width 40%, background #F5C518, border-radius 999px
```

---

## 7. KOMPONEN: INFO BANNER

```
Background:     #161616
Border:         1px solid #262626
Border-left:    3px solid #F5C518   (accent rail)
Border-radius:  16px
Padding:        16px
Margin:         0 16px 24px
Display:        flex, align-items flex-start, gap 12px

Icon:           (i) info dalam lingkaran, 20px, color #F5C518
Text:           "Sesi berikutnya terbuka setelah sesi aktif selesai 100% dan dimulai kembali oleh trainer."
                → 13px, weight 500, line-height 1.5, color #9A9A9A
```

---

## 8. KOMPONEN: TIMELINE (Progressive Unlock)

### 8.1 Struktur Timeline
```
Layout:         flex per item (Node Column kiri + Content kanan)
Node Column:    width ~56px, posisi node center; garis konektor vertikal 2px
                color #2A2A2A menghubungkan antar node (center-aligned)
Content:        flex 1, padding-left 12px, margin-bottom 24px (gap antar sesi)
```

### 8.2 Node — DONE (Session 1, SELESAI)
```
Size:           48px × 48px, border-radius 50%
Background:     rgba(46,189,133,0.15)
Border:         2px solid #2EBD85
Icon:           ✓ check, 22px, color #2EBD85
```

### 8.3 Node — ACTIVE (Session 2, AKTIF)
```
Size:           48px × 48px, border-radius 50%
Background:     #F5C518 (kuning solid)
Icon:           ▶ play, 20px, color #0E0E0E
Box-shadow:     0 0 16px rgba(245,197,24,0.45)  (glow)
```

### 8.4 Node — LOCKED (Session 3 & 4, TERKUNCI)
```
Size:           48px × 48px, border-radius 50%
Background:     #1C1C1C
Border:         1px solid #3A3A3A
Icon:           🔒 lock, 20px, color #6B6B6B
```

### 8.5 Content — DONE State (Session 1)
```
Title Row (flex, justify space-between, align flex-start):
  Title:        "Session 1: Introduction" → 20px, weight 800, color #FFFFFF
  Badge:        "SELESAI" → 10px, weight 700, uppercase, color #2EBD85,
                bg rgba(46,189,133,0.15), padding 4px 10px, border-radius 6px
Description:    "Evaluasi postur & Dasar pernapasan" → 13px, weight 500, color #9A9A9A, margin-top 6px
Date Pill (margin-top 12px):
  Background:   #1A1A1A
  Border:       1px solid #262626
  Border-radius:12px
  Padding:      12px 14px
  Content:      📅 + "12 Okt 2023" → 12px, weight 600, color #9A9A9A
```

### 8.6 Content — ACTIVE State (Session 2)
```
Title:          "Session 2: Core Foundation" → 20px, weight 800, color #F5C518
Badge:          "AKTIF" → 10px, weight 700, uppercase, color #0E0E0E,
                bg #F5C518, padding 4px 10px, border-radius 6px
Description:    "Penguatan otot inti & Stabilitas pelvis" → 13px, weight 500, color #9A9A9A, margin-top 6px

Active Session Card (margin-top 14px):
  Background:   #141414
  Border:       1px solid rgba(245,197,24,0.4)
  Border-radius:16px
  Padding:      16px

  Progress Row (flex, justify space-between, align center):
    Label:      "SESI BERLANGSUNG" → 11px, weight 700, uppercase, letter-spacing 0.5px, color #9A9A9A
    Percent:    "65%" → 12px, weight 700, color #F5C518
  Progress Bar (margin-top 10px):
    Track:      height 6px, background #2A2A2A, border-radius 999px
    Fill:       width 65%, background #F5C518, border-radius 999px

  CTA "Lanjutkan Latihan" (margin-top 14px):
    Width:      100%
    Background: #F5C518
    Color:      #0E0E0E
    Padding:    14px 0, border-radius 999px
    Content:    "Lanjutkan Latihan →" → 15px, weight 800, text-align center, gap 8px (arrow icon)
    Box-shadow: 0 0 18px rgba(245,197,24,0.35)
    Behavior:   tap → masuk mode latihan sesi aktif
```

### 8.7 Content — LOCKED State (Session 3 & 4)
```
Title:          "Session 3: Power & Force" / "Session 4: Final Peak"
                → 20px, weight 800, color #6B6B6B (muted)
Badge:          "TERKUNCI" → 10px, weight 700, uppercase, color #6B6B6B,
                bg #1C1C1C, padding 4px 10px, border-radius 6px
Description:    "Explosive movements & Hypertrophy basics" / "Max intensity & Performance assessment"
                → 13px, weight 500, color #6B6B6B, margin-top 6px
State:          non-interaktif (tidak ada CTA); seluruh konten dim/muted
```

---

## 9. KOMPONEN: BOTTOM TAB BAR (TRAINER VARIANT)

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
Label:          9px, weight 600, uppercase, letter-spacing 0.5px, color #6B6B6B
```

### 9.3 Tab Item (Active — PROGRAM)
```
Icon:           22px, color #F5C518
Label-color:    #F5C518
Indicator:      highlight pill bg di belakang ikon PROGRAM
                (bg rgba(245,197,24,0.12), border-radius 12px)
```

### 9.4 Daftar Tabs (5 item — VERSI TRAINER)
```
1. 🏠  HOME
2. 📅  JADWAL
3. 👥  KLIEN
4. ⚡  PROGRAM    ← ACTIVE (kuning)
5. 👤  PROFIL
```

---

## 10. GRID RECAP — RINGKASAN ZONA LAYOUT (Mobile)

| Zone                    | X Offset | Y Offset  | Width            | Height     |
|-------------------------|----------|-----------|------------------|------------|
| Top Bar                 | 0        | safe-top  | 100%             | ~64px      |
| Completion Status Block | 16px     | ~96px     | calc(100% - 32px)| ~150px     |
| Info Banner             | 16px     | ~266px    | calc(100% - 32px)| ~90px      |
| Timeline Node Column    | 16px     | ~380px    | ~56px            | auto       |
| Session 1 (DONE)        | 72px     | ~380px    | calc(100% - 88px)| ~150px     |
| Session 2 (ACTIVE)      | 72px     | ~560px    | calc(100% - 88px)| ~250px     |
| Session 3 (LOCKED)      | 72px     | ~840px    | calc(100% - 88px)| ~110px     |
| Session 4 (LOCKED)      | 72px     | ~980px    | calc(100% - 88px)| ~110px     |
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px       |

*Catatan: konten melebihi tinggi viewport (932px) → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 11. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Program Progress Screen (Progressive Unlock Timeline, Pro Trainer, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Progressive Unlock Timeline.png
   Generated: 2026-06-27
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:        #0E0E0E;
  --color-bg-card:           #141414;
  --color-bg-card-alt:       #1A1A1A;
  --color-bg-banner:         #161616;
  --color-bg-chip:           #1C1C1C;
  --color-bg-navbar:         #121212;
  --color-accent-primary:    #F5C518;
  --color-accent-hover:      #E0B200;
  --color-text-primary:      #FFFFFF;
  --color-text-secondary:    #9A9A9A;
  --color-text-muted:        #6B6B6B;
  --color-text-on-accent:    #0E0E0E;
  --color-status-label:      #B0B0B0;
  --color-percent-big:       #F5C518;
  --color-percent-unit:      #6B6B6B;
  --color-watermark:         rgba(245,197,24,0.06);
  --color-progress-track:    #2A2A2A;
  --color-progress-fill:     #F5C518;
  --color-info-icon:         #F5C518;
  --color-info-rail:         #F5C518;
  --color-node-done:         #2EBD85;
  --color-node-done-bg:      rgba(46,189,133,0.15);
  --color-node-active:       #F5C518;
  --color-node-active-glow:  rgba(245,197,24,0.45);
  --color-node-locked:       #3A3A3A;
  --color-node-locked-icon:  #6B6B6B;
  --color-timeline-line:     #2A2A2A;
  --color-badge-done:        #2EBD85;
  --color-badge-done-bg:     rgba(46,189,133,0.15);
  --color-badge-active:      #0E0E0E;
  --color-badge-active-bg:   #F5C518;
  --color-badge-locked:      #6B6B6B;
  --color-badge-locked-bg:   #1C1C1C;
  --color-border-card:       #262626;
  --color-border-active-card:rgba(245,197,24,0.4);
  --color-cta-bg:            #F5C518;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.35);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-topbar-title:       20px;
  --text-status-label:       12px;
  --text-percent-big:        56px;
  --text-percent-unit:       20px;
  --text-watermark:          64px;
  --text-info-banner:        13px;
  --text-session-title:      20px;
  --text-session-desc:       13px;
  --text-status-badge:       10px;
  --text-date-pill:          12px;
  --text-progress-label:     11px;
  --text-progress-pct:       12px;
  --text-cta:                15px;
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
  --radius-sm:               6px;
  --radius-md:               12px;
  --radius-lg:               16px;
  --radius-pill:             999px;
  --radius-full:             50%;

  /* ── SHADOWS ── */
  --shadow-card:             0 2px 8px rgba(0,0,0,0.4);
  --shadow-node:             0 0 16px rgba(245,197,24,0.45);
  --shadow-cta:              0 0 18px rgba(245,197,24,0.35);
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --topbar-height:           64px;
  --navbar-height:           72px;
  --node-size:               48px;
  --node-column-width:       56px;
  --timeline-line-width:     2px;
  --card-radius:             16px;
  --tab-count:               5;
}
```

---

## 12. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Progressive Unlock Timeline.png`. Semua teks (Program Progress, COMPLETION STATUS, 40%, UNLK watermark, Sesi berikutnya terbuka setelah sesi aktif selesai 100% dan dimulai kembali oleh trainer., Session 1: Introduction, SELESAI, Evaluasi postur & Dasar pernapasan, 12 Okt 2023, Session 2: Core Foundation, AKTIF, Penguatan otot inti & Stabilitas pelvis, SESI BERLANGSUNG, 65%, Lanjutkan Latihan, Session 3: Power & Force, TERKUNCI, Explosive movements & Hypertrophy basics, Session 4: Final Peak, Max intensity & Performance assessment) harus persis sama dengan gambar.

2. **TRAINER SIDE (Bukan Member)**: Bagian dari keluarga Trainer-side (lihat HOME_PT_DASHBOARD, TRAINER_SCHEDULE, CREATE_PROGRAM_FORM & EDIT_TRAINING_SESSION specs). Bottom tab bar versi trainer: **HOME / JADWAL / KLIEN / PROGRAM / PROFIL** dengan **PROGRAM aktif**. Jangan tertukar dengan tab bar member.

3. **Relasi dengan Buat Program / Buat Sesi**: Layar ini menampilkan eksekusi/progres dari program yang dibuat di CREATE_PROGRAM_FORM (struktur sesi) & diisi latihan di EDIT_TRAINING_SESSION. Tiap "Session N" di timeline = satu kartu SESI di Buat Program. Sinkronkan judul & jumlah sesi.

4. **Progressive Unlock Logic**: Inti layar ini adalah sistem unlock bertahap — sesi terbuka berurutan. Sesi SELESAI (hijau ✓) → AKTIF (kuning ▶) → TERKUNCI (abu 🔒). Sesi berikutnya hanya terbuka setelah sesi aktif 100% selesai DAN di-restart oleh trainer (lihat info banner). Implementasikan state machine: done → active → locked.

5. **Completion Status & Watermark**: Persen besar (40%) = progres keseluruhan program (mis. jumlah sesi selesai/total). Watermark "UNLK" (singkatan "UNLOCK") dekoratif di belakang dengan opacity sangat rendah (~6%) — pastikan tidak mengganggu keterbacaan. Progress bar mencerminkan persen yang sama.

6. **Info Banner**: Banner dengan accent rail kuning + ikon (i) menjelaskan aturan unlock. Konsisten pola accent rail dengan request/session card di spec lain. Bersifat informatif, non-interaktif.

7. **Timeline Structure**: Layout dua kolom — node column (kiri) dengan garis konektor vertikal, dan konten (kanan). Garis konektor `#2A2A2A` 2px menyambung antar node center-aligned. Node terakhir tidak memerlukan garis setelahnya.

8. **Node 3-State (warna = status)**: DONE = hijau `#2EBD85` ring + ✓; ACTIVE = kuning solid `#F5C518` + ▶ play + glow; LOCKED = abu `#1C1C1C`/border `#3A3A3A` + 🔒. Warna node, badge, dan teks judul harus konsisten per status (active title kuning, locked title muted).

9. **Status Badge per-Sesi**: "SELESAI" (hijau tinted), "AKTIF" (kuning solid teks gelap), "TERKUNCI" (abu pada bg gelap). Badge ditempatkan di kanan title row. Jangan andalkan warna saja — sertakan teks badge untuk aksesibilitas.

10. **Active Session Card**: Hanya sesi AKTIF yang punya kartu interaktif berisi progress bar "SESI BERLANGSUNG" (65%) + CTA "Lanjutkan Latihan →". Border kartu memakai kuning subtle `rgba(245,197,24,0.4)`. Persen di sini = progres dalam sesi itu (berbeda dari completion keseluruhan 40%).

11. **CTA Lanjutkan Latihan**: Tombol kuning pill full-width dengan panah → + glow. Tap → masuk mode eksekusi latihan sesi aktif. Hanya muncul pada sesi AKTIF; sesi DONE & LOCKED tidak punya CTA.

12. **Locked State (non-interaktif)**: Sesi terkunci seluruhnya di-dim (teks muted `#6B6B6B`), tanpa CTA atau date pill, dan tidak dapat di-tap. Beri `aria-disabled="true"` & feedback bila user mencoba tap ("Selesaikan sesi sebelumnya untuk membuka").

13. **Scroll & Padding**: Konten (4 sesi + blok atas) melebihi viewport → scroll vertikal. Beri `padding-bottom:88px` agar sesi terbawah tidak tertutup tab bar. Garis timeline ikut ter-scroll bersama konten.

14. **Accessibility**: Beri `aria-current="page"` pada tab PROGRAM. Timeline gunakan `<ol>` semantik (urutan sesi penting). Tiap node sertakan status teks (selesai/aktif/terkunci), jangan warna saja. Progress bar gunakan `role="progressbar"` + `aria-valuenow`. CTA beri `aria-label` ("Lanjutkan Latihan Session 2: Core Foundation"). Sesi terkunci `aria-disabled`. Watermark `aria-hidden="true"`. Kontras teks gelap pada elemen kuning/hijau penuhi WCAG AA. Touch target minimum 44×44px.

---

*Spec ini generated dari analisis visual screen Progressive Unlock Timeline.png (visual-verified).*
*Design system reference: Egg Gym — Home PT Dashboard, Trainer Schedule (TRAINER_SCHEDULE_UI_SPEC.md), Create Program Form (CREATE_PROGRAM_FORM_UI_SPEC.md), Edit Training Session (EDIT_TRAINING_SESSION_UI_SPEC.md) & Member specs. CATATAN: sisi TRAINER, bottom tab bar HOME/JADWAL/KLIEN/PROGRAM/PROFIL, PROGRAM aktif. Layar ini menampilkan progres/eksekusi program (timeline unlock bertahap).*
*Total sections: 12 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

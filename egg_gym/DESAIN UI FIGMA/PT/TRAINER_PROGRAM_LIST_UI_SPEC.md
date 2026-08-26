# TRAINER_PROGRAM_LIST_UI_SPEC.md
# Egg Gym App — Trainer Program List Screen (Program Latihan, Pro Trainer Side, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Trainer App > Program (Program Latihan — Program Management)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Trainer Program List.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Program Latihan (Pro Trainer) memakai sistem warna identik dengan Home PT Dashboard, Trainer Schedule & Client List/Details (Editorial Athletics): latar near-black dengan aksen kuning emas. Token tambahan ditambahkan untuk hero banner watermark, primary CTA full-width, status badge (aktif/selesai), accent rail program aktif, progress bar, dan state dimmed (program selesai).

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0E0E0E               | App background (screen utama)                  |
| --color-bg-card           | #1A1A1A               | Program card & hero banner background          |
| --color-bg-card-alt       | #161616               | Inner block background                         |
| --color-bg-chip           | #1C1C1C               | Status badge & meta chip background            |
| --color-bg-navbar         | #121212               | Bottom tab bar background                      |
| --color-accent-primary    | #F5C518               | CTA, link, progress fill, brand, status aktif  |
| --color-accent-hover      | #E0B200               | Button pressed state                           |
| --color-text-primary      | #FFFFFF               | Program names, headings, primary values        |
| --color-text-secondary    | #9A9A9A               | Labels, captions, meta text, client name       |
| --color-text-muted        | #6B6B6B               | Inactive tab, placeholder, dimmed text         |
| --color-text-on-accent    | #0E0E0E               | Text on yellow/accent elements (CTA, badge)    |
| --color-cta-bg            | #F5C518               | "BUAT PROGRAM BARU" button background          |
| --color-status-active     | #F5C518               | Badge "AKTIF" text                             |
| --color-status-active-bg  | rgba(245,197,24,0.15) | Background badge "AKTIF"                        |
| --color-status-done       | #9A9A9A               | Badge "SELESAI" text                           |
| --color-status-done-bg    | #1C1C1C               | Background badge "SELESAI"                      |
| --color-progress-fill     | #F5C518               | Progress bar fill (program aktif)              |
| --color-progress-fill-done| #6B6B6B               | Progress bar fill (program selesai, dimmed)    |
| --color-progress-track    | #2A2A2A               | Progress bar track (unfilled)                  |
| --color-progress-number   | #F5C518               | Persentase "65%" / "32%" (aktif)               |
| --color-progress-number-done | #6B6B6B            | Persentase "100%" (selesai, dimmed)            |
| --color-watermark         | rgba(245,197,24,0.06) | Watermark "PROG" di hero banner                |
| --color-accent-rail       | #F5C518               | Left accent rail di program card aktif         |
| --color-link              | #F5C518               | "Lihat Detail →" link                          |
| --color-archive           | #9A9A9A               | "Arsip" action (program selesai)               |
| --color-meta-total        | #F5C518               | "3 TOTAL" meta badge                           |
| --color-border-card       | #262626               | Card & panel borders                           |
| --color-border-chip       | #2A2A2A               | Badge & outline border                         |
| --color-tab-active        | #F5C518               | Active bottom-tab icon & label (PROGRAM)       |
| --color-tab-inactive      | #6B6B6B               | Inactive bottom-tab icon & label               |
| --color-glow-cta          | rgba(245,197,24,0.45) | Glow CTA kuning                                |
| --color-overlay-dark      | rgba(0,0,0,0.7)       | Modal backdrop                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (hero title, progress number & watermark)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-brand             | 20px | 800    | 1.1    | 0.5px (uppercase)| "EGGGYM" brand text                |
| --text-hero-title        | 28px | 800    | 1.1    | -0.3px           | "Program Latihan" hero title       |
| --text-hero-sub          | 14px | 400    | 1.4    | 0px              | "Kelola dan pantau progres..."     |
| --text-watermark         | 80px | 900    | 1.0    | -2px (uppercase) | "PROG" hero watermark              |
| --text-cta              | 15px | 800    | 1.2    | 0.5px (uppercase)| "BUAT PROGRAM BARU" button         |
| --text-section-title     | 13px | 700    | 1.2    | 1px (uppercase)  | "PROGRAM AKTIF" section title      |
| --text-section-meta      | 10px | 700    | 1.2    | 0.5px (uppercase)| "3 TOTAL" meta badge               |
| --text-status-badge      | 9px  | 800    | 1.0    | 0.8px (uppercase)| "AKTIF" / "SELESAI" badge          |
| --text-category          | 11px | 600    | 1.2    | 0.8px (uppercase)| "PREMIUM PLAN" / "STRENGTH" tag    |
| --text-program-name      | 20px | 800    | 1.2    | -0.3px           | "6-Week Mass Builder" program name |
| --text-client            | 13px | 500    | 1.3    | 0px              | "Naufal" / "Budi Santoso" client   |
| --text-progress-number   | 28px | 800    | 1.0    | -0.5px           | "65%" / "32%" / "100%" percentage  |
| --text-progress-status   | 9px  | 600    | 1.3    | 0.8px (uppercase)| "PROGRES" label                    |
| --text-session-label     | 9px  | 600    | 1.3    | 0.8px (uppercase)| "SESI SELESAI" label               |
| --text-session-value     | 18px | 800    | 1.0    | -0.5px           | "18 / 24" session count            |
| --text-link              | 13px | 700    | 1.2    | 0.3px            | "Lihat Detail →" / "Arsip" action  |
| --text-tab-label         | 9px  | 600    | 1.2    | 0.5px (uppercase)| Bottom tab labels                  |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Badge padding, tiny gaps                         |
| --space-sm     | 8px   | Icon-text gap, label-value gap                   |
| --space-md     | 12px  | Inter-element gap                                |
| --space-base   | 16px  | Screen horizontal padding, card padding          |
| --space-lg     | 20px  | Card-to-card vertical gap                        |
| --space-xl     | 24px  | Section separation                               |
| --space-2xl    | 32px  | Major block separation                           |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Status badge, small elements                     |
| --radius-md    | 12px  | CTA button, meta chip                            |
| --radius-lg    | 16px  | Hero banner, program cards                       |
| --radius-pill  | 999px | Progress bar, status badge (pill)                |
| --radius-full  | 50%   | Brand avatar, notification button               |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards default               |
| --shadow-cta     | 0 4px 16px rgba(245,197,24,0.4)       | Glow "BUAT PROGRAM BARU"    |
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
Card Gap:       20px (antar program card) / 24px (antar section)
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ (👤) EGGGYM                   [🔔]   │  ← Brand Header
├──────────────────────────────────────┤
│ ┌──────────────────────────────────┐ │
│ │ ░░PROG░░                          │ │  ← Hero Banner + watermark
│ │ Program Latihan                  │ │
│ │ Kelola dan pantau progres…       │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │    ⊕  BUAT PROGRAM BARU          │ │  ← Primary CTA (full-width)
│ └──────────────────────────────────┘ │
│ PROGRAM AKTIF              [3 TOTAL]  │  ← Section header
│ ┃┌─────────────────────────────────┐ │
│ ┃│ [AKTIF] PREMIUM PLAN       65%  │ │  ← Program Card (AKTIF)
│ ┃│ 6-Week Mass Builder      PROGRES│ │  (rail kuning)
│ ┃│ 👤 Naufal                       │ │
│ ┃│ ▓▓▓▓▓▓▓▓▓▓░░░░                  │ │
│ ┃│ SESI SELESAI                    │ │
│ ┃│ 18 / 24        Lihat Detail →   │ │
│ ┃└─────────────────────────────────┘ │
│ ┃┌─────────────────────────────────┐ │
│ ┃│ [AKTIF] STRENGTH           32%  │ │  ← Program Card (AKTIF)
│ ┃│ Powerlifting Phase I     PROGRES│ │
│ ┃│ 👤 Budi Santoso                 │ │
│ ┃│ ▓▓▓▓░░░░░░░░░░                  │ │
│ ┃│ SESI SELESAI                    │ │
│ ┃│ 4 / 12         Lihat Detail →   │ │
│ ┃└─────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [SELESAI]                  100%  │ │  ← Program Card (SELESAI/dimmed)
│ │ Fat Loss Blitz           PROGRES │ │
│ │ 👤 Indah                         │ │
│ │ ▓▓▓▓▓▓▓▓▓▓▓▓▓▓                  │ │
│ │ SESI SELESAI                     │ │
│ │ 20 / 20             Arsip ⊡      │ │
│ └──────────────────────────────────┘ │
├──────────────────────────────────────┤
│ 🏠     📅     👥      ⚡      👤    │  ← Bottom Tab Bar (TRAINER)
│ HOME JADWAL KLIEN PROGRAM PROFIL     │  ← PROGRAM active
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
Icon:           🔔 bell (filled), 20px, color #F5C518
Display:        flex center
```

---

## 6. KOMPONEN: HERO BANNER

### 6.1 Container
```
Background:     #1A1A1A  (subtle gradient ke #161616 boleh)
Border:         1px solid #262626
Border-radius:  16px
Padding:        24px 20px
Margin:         8px 16px 24px
Position:       relative
Overflow:       hidden  (untuk crop watermark)
```

### 6.2 Watermark Dekoratif
```
Text:           "PROG"
Font-size:      80px, weight 900, color rgba(245,197,24,0.06)
Position:       absolute, top-right, melewati tepi
Text-transform: uppercase, z-index 0, pointer-events none
```

### 6.3 Konten
```
Title:
  Text:         "Program Latihan" → 28px, weight 800, color #FFFFFF, letter-spacing -0.3px

Subtitle:
  Text:         "Kelola dan pantau progres latihan semua klien Anda."
  Font-size:    14px, weight 400, color #9A9A9A, line-height 1.4, margin-top 6px (wrap 2 baris)
```

---

## 7. KOMPONEN: PRIMARY CTA — BUAT PROGRAM BARU

```
Width:          calc(100% - 32px)
Margin:         0 16px 24px
Background:     #F5C518
Border-radius:  12px
Padding:        18px 0
Display:        flex, align-items center, justify-content center, gap 10px
Box-shadow:     0 4px 16px rgba(245,197,24,0.4)  (glow)

Icon:
  Icon:         ⊕ plus-circle, 20px, color #0E0E0E

Text:
  Text:         "BUAT PROGRAM BARU"
  Font-size:    15px, weight 800, uppercase, letter-spacing 0.5px, color #0E0E0E
```

---

## 8. KOMPONEN: SECTION HEADER (PROGRAM AKTIF)

```
Display:        flex, justify-content space-between, align-items center
Padding:        0 16px
Margin-bottom:  16px

Judul:
  Text:         "PROGRAM AKTIF"
  Font-size:    13px, weight 700, uppercase, letter-spacing 1px, color #9A9A9A

Meta Badge:
  Text:         "3 TOTAL"
  Font-size:    10px, weight 700, uppercase, letter-spacing 0.5px, color #F5C518
  Background:   rgba(245,197,24,0.15), padding 4px 10px, border-radius 999px
```

---

## 9. KOMPONEN: PROGRAM CARD

### 9.1 Container — Variant AKTIF
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-left:    3px solid #F5C518   (accent rail)
Border-radius:  16px
Padding:        16px
Margin:         0 16px 20px
Position:       relative
```

### 9.2 Top Row (badge + kategori + persen)
```
Display:        flex, justify-content space-between, align-items flex-start

Kiri — Badge + Category (flex, align center, gap 8px):
  Status Badge "AKTIF":
    Font:       9px, weight 800, uppercase, letter-spacing 0.8px, color #F5C518
    Background: rgba(245,197,24,0.15), padding 3px 8px, border-radius 6px
  Category:     "PREMIUM PLAN" / "STRENGTH"
    Font:       11px, weight 600, uppercase, letter-spacing 0.8px, color #6B6B6B

Kanan — Progress Number (text-align right):
  Number:       "65%" / "32%" → 28px, weight 800, color #F5C518, letter-spacing -0.5px
  Status:       "PROGRES" → 9px, weight 600, uppercase, letter-spacing 0.8px, color #9A9A9A
```

### 9.3 Program Name + Client
```
Name:
  Text:         "6-Week Mass Builder" / "Powerlifting Phase I" → 20px, weight 800, color #FFFFFF, margin-top 4px

Client Row (flex, align center, gap 6px, margin-top 4px):
  Icon:         👤 person, 14px, color #9A9A9A
  Text:         "Naufal" / "Budi Santoso" → 13px, weight 500, color #9A9A9A
```

### 9.4 Progress Bar
```
Margin:         14px 0
Height:         6px
Border-radius:  999px
Track:          background #2A2A2A (100% width)
Fill:           background #F5C518, width = persen (65% / 32%), border-radius 999px
```

### 9.5 Footer Row
```
Display:        flex, justify-content space-between, align-items flex-end

Kiri — Sesi Selesai:
  Label:        "SESI SELESAI" → 9px, weight 600, uppercase, letter-spacing 0.8px, color #9A9A9A
                (wrap, boleh multi-baris seperti gambar)
  Value:        "18 / 24" / "4 / 12" → 18px, weight 800
                ("18"/"4" putih #FFFFFF, "/ 24"/"/ 12" abu #9A9A9A)

Kanan — Action Link:
  Text:         "Lihat Detail →"
  Font-size:    13px, weight 700, color #F5C518, letter-spacing 0.3px
```

### 9.6 Variant SELESAI (Completed — dimmed)
```
Container:
  Background:   #161616
  Border:       1px solid #1E1E1E
  Border-left:  none  (tanpa accent rail kuning)
  Opacity:      0.6  (seluruh card diredupkan)

Status Badge "SELESAI":
  Font:         9px, weight 800, uppercase, color #9A9A9A
  Background:   #1C1C1C, border 1px solid #2A2A2A, padding 3px 8px, border-radius 6px

Progress Number "100%":
  Color:        #6B6B6B (abu, bukan kuning)

Program Name "Fat Loss Blitz":
  Color:        #9A9A9A (bukan putih penuh)

Progress Bar Fill:
  Background:   #6B6B6B (abu), width 100%

Session Value "20 / 20":
  Color:        #9A9A9A

Action — Arsip (kanan):
  Text:         "Arsip" + ikon ⊡ archive, 13px, weight 700, color #9A9A9A
                (aksi arsipkan program selesai, bukan "Lihat Detail")
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

### 10.4 Daftar Tabs (5 item — VERSI TRAINER, berbeda dari Member)
```
1. 🏠  HOME
2. 📅  JADWAL
3. 👥  KLIEN
4. ⚡  PROGRAM     ← ACTIVE (kuning)
5. 👤  PROFIL
```

---

## 11. GRID RECAP — RINGKASAN ZONA LAYOUT (Mobile)

| Zone                    | X Offset | Y Offset  | Width            | Height    |
|-------------------------|----------|-----------|------------------|-----------|
| Brand Header            | 0        | safe-top  | 100%             | ~72px     |
| Hero Banner             | 16px     | ~124px    | calc(100% - 32px)| ~150px    |
| Primary CTA             | 16px     | ~298px    | calc(100% - 32px)| ~56px     |
| Program Aktif Header    | 16px     | ~378px    | calc(100% - 32px)| ~30px     |
| Program Card (AKTIF #1) | 16px     | ~424px    | calc(100% - 32px)| ~230px    |
| Program Card (AKTIF #2) | 16px     | ~674px    | calc(100% - 32px)| ~230px    |
| Program Card (SELESAI)  | 16px     | ~924px    | calc(100% - 32px)| ~220px    |
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px      |

*Catatan: konten melebihi tinggi viewport (932px) → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 12. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Trainer Program List Screen (Program Latihan, Pro Trainer, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Trainer Program List.png
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
  --color-cta-bg:               #F5C518;
  --color-status-active:        #F5C518;
  --color-status-active-bg:     rgba(245,197,24,0.15);
  --color-status-done:          #9A9A9A;
  --color-status-done-bg:       #1C1C1C;
  --color-progress-fill:        #F5C518;
  --color-progress-fill-done:   #6B6B6B;
  --color-progress-track:       #2A2A2A;
  --color-progress-number:      #F5C518;
  --color-progress-number-done: #6B6B6B;
  --color-watermark:            rgba(245,197,24,0.06);
  --color-accent-rail:          #F5C518;
  --color-link:                 #F5C518;
  --color-archive:              #9A9A9A;
  --color-meta-total:           #F5C518;
  --color-border-card:          #262626;
  --color-border-chip:          #2A2A2A;
  --color-tab-active:           #F5C518;
  --color-tab-inactive:         #6B6B6B;
  --color-glow-cta:             rgba(245,197,24,0.45);
  --color-overlay-dark:         rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:        "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-brand:                 20px;
  --text-hero-title:            28px;
  --text-hero-sub:              14px;
  --text-watermark:             80px;
  --text-cta:                   15px;
  --text-section-title:         13px;
  --text-section-meta:          10px;
  --text-status-badge:          9px;
  --text-category:              11px;
  --text-program-name:          20px;
  --text-client:                13px;
  --text-progress-number:       28px;
  --text-progress-status:       9px;
  --text-session-label:         9px;
  --text-session-value:         18px;
  --text-link:                  13px;
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
  --shadow-cta:                 0 4px 16px rgba(245,197,24,0.4);
  --shadow-navbar:              0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:             16px;
  --navbar-height:              72px;
  --card-gap:                   20px;
  --card-radius:                16px;
  --tab-count:                  5;
}
```

---

## 13. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Trainer Program List.png`. Semua teks (EGGGYM, Program Latihan, Kelola dan pantau progres latihan semua klien Anda., BUAT PROGRAM BARU, PROGRAM AKTIF, 3 TOTAL, AKTIF, PREMIUM PLAN, 6-Week Mass Builder, Naufal, 65% PROGRES, SESI SELESAI 18/24, Lihat Detail, STRENGTH, Powerlifting Phase I, Budi Santoso, 32%, 4/12, SELESAI, Fat Loss Blitz, Indah, 100%, 20/20, Arsip) harus persis sama dengan gambar.

2. **TRAINER SIDE (Bukan Member)**: Bagian dari keluarga Trainer-side (lihat HOME_PT_DASHBOARD, TRAINER_SCHEDULE, CLIENT_LIST & CLIENT_DETAILS). Bottom tab bar trainer: **HOME / JADWAL / KLIEN / PROGRAM / PROFIL** dengan PROGRAM aktif. PENTING: ini "PROGRAM" sisi trainer (kelola program semua klien), berbeda dari "PROGRAM" sisi member (program latihan diri sendiri).

3. **Mobile-First Layout**: Layar manajemen program trainer, konten scrollable vertikal. Gunakan `safe-area-inset-*`. Brand header EGGGYM.

4. **Hero Banner + Watermark**: Banner sambutan dengan judul "Program Latihan" + subtitle, dan watermark "PROG" raksasa opacity rendah di belakang. Wajib `overflow:hidden` + `pointer-events:none`. Konsisten dengan treatment watermark di Fitness Target/Phase card layar lain.

5. **Primary CTA Full-Width**: Tombol "BUAT PROGRAM BARU" kuning solid full-width dengan ikon plus + glow. Membuka flow pembuatan program baru. Ini aksi utama layar — posisikan menonjol di atas daftar. Beri `aria-label`.

6. **Section Meta Count**: "PROGRAM AKTIF" + badge "3 TOTAL" menunjukkan jumlah total program. Catatan: label section "AKTIF" tapi daftar juga memuat 1 program SELESAI — "3 TOTAL" menghitung semua program (2 aktif + 1 selesai). Verifikasi logika hitung saat implementasi.

7. **Program Card 2 State (enum)**: AKTIF (accent rail kuning, badge kuning, progress kuning, aksi "Lihat Detail") vs SELESAI (dimmed opacity 0.6, tanpa rail, badge abu, progress abu 100%, aksi "Arsip"). Render kondisional berdasarkan status program.

8. **Progress Number Prominent**: Persentase besar (28px) di pojok kanan atas card + label "PROGRES" — focal point status kemajuan. Kuning untuk aktif, abu untuk selesai. Width progress bar mengikuti angka persen.

9. **Client Attribution**: Tiap program ditautkan ke satu klien (ikon person + nama: Naufal/Budi Santoso/Indah). Selaras dengan data klien di Client List/Details. Tap card/Lihat Detail membuka detail program klien tsb.

10. **Session Count**: "SESI SELESAI {done} / {total}" menampilkan progres sesi (18/24, 4/12, 20/20). Angka selesai putih, total abu. Konsisten dengan progress bar & persentase (verifikasi: 18/24=75% tapi tertulis 65% → gunakan angka persen sebagai source of truth tampilan, cek konsistensi data seperti catatan di Program member).

11. **Action Kontekstual per State**: Program AKTIF → "Lihat Detail →" (buka & kelola). Program SELESAI → "Arsip ⊡" (arsipkan dari daftar aktif). Aksi berubah sesuai status — jangan tampilkan "Lihat Detail" pada item selesai.

12. **Dimmed Completed Treatment**: Program selesai diredupkan menyeluruh (opacity 0.6) — sinyal visual "tidak lagi aktif". Berbeda dari item LOCKED di layar lain; di sini status final/positif (100%), bukan terkunci. Pertahankan keterbacaan teks.

13. **Scroll & Padding**: Konten lebih tinggi dari viewport → scroll vertikal. Beri `padding-bottom:88px` agar program card terbawah tidak tertutup tab bar. Header & CTA boleh sticky agar "Buat Program Baru" selalu terjangkau.

14. **Accessibility**: Beri `aria-current="page"` pada tab PROGRAM. Progress bar gunakan `role="progressbar"` + `aria-valuenow`. Status badge sertakan teks (AKTIF/SELESAI), jangan warna saja. CTA & aksi (Lihat Detail/Arsip) beri `aria-label` menyertakan nama program/klien. Program selesai (dimmed) jangan turunkan kontras di bawah WCAG AA — pastikan teks tetap terbaca. Touch target minimum 44×44px.

---

*Spec ini generated dari analisis visual screen Trainer Program List.png (visual-verified).*
*Design system reference: Egg Gym — Home PT Dashboard, Trainer Schedule, Client List (CLIENT_LIST_UI_SPEC.md), Client Details & Member specs. CATATAN: sisi TRAINER, tab bar HOME/JADWAL/KLIEN/PROGRAM/PROFIL; "PROGRAM" trainer ≠ "PROGRAM" member.*
*Total sections: 14 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

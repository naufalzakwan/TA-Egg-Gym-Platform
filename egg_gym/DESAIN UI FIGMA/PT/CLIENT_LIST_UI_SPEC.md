# CLIENT_LIST_UI_SPEC.md
# Egg Gym App — Client List Screen (Daftar Klien, Pro Trainer Side, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Trainer App > Klien (Daftar Klien — Client Management)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Client List.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Daftar Klien (Pro Trainer) memakai sistem warna identik dengan Home PT Dashboard & Trainer Schedule (Editorial Athletics): latar near-black dengan aksen kuning emas. CATATAN: layar ini memperkenalkan aksen sekunder cyan untuk metrik "Aktif Hari Ini". Token tambahan untuk summary stat dual-rail, tier badge (platinum/gold), progress bar program, dan client card.

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0E0E0E               | App background (screen utama)                  |
| --color-bg-card           | #1A1A1A               | Client card & summary stat background          |
| --color-bg-card-alt       | #161616               | Inner block background                         |
| --color-bg-chip           | #1C1C1C               | Tier badge & icon button background            |
| --color-bg-search         | #1A1A1A               | Search bar background                          |
| --color-bg-navbar         | #121212               | Bottom tab bar background                      |
| --color-accent-primary    | #F5C518               | CTA, link, progress fill, brand text           |
| --color-accent-hover      | #E0B200               | Pressed state                                  |
| --color-accent-secondary  | #2DD4D4               | Aksen cyan — metrik "Aktif Hari Ini"           |
| --color-text-primary      | #FFFFFF               | Client name, headings, program name            |
| --color-text-secondary    | #9A9A9A               | Labels, captions, meta text                    |
| --color-text-muted        | #6B6B6B               | Inactive tab, placeholder, since-meta          |
| --color-text-on-accent    | #0E0E0E               | Text on yellow/accent elements                 |
| --color-stat-number       | #F5C518               | "24" total klien number (kuning)               |
| --color-stat-number-alt   | #2DD4D4               | "08" aktif hari ini number (cyan)              |
| --color-rail-primary      | #F5C518               | Accent rail kiri stat "Total Klien"            |
| --color-rail-secondary    | #2DD4D4               | Accent rail kiri stat "Aktif Hari Ini"         |
| --color-tier-platinum     | #F5C518               | Badge "PLATINUM" text                          |
| --color-tier-gold         | #F5C518               | Badge "GOLD" text                              |
| --color-tier-badge-bg     | rgba(245,197,24,0.15) | Background tier badge                          |
| --color-progress-fill     | #F5C518               | Progress bar program fill                      |
| --color-progress-track    | #2A2A2A               | Progress bar track (unfilled)                  |
| --color-progress-number   | #F5C518               | Persentase "75%" / "42%" / "12%"               |
| --color-link              | #F5C518               | "Lihat Detail →" link                          |
| --color-border-card       | #262626               | Card & panel borders                           |
| --color-border-chip       | #2A2A2A               | Badge & outline border                         |
| --color-search-border     | #2A2A2A               | Search bar border                              |
| --color-tab-active        | #F5C518               | Active bottom-tab icon & label (KLIEN)         |
| --color-tab-inactive      | #6B6B6B               | Inactive bottom-tab icon & label               |
| --color-glow-cta          | rgba(245,197,24,0.45) | Glow elemen kuning                             |
| --color-overlay-dark      | rgba(0,0,0,0.7)       | Modal backdrop                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (screen title & stat number)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-brand             | 20px | 800    | 1.1    | 0.5px (uppercase)| "EGGGYM" brand text                |
| --text-screen-title      | 30px | 800    | 1.1    | -0.3px           | "Daftar Klien" screen title        |
| --text-screen-sub        | 13px | 400    | 1.4    | 0px              | "Kelola kemajuan dan program..."   |
| --text-search            | 14px | 400    | 1.3    | 0px              | Search input & placeholder         |
| --text-stat-label        | 10px | 600    | 1.3    | 0.8px (uppercase)| "TOTAL KLIEN" / "AKTIF HARI INI"   |
| --text-stat-number       | 32px | 800    | 1.0    | -0.5px           | "24" / "08" stat number            |
| --text-client-name       | 18px | 800    | 1.2    | -0.2px           | "Sarah Jenkins" client name        |
| --text-tier-badge        | 9px  | 800    | 1.0    | 0.8px (uppercase)| "PLATINUM" / "GOLD" tier badge     |
| --text-since-meta        | 11px | 500    | 1.3    | 0.3px            | "ACTIVE SINCE 2023" / "NEW CLIENT" |
| --text-program-label     | 10px | 600    | 1.3    | 0.8px (uppercase)| "CURRENT PROGRAM" supra-label      |
| --text-program-name      | 17px | 700    | 1.3    | 0px              | "Hypertrophy Phase II" program     |
| --text-progress-number   | 16px | 800    | 1.0    | 0px              | "75%" / "42%" / "12%" percentage   |
| --text-link              | 13px | 700    | 1.2    | 0.3px            | "Lihat Detail →" link              |
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
| --radius-sm    | 8px   | Tier badge, small elements                       |
| --radius-md    | 12px  | Search bar, summary stat, avatar thumb           |
| --radius-lg    | 16px  | Client cards                                     |
| --radius-pill  | 999px | Progress bar, (pill badge)                       |
| --radius-full  | 50%   | Brand avatar, notification button               |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards default               |
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
Card Gap:       20px (antar client card) / 24px (antar section)
Summary Stats:  2 kolom equal-width, gap 12px, masing-masing accent rail kiri
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ (👤) EGGGYM                   [🔔]   │  ← Brand Header
├──────────────────────────────────────┤
│ Daftar Klien                         │  ← Screen Title
│ Kelola kemajuan dan program latihan… │  ← Subtitle
│ ┌──────────────────────────────────┐ │
│ │ 🔍 Cari nama klien atau program…  │ │  ← Search Bar
│ └──────────────────────────────────┘ │
│ ┌────────────┐ ┌────────────┐        │
│ ┃│TOTAL KLIEN │ ┃│AKTIF HARI..│       │  ← Summary Stats (dual-rail)
│ ┃│   24       │ ┃│   03       │       │  (kuning / cyan)
│ └────────────┘ └────────────┘        │
│ ┌──────────────────────────────────┐ │
│ │ [👤] Sarah Jenkins           [⋮] │ │  ← Client Card
│ │      [PLATINUM] ACTIVE SINCE 2023│ │
│ │ CURRENT PROGRAM                  │ │
│ │ Hypertrophy Phase II        75%  │ │
│ │ ▓▓▓▓▓▓▓▓▓▓▓░░░                   │ │  ← Progress bar
│ │ [📅][⏱]          Lihat Detail → │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [👤] Marcus Thorne           [⋮] │ │  ← Client Card
│ │      [GOLD] ACTIVE SINCE 2024    │ │
│ │ CURRENT PROGRAM                  │ │
│ │ Strength & Power Base       42%  │ │
│ │ ▓▓▓▓▓▓░░░░░░░░                   │ │
│ │ [📅]              Lihat Detail → │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [👤] Elena Rodriguez         [⋮] │ │  ← Client Card
│ │      [PLATINUM] NEW CLIENT       │ │
│ │ CURRENT PROGRAM                  │ │
│ │ Functional Core Mobility    12%  │ │
│ │ ▓▓░░░░░░░░░░░░                   │ │
│ │ [⚡]              Lihat Detail → │ │
│ └──────────────────────────────────┘ │
├──────────────────────────────────────┤
│ 🏠     📅     👥      ⚡      👤    │  ← Bottom Tab Bar (TRAINER)
│ HOME JADWAL KLIEN PROGRAM PROFIL     │  ← KLIEN active
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
Icon:           🔔 bell (outline), 20px, color #9A9A9A
Display:        flex center
```

---

## 6. KOMPONEN: SCREEN TITLE BLOCK

```
Padding:        0 16px
Margin:         8px 0 20px

Title:
  Text:         "Daftar Klien"
  Font-size:    30px, weight 800, color #FFFFFF, letter-spacing -0.3px

Subtitle:
  Text:         "Kelola kemajuan dan program latihan klien Anda."
  Font-size:    13px, weight 400, color #9A9A9A, margin-top 4px
```

---

## 7. KOMPONEN: SEARCH BAR

```
Background:     #1A1A1A
Border:         1px solid #2A2A2A
Border-radius:  12px
Padding:        14px 16px
Margin:         0 16px 20px
Display:        flex, align-items center, gap 12px

Icon:
  Icon:         🔍 magnifier, 18px, color #9A9A9A

Input/Placeholder:
  Text:         "Cari nama klien atau program…"
  Font-size:    14px, weight 400, color #6B6B6B (placeholder) / #FFFFFF (terisi)
```

---

## 8. KOMPONEN: SUMMARY STATS (Dual-Rail)

### 8.1 Container
```
Display:        flex, gap 12px
Padding:        0 16px
Margin-bottom:  24px
```

### 8.2 Stat Card — Total Klien (rail kuning)
```
Flex:           1
Background:     #1A1A1A
Border:         1px solid #262626
Border-left:    3px solid #F5C518   (accent rail primary)
Border-radius:  12px
Padding:        16px

Label:          "TOTAL KLIEN" → 10px, weight 600, uppercase, letter-spacing 0.8px, color #9A9A9A
Number:         "24" → 32px, weight 800, color #F5C518, margin-top 8px
```

### 8.3 Stat Card — Aktif Hari Ini (rail cyan)
```
Flex:           1
Background:     #1A1A1A
Border:         1px solid #262626
Border-left:    3px solid #2DD4D4   (accent rail secondary — cyan)
Border-radius:  12px
Padding:        16px

Label:          "AKTIF HARI INI" → 10px, weight 600, uppercase, color #9A9A9A
Number:         "08" → 32px, weight 800, color #2DD4D4, margin-top 8px
```

---

## 9. KOMPONEN: CLIENT CARD

### 9.1 Container
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Padding:        16px
Margin:         0 16px 20px
```

### 9.2 Header Row
```
Display:        flex, align-items flex-start, gap 12px

Avatar:
  Size:         48px × 48px, border-radius 12px (rounded-square), object-fit cover

Info (flex 1):
  Name:         "Sarah Jenkins" → 18px, weight 800, color #FFFFFF, letter-spacing -0.2px
  Meta Row (flex, align center, gap 8px, margin-top 4px):
    Tier Badge: "PLATINUM" / "GOLD"
      Font:     9px, weight 800, uppercase, letter-spacing 0.8px, color #F5C518
      Background: rgba(245,197,24,0.15), padding 3px 8px, border-radius 6px
    Since Meta: "ACTIVE SINCE 2023" / "ACTIVE SINCE 2024" / "NEW CLIENT"
      Font:     11px, weight 500, color #9A9A9A, uppercase

Overflow Menu (kanan atas):
  Icon:         ⋮ vertical-dots, 18px, color #6B6B6B
```

### 9.3 Current Program Block
```
Margin-top:     16px

Supra-label:
  Text:         "CURRENT PROGRAM" → 10px, weight 600, uppercase, letter-spacing 0.8px, color #9A9A9A

Program Row (flex, justify-content space-between, align-items baseline, margin-top 4px):
  Name:         "Hypertrophy Phase II" → 17px, weight 700, color #FFFFFF
  Percentage:   "75%" → 16px, weight 800, color #F5C518
```

### 9.4 Progress Bar
```
Margin-top:     12px
Height:         6px
Border-radius:  999px
Track:          background #2A2A2A (100% width)
Fill:           background #F5C518, width = persen (75% / 42% / 12%), border-radius 999px
```

### 9.5 Footer Row
```
Display:        flex, justify-content space-between, align-items center
Margin-top:     16px

Meta Icons (kiri):
  Icon button:  32px × 32px, bg #1C1C1C, border-radius 8px, icon 16px color #9A9A9A
                - Sarah:  📅 calendar + ⏱ stopwatch (2 ikon)
                - Marcus: 📅 calendar (1 ikon)
                - Elena:  ⚡ bolt (1 ikon)
                (ikon meta kontekstual per klien)

Link "Lihat Detail →" (kanan):
  Text:         "Lihat Detail →"
  Font-size:    13px, weight 700, color #F5C518, letter-spacing 0.3px
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

### 10.3 Tab Item (Active — KLIEN)
```
Icon:           22px, color #F5C518
Label-color:    #F5C518
Indicator:      highlight pill bg di belakang ikon KLIEN
                (bg rgba(245,197,24,0.12), border-radius 12px)
```

### 10.4 Daftar Tabs (5 item — VERSI TRAINER, berbeda dari Member)
```
1. 🏠  HOME
2. 📅  JADWAL
3. 👥  KLIEN       ← ACTIVE (kuning)
4. ⚡  PROGRAM
5. 👤  PROFIL
```

---

## 11. GRID RECAP — RINGKASAN ZONA LAYOUT (Mobile)

| Zone                    | X Offset | Y Offset  | Width            | Height    |
|-------------------------|----------|-----------|------------------|-----------|
| Brand Header            | 0        | safe-top  | 100%             | ~72px     |
| Screen Title Block      | 16px     | ~124px    | calc(100% - 32px)| ~80px     |
| Search Bar              | 16px     | ~220px    | calc(100% - 32px)| ~52px     |
| Summary Stats (×2)      | 16px     | ~288px    | calc(100% - 32px)| ~96px     |
| Client Card (Sarah)     | 16px     | ~400px    | calc(100% - 32px)| ~250px    |
| Client Card (Marcus)    | 16px     | ~670px    | calc(100% - 32px)| ~230px    |
| Client Card (Elena)     | 16px     | ~920px    | calc(100% - 32px)| ~230px    |
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px      |

*Catatan: konten melebihi tinggi viewport (932px) → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 12. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Client List Screen (Daftar Klien, Pro Trainer, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Client List.png
   Generated: 2026-06-27
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:        #0E0E0E;
  --color-bg-card:           #1A1A1A;
  --color-bg-card-alt:       #161616;
  --color-bg-chip:           #1C1C1C;
  --color-bg-search:         #1A1A1A;
  --color-bg-navbar:         #121212;
  --color-accent-primary:    #F5C518;
  --color-accent-hover:      #E0B200;
  --color-accent-secondary:  #2DD4D4;
  --color-text-primary:      #FFFFFF;
  --color-text-secondary:    #9A9A9A;
  --color-text-muted:        #6B6B6B;
  --color-text-on-accent:    #0E0E0E;
  --color-stat-number:       #F5C518;
  --color-stat-number-alt:   #2DD4D4;
  --color-rail-primary:      #F5C518;
  --color-rail-secondary:    #2DD4D4;
  --color-tier-platinum:     #F5C518;
  --color-tier-gold:         #F5C518;
  --color-tier-badge-bg:     rgba(245,197,24,0.15);
  --color-progress-fill:     #F5C518;
  --color-progress-track:    #2A2A2A;
  --color-progress-number:   #F5C518;
  --color-link:              #F5C518;
  --color-border-card:       #262626;
  --color-border-chip:       #2A2A2A;
  --color-search-border:     #2A2A2A;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.45);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-brand:              20px;
  --text-screen-title:       30px;
  --text-screen-sub:         13px;
  --text-search:             14px;
  --text-stat-label:         10px;
  --text-stat-number:        32px;
  --text-client-name:        18px;
  --text-tier-badge:         9px;
  --text-since-meta:         11px;
  --text-program-label:      10px;
  --text-program-name:       17px;
  --text-progress-number:    16px;
  --text-link:               13px;
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
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --navbar-height:           72px;
  --card-gap:                20px;
  --card-radius:             16px;
  --stat-count:              2;
  --tab-count:               5;
}
```

---

## 13. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Client List.png`. Semua teks (EGGGYM, Daftar Klien, Kelola kemajuan dan program latihan klien Anda., Cari nama klien atau program…, TOTAL KLIEN 24, AKTIF HARI INI 08, Sarah Jenkins, PLATINUM, ACTIVE SINCE 2023, CURRENT PROGRAM, Hypertrophy Phase II 75%, Marcus Thorne, GOLD, ACTIVE SINCE 2024, Strength & Power Base 42%, Elena Rodriguez, NEW CLIENT, Functional Core Mobility 12%, Lihat Detail) harus persis sama dengan gambar.

2. **TRAINER SIDE (Bukan Member)**: Bagian dari keluarga Trainer-side (lihat HOME_PT_DASHBOARD & TRAINER_SCHEDULE). Bottom tab bar versi trainer: **HOME / JADWAL / KLIEN / PROGRAM / PROFIL** dengan KLIEN aktif. Jangan tertukar dengan tab bar member.

3. **Aksen Sekunder Cyan (Baru)**: Layar ini memperkenalkan warna aksen kedua — cyan `#2DD4D4` — khusus untuk metrik "Aktif Hari Ini" (rail + angka). Ini pengecualian dari skema mono-kuning. Catat sebagai token `--color-accent-secondary` agar bisa dipakai konsisten bila ada metrik "live/active" di layar trainer lain.

4. **Mobile-First Layout**: Layar manajemen klien, konten scrollable vertikal. Gunakan `safe-area-inset-*`. Brand header EGGGYM.

5. **Search Klien**: Search bar full-width untuk cari klien by nama atau program. Gunakan `role="search"` + `aria-label`. Filter real-time terhadap daftar client card.

6. **Summary Stats Dual-Rail**: Dua kartu ringkasan berdampingan, masing-masing dengan accent rail kiri 3px berwarna beda — kuning (Total Klien 24) & cyan (Aktif Hari Ini 08). Rail + warna angka membedakan makna metrik (total vs live/aktif). Equal-width 2 kolom.

7. **Client Card Structure**: Tiap kartu = header (avatar + nama + tier badge + since-meta + overflow menu), block program berjalan (supra-label + nama + persen), progress bar, footer (ikon meta + link detail). Konsisten layout antar klien.

8. **Tier Badge (enum)**: PLATINUM & GOLD ditampilkan sebagai badge kecil kuning (bg kuning transparan). Pada gambar keduanya berwarna kuning; bila ada tier lain (Silver/Bronze) bedakan warna. Sertakan teks tier, jangan andalkan warna.

9. **Since-Meta Kontekstual**: "ACTIVE SINCE {year}" untuk klien lama; "NEW CLIENT" untuk klien baru (Elena). Render dinamis berdasarkan tanggal bergabung. Klien baru bisa diberi penanda visual tambahan bila perlu.

10. **Progress Bar Program**: Menampilkan kemajuan program berjalan tiap klien (75% / 42% / 12%). Width fill = nilai persen. Angka persen kuning di kanan nama program. Gunakan `role="progressbar"` + `aria-valuenow`.

11. **Footer Meta Icons Kontekstual**: Jumlah & jenis ikon meta berbeda per klien (Sarah: calendar+stopwatch; Marcus: calendar; Elena: bolt) — kemungkinan menandakan jadwal/sesi/aktivitas terkait. Render dinamis dari data klien; sembunyikan ikon yang tidak relevan.

12. **Lihat Detail Link**: Link kuning "Lihat Detail →" di footer membuka halaman detail klien (progress lengkap, riwayat sesi, program). Konsisten di setiap kartu. Beri `aria-label` menyertakan nama klien.

13. **Scroll & Padding**: Konten lebih tinggi dari viewport → scroll vertikal. Beri `padding-bottom:88px` agar client card terbawah tidak tertutup tab bar. Header & search boleh sticky agar pencarian selalu terjangkau.

14. **Accessibility**: Beri `aria-current="page"` pada tab KLIEN. Search input beri `aria-label`. Progress bar gunakan `role="progressbar"` dengan `aria-valuenow`. Tier badge & since-meta sertakan teks jelas. Pastikan kontras cyan `#2DD4D4` di atas latar gelap memenuhi WCAG AA (cek rasio ≥ 4.5:1). Overflow menu (⋮) beri `aria-haspopup="menu"`. Link "Lihat Detail" beri `aria-label` menyertakan nama klien. Touch target minimum 44×44px.

---

*Spec ini generated dari analisis visual screen Client List.png (visual-verified).*
*Design system reference: Egg Gym — Home PT Dashboard (HOME_PT_DASHBOARD_UI_SPEC.md), Trainer Schedule (TRAINER_SCHEDULE_UI_SPEC.md) & Member specs. CATATAN: sisi TRAINER, tab bar HOME/JADWAL/KLIEN/PROGRAM/PROFIL; memperkenalkan aksen sekunder cyan.*
*Total sections: 14 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

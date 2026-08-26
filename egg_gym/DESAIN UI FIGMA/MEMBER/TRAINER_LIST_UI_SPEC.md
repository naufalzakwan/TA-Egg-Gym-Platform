# TRAINER_LIST_UI_SPEC.md
# Egg Gym App — Trainer List Screen (Find Your Expert Guide, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Member App > Trainer > Trainer List (Coach Directory)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Trainer List.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Trainer List mewarisi sistem warna identik dengan Program, Session Detail, Booking History, Profile & Rating: latar near-black dengan aksen kuning emas. Token tambahan ditambahkan untuk tier badge (PRO/ELITE/MASTER), search bar, filter chips, gradient overlay foto trainer, dan rating star inline.

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0E0E0E               | App background (screen utama)                  |
| --color-bg-card           | #1A1A1A               | Trainer card background                        |
| --color-bg-card-alt       | #161616               | Lower info area pada trainer card              |
| --color-bg-chip           | #1C1C1C               | Filter chip inactive & tag background          |
| --color-bg-search         | #1A1A1A               | Search bar background                          |
| --color-bg-navbar         | #121212               | Bottom tab bar background                      |
| --color-accent-primary    | #F5C518               | CTA, active chip, hero accent, tier badge      |
| --color-accent-hover      | #E0B200               | Button pressed state                           |
| --color-text-primary      | #FFFFFF               | Trainer name, headings, primary values         |
| --color-text-secondary    | #9A9A9A               | Labels, captions, meta text                    |
| --color-text-muted        | #6B6B6B               | Inactive tab, placeholder, description meta    |
| --color-text-on-accent    | #0E0E0E               | Text on yellow/accent (CTA, active chip, badge)|
| --color-title-white       | #FFFFFF               | "FIND YOUR" baris putih pada hero              |
| --color-title-accent      | #F5C518               | "EXPERT GUIDE" baris kuning pada hero          |
| --color-badge-pro         | #F5C518               | Badge "PRO" (kuning solid)                     |
| --color-badge-elite       | #F5C518               | Badge "ELITE" (kuning solid)                   |
| --color-badge-master      | #F5C518               | "MASTER COACH" supra-label (kuning)            |
| --color-rating-star       | #F5C518               | Bintang rating inline                          |
| --color-rating-text       | #F5C518               | Angka rating "4.9 (124)"                       |
| --color-stat-number       | #F5C518               | "4.95" rating stat (featured card)             |
| --color-stat-number-alt   | #FFFFFF               | "1.2k+" sessions stat                          |
| --color-overlay-img       | linear-gradient(180deg, transparent 35%, rgba(14,14,14,0.95) 100%) | Gradient overlay foto trainer |
| --color-border-card       | #262626               | Card & panel borders                           |
| --color-border-chip       | #2A2A2A               | Filter chip & tag border                       |
| --color-search-border     | #2A2A2A               | Search bar border                              |
| --color-tab-active        | #F5C518               | Active bottom-tab icon & label (TRAINER)       |
| --color-tab-inactive      | #6B6B6B               | Inactive bottom-tab icon & label               |
| --color-glow-cta          | rgba(245,197,24,0.45) | Glow di sekitar CTA kuning                     |
| --color-overlay-dark      | rgba(0,0,0,0.7)       | Modal backdrop                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (hero title & trainer name)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-screen-title      | 18px | 800    | 1.1    | 0px              | "Welcome, Athlete" header title    |
| --text-hero-title        | 32px | 900    | 1.05   | -0.5px           | "FIND YOUR EXPERT GUIDE" hero      |
| --text-hero-sub          | 13px | 600    | 1.4    | 1px (uppercase)  | "CURATED ELITE PERFORMANCE COACHES."|
| --text-search            | 14px | 400    | 1.3    | 0px              | Search input & placeholder         |
| --text-filter-chip       | 11px | 700    | 1.2    | 0.5px (uppercase)| "ALL TRAINERS" / "BODYBUILDING"    |
| --text-tier-badge        | 10px | 800    | 1.0    | 0.8px (uppercase)| "PRO" / "ELITE" badge              |
| --text-master-supra      | 11px | 700    | 1.2    | 1px (uppercase)  | "MASTER COACH" supra-label         |
| --text-trainer-name      | 24px | 800    | 1.15   | -0.3px           | "Marcus Thorne" trainer name       |
| --text-rating            | 14px | 700    | 1.2    | 0px              | "4.9 (124)" rating inline          |
| --text-tag               | 11px | 600    | 1.2    | 0.5px (uppercase)| "HYPERTROPHY" / "FAT LOSS" tag     |
| --text-description       | 13px | 400    | 1.5    | 0px              | Deskripsi bio Master Coach         |
| --text-stat-label        | 10px | 600    | 1.3    | 0.8px (uppercase)| "RATING" / "SESSIONS" label        |
| --text-stat-number       | 22px | 800    | 1.0    | -0.5px           | "4.95" / "1.2k+" stat number       |
| --text-cta               | 14px | 800    | 1.2    | 1px (uppercase)  | "LIHAT PROFIL" button              |
| --text-tab-label         | 10px | 600    | 1.2    | 0.5px (uppercase)| Bottom tab labels                  |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Badge padding, tiny gaps                         |
| --space-sm     | 8px   | Icon-text gap, tag gap                            |
| --space-md     | 12px  | Inter-element gap                                |
| --space-base   | 16px  | Screen horizontal padding, card inner padding    |
| --space-lg     | 20px  | Card-to-card vertical gap                        |
| --space-xl     | 24px  | Section separation                               |
| --space-2xl    | 32px  | Major block separation (hero ke search)          |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Tag, tier badge, CTA button                      |
| --radius-md    | 12px  | Search bar, filter chip                          |
| --radius-lg    | 16px  | Trainer cards                                    |
| --radius-pill  | 999px | Filter chip (pill), tier badge                   |
| --radius-full  | 50%   | Header avatar, notification button               |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 4px 16px rgba(0,0,0,0.5)            | Trainer cards default       |
| --shadow-cta     | 0 0 16px rgba(245,197,24,0.35)        | Glow CTA kuning             |
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
Card Gap:       20px (antar trainer card)
Card Image:     full-width × ~380px (foto trainer, gradient overlay di bawah)
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ (👤) Welcome, Athlete         [🔔]   │  ← Header
├──────────────────────────────────────┤
│ FIND YOUR                            │  ← Hero (putih)
│ EXPERT GUIDE                         │  ← Hero (kuning)
│ CURATED ELITE PERFORMANCE COACHES.   │  ← Hero subtitle
│ ┌──────────────────────────────────┐ │
│ │ 🔍 Search by name or specialty…   │ │  ← Search Bar
│ └──────────────────────────────────┘ │
│ [ALL TRAINERS][BODYBUILDING][YOGA EXP]│  ← Filter Chips
│ ┌──────────────────────────────────┐ │
│ │ [   foto trainer   ]      [PRO]  │ │  ← Trainer Card (standar)
│ │ Marcus Thorne                    │ │
│ │ ★ 4.9 (124)                      │ │
│ │ [HYPERTROPHY] [FAT LOSS]         │ │
│ │ [      LIHAT PROFIL        ]     │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [   foto trainer   ]    [ELITE]  │ │  ← Trainer Card (standar)
│ │ Elena Rodriguez                  │ │
│ │ ★ 5.0 (88)                       │ │
│ │ [YOGA] [MOBILITY]                │ │
│ │ [      LIHAT PROFIL        ]     │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [   foto trainer   ]             │ │  ← Trainer Card (FEATURED)
│ │ MASTER COACH                     │ │
│ │ Julian Vane                      │ │
│ │ Former Olympic conditioning...   │ │
│ │ RATING    SESSIONS               │ │
│ │ 4.95      1.2k+                  │ │
│ │ [      LIHAT PROFIL        ]     │ │
│ └──────────────────────────────────┘ │
├──────────────────────────────────────┤
│ 🏠     ⚡      👥      🖥️      👤    │  ← Bottom Tab Bar
│ HOME PROGRAM TRAINER MEMBERSHIP PROFIL│  ← TRAINER active
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
  Size:         36px × 36px, border-radius 50%
  Background:   #1C1C1C, object-fit cover

Title:
  Text:         "Welcome, Athlete"
  Font-size:    18px, weight 800, color #F5C518
```

### 5.3 Kanan — Notification Button
```
Size:           40px × 40px (icon-only, transparan/subtle bg)
Icon:           🔔 bell (outline), 20px, color #F5C518
Display:        flex center
```

---

## 6. KOMPONEN: HERO TITLE BLOCK

```
Padding:        0 16px
Margin:         8px 0 24px

Title (2 baris):
  Line 1:       "FIND YOUR"  → 32px, weight 900, color #FFFFFF, uppercase
  Line 2:       "EXPERT GUIDE" → 32px, weight 900, color #F5C518, uppercase
  Letter-spacing: -0.5px, line-height 1.05

Subtitle:
  Text:         "CURATED ELITE PERFORMANCE COACHES."
  Font-size:    13px, weight 600, uppercase, letter-spacing 1px, color #9A9A9A
  Margin-top:   8px  (wrap 2 baris)
```

---

## 7. KOMPONEN: SEARCH BAR

```
Background:     #1A1A1A
Border:         1px solid #2A2A2A
Border-radius:  12px
Padding:        14px 16px
Margin:         0 16px 16px
Display:        flex, align-items center, gap 12px

Icon:
  Icon:         🔍 magnifier, 18px, color #9A9A9A

Input/Placeholder:
  Text:         "Search by name or specialty…"
  Font-size:    14px, weight 400, color #6B6B6B (placeholder) / #FFFFFF (terisi)
```

---

## 8. KOMPONEN: FILTER CHIPS

### 8.1 Container
```
Display:        flex, gap 10px, overflow-x auto (scrollable horizontal)
Padding:        0 16px
Margin-bottom:  24px
```

### 8.2 Chip Active ("ALL TRAINERS")
```
Padding:        10px 16px
Background:     #F5C518
Border-radius:  999px
Color:          #0E0E0E
Font-size:      11px, weight 700, uppercase, letter-spacing 0.5px
```

### 8.3 Chip Inactive ("BODYBUILDING" / "YOGA EXPERT")
```
Padding:        10px 16px
Background:     #1C1C1C
Border:         1px solid #2A2A2A
Border-radius:  999px
Color:          #9A9A9A
Font-size:      11px, weight 700, uppercase, letter-spacing 0.5px
```

---

## 9. KOMPONEN: TRAINER CARD — VARIANT STANDARD

### 9.1 Container
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Margin:         0 16px 20px
Overflow:       hidden  (untuk crop foto)
Box-shadow:     0 4px 16px rgba(0,0,0,0.5)
```

### 9.2 Image Area (Foto Trainer)
```
Width:          100%
Height:         ~380px
Object-fit:     cover
Position:       relative
Overlay:        linear-gradient(180deg, transparent 35%, rgba(14,14,14,0.95) 100%)

Tier Badge (absolute, top-right, offset 12px):
  Padding:      6px 12px, border-radius 8px
  Background:   #F5C518
  Color:        #0E0E0E
  Font:         10px, weight 800, uppercase, letter-spacing 0.8px
  Variants:     "PRO" (Marcus) / "ELITE" (Elena)

Name + Rating Overlay (absolute, bottom-left, di atas gradient):
  Name:         "Marcus Thorne" → 24px, weight 800, color #FFFFFF
  Rating Row:   ★ (kuning, 14px) + "4.9 (124)" → 14px, weight 700, color #F5C518
                margin-top 4px
```

### 9.3 Info Area (di bawah foto)
```
Background:     #161616
Padding:        16px

Tags Row (flex, gap 8px, margin-bottom 14px):
  Tag:          bg #1C1C1C, border 1px solid #2A2A2A, border-radius 8px, padding 6px 12px
  Font:         11px, weight 600, uppercase, letter-spacing 0.5px, color #9A9A9A
  Tags:  (Marcus) HYPERTROPHY • FAT LOSS
         (Elena)  YOGA • MOBILITY

CTA Button — LIHAT PROFIL:
  Width:        100%
  Background:   #F5C518
  Border-radius:8px
  Padding:      16px 0
  Color:        #0E0E0E
  Font:         14px, weight 800, uppercase, letter-spacing 1px
  Text-align:   center
  Box-shadow:   0 0 16px rgba(245,197,24,0.35)  (glow subtle)
```

---

## 10. KOMPONEN: TRAINER CARD — VARIANT FEATURED (MASTER COACH)

### 10.1 Container
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Margin:         0 16px 20px
Overflow:       hidden
```

### 10.2 Image Area
```
Width:          100%
Height:         ~330px
Object-fit:     cover
Overlay:        linear-gradient(180deg, transparent 30%, rgba(14,14,14,0.95) 100%)
(Tanpa tier badge di pojok; tier ditandai via supra-label "MASTER COACH" di info area)
```

### 10.3 Info Area
```
Background:     #161616
Padding:        20px 16px 16px

Supra-label:
  Text:         "MASTER COACH" → 11px, weight 700, uppercase, letter-spacing 1px, color #F5C518

Name:
  Text:         "Julian Vane" → 24px, weight 800, color #FFFFFF, margin-top 6px

Description:
  Text:         "Former Olympic conditioning coach with 15+ years experience
                 in high-performance metabolic training."
  Font-size:    13px, weight 400, color #9A9A9A, line-height 1.5, margin-top 8px

Stats Row (flex, gap 40px, margin-top 16px):
  Stat block (label di atas, number di bawah):
    Label:      10px, weight 600, uppercase, letter-spacing 0.8px, color #9A9A9A
    Number:     22px, weight 800
  Stat 1:  "RATING"   / "4.95"  (number kuning #F5C518)
  Stat 2:  "SESSIONS" / "1.2k+" (number putih #FFFFFF)

CTA Button — LIHAT PROFIL:
  (Identik dengan 9.3 — full-width kuning, padding 16px, glow)
  Margin-top:   16px
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

### 11.3 Tab Item (Active — TRAINER)
```
Icon:           22px, color #F5C518
Label-color:    #F5C518
Indicator:      highlight pill bg di belakang ikon TRAINER
                (bg rgba(245,197,24,0.12), border-radius 12px)
```

### 11.4 Daftar Tabs (5 item — sesuai gambar)
```
1. 🏠  HOME
2. ⚡  PROGRAM
3. 👥  TRAINER     ← ACTIVE (kuning)
4. 🖥️  MEMBERSHIP
5. 👤  PROFIL
```

---

## 12. GRID RECAP — RINGKASAN ZONA LAYOUT (Mobile)

| Zone                    | X Offset | Y Offset  | Width            | Height    |
|-------------------------|----------|-----------|------------------|-----------|
| Header                  | 0        | safe-top  | 100%             | ~64px     |
| Hero Title Block        | 16px     | ~116px    | calc(100% - 32px)| ~120px    |
| Search Bar              | 16px     | ~252px    | calc(100% - 32px)| ~52px     |
| Filter Chips            | 16px     | ~320px    | calc(100% - 32px)| ~40px     |
| Trainer Card (PRO)      | 16px     | ~376px    | calc(100% - 32px)| ~560px    |
| Trainer Card (ELITE)    | 16px     | ~956px    | calc(100% - 32px)| ~540px    |
| Trainer Card (FEATURED) | 16px     | ~1516px   | calc(100% - 32px)| ~580px    |
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px      |

*Catatan: konten jauh melebihi tinggi viewport (932px) → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 13. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Trainer List Screen (Find Your Expert Guide, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Trainer List.png
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
  --color-text-primary:      #FFFFFF;
  --color-text-secondary:    #9A9A9A;
  --color-text-muted:        #6B6B6B;
  --color-text-on-accent:    #0E0E0E;
  --color-title-white:       #FFFFFF;
  --color-title-accent:      #F5C518;
  --color-badge-pro:         #F5C518;
  --color-badge-elite:       #F5C518;
  --color-badge-master:      #F5C518;
  --color-rating-star:       #F5C518;
  --color-rating-text:       #F5C518;
  --color-stat-number:       #F5C518;
  --color-stat-number-alt:   #FFFFFF;
  --color-border-card:       #262626;
  --color-border-chip:       #2A2A2A;
  --color-search-border:     #2A2A2A;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.45);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-screen-title:       18px;
  --text-hero-title:         32px;
  --text-hero-sub:           13px;
  --text-search:             14px;
  --text-filter-chip:        11px;
  --text-tier-badge:         10px;
  --text-master-supra:       11px;
  --text-trainer-name:       24px;
  --text-rating:             14px;
  --text-tag:                11px;
  --text-description:        13px;
  --text-stat-label:         10px;
  --text-stat-number:        22px;
  --text-cta:                14px;
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
  --shadow-card:             0 4px 16px rgba(0,0,0,0.5);
  --shadow-cta:              0 0 16px rgba(245,197,24,0.35);
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --navbar-height:           72px;
  --card-gap:                20px;
  --card-radius:             16px;
  --card-image-height:       380px;
  --tab-count:               5;
}
```

---

## 14. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Trainer List.png`. Semua teks (Welcome Athlete, FIND YOUR EXPERT GUIDE, CURATED ELITE PERFORMANCE COACHES., Search by name or specialty…, ALL TRAINERS/BODYBUILDING/YOGA EXPERT, Marcus Thorne, 4.9 (124), HYPERTROPHY/FAT LOSS, Elena Rodriguez, 5.0 (88), YOGA/MOBILITY, MASTER COACH, Julian Vane, deskripsi bio, RATING 4.95, SESSIONS 1.2k+, LIHAT PROFIL, PRO/ELITE) harus persis sama dengan gambar.

2. **Mobile-First Layout**: Direktori coach diakses dari tab TRAINER (aktif/kuning). List trainer scrollable vertikal. Gunakan `safe-area-inset-*`.

3. **Hero Title Dua Warna**: "FIND YOUR" putih + "EXPERT GUIDE" kuning, weight 900 uppercase — focal point teratas. Konsisten dengan hero dua-warna di Rating & Review.

4. **Search + Filter Pattern**: Search bar full-width (cari by name/specialty) + baris filter chips horizontal-scrollable. Chip aktif "ALL TRAINERS" (kuning solid), lainnya outline. Filter mengubah daftar trainer. Gunakan `role="search"` & `aria-pressed` pada chip.

5. **Trainer Card Image-Dominant**: Berbeda dari booking card, foto trainer mendominasi (~380px) dengan gradient overlay kuat di bawah agar nama + rating overlay terbaca. Wajib `overflow:hidden` untuk crop foto mengikuti radius.

6. **Tier Badge (enum)**: PRO & ELITE = badge kuning solid di pojok kanan atas foto. MASTER COACH = supra-label kuning di info area (bukan badge pojok) — menandai tier tertinggi/featured. Render badge berdasarkan enum tier trainer.

7. **Dua Varian Card**: STANDARD (Marcus, Elena) → nama+rating overlay di foto, tag spesialisasi, CTA. FEATURED/MASTER (Julian) → info area lebih kaya: supra-label, nama, deskripsi bio, stat RATING/SESSIONS, CTA. Render kondisional berdasarkan tier/featured flag.

8. **Rating Treatment Berbeda**: Card standard menampilkan rating inline "★ 4.9 (124)" (bintang + jumlah review) di overlay foto. Card featured menampilkan rating sebagai stat block "4.95" + "SESSIONS 1.2k+". Konsisten dalam warna kuning untuk angka rating.

9. **Gradient Overlay Foto**: Foto trainer diberi gradient gelap di bawah (`transparent → rgba(14,14,14,0.95)`) untuk transisi mulus ke info area & keterbacaan teks overlay. Tinggi gradient ~50-65% bagian bawah foto.

10. **Tags Spesialisasi**: Chip tag kecil (HYPERTROPHY, FAT LOSS, YOGA, MOBILITY) menandai keahlian trainer. Bisa lebih dari satu; wrap bila perlu. Konsisten styling dengan chip di layar lain.

11. **CTA LIHAT PROFIL**: Tombol full-width kuning solid di setiap card, membuka halaman detail/profil trainer. Punya glow subtle. Aksi konsisten antar varian card.

12. **Stat Block Hierarki Warna (Featured)**: "4.95" (rating) kuning — metrik kualitas brand-positive; "1.2k+" (sessions) putih — metrik volume netral. Bedakan warna untuk hierarki.

13. **Scroll & Padding**: Konten jauh lebih panjang dari viewport (kartu besar). Beri `padding-bottom:88px` agar card terbawah tidak tertutup tab bar. Header/search boleh sticky agar pencarian selalu terjangkau.

14. **Accessibility**: Beri `aria-current="page"` pada tab TRAINER. Search input beri `aria-label`. Filter chips gunakan `aria-pressed`/`role="button"`. Rating sertakan teks (4.9, 124 reviews), jangan andalkan ikon bintang saja. Tier badge sertakan teks (PRO/ELITE/MASTER COACH). CTA "LIHAT PROFIL" beri `aria-label` menyertakan nama trainer (mis. "Lihat profil Marcus Thorne"). Kontras teks gelap pada tombol kuning penuhi WCAG AA. Touch target minimum 44×44px.

---

*Spec ini generated dari analisis visual screen Trainer List.png (visual-verified).*
*Design system reference: Egg Gym — Program (PROGRAM_TAB_UI_SPEC.md), Session Detail PT/Self, Booking History, Profile Member & Rating & Review (RATING_REVIEW_UI_SPEC.md).*
*Total sections: 14 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

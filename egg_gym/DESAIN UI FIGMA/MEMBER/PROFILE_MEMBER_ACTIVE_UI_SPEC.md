# PROFILE_MEMBER_ACTIVE_UI_SPEC.md
# Egg Gym App — Profile Member Screen (Active Membership, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Member App > Profil (Profil Saya — Active Member)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Profile Member (Active).png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Profil mewarisi sistem warna identik dengan Program, Session Detail & Booking History: latar near-black dengan aksen kuning emas. Token tambahan ditambahkan untuk avatar ring, membership badge, target card kuning solid, accordion info card, dan tombol logout (merah).

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0E0E0E               | App background (screen utama)                  |
| --color-bg-card           | #1A1A1A               | Info accordion card background                 |
| --color-bg-card-alt       | #161616               | Card inner / row alt background                |
| --color-bg-chip           | #1C1C1C               | Membership badge & icon thumb background       |
| --color-bg-navbar         | #121212               | Bottom tab bar background                      |
| --color-accent-primary    | #F5C518               | CTA, target card, avatar ring, brand text      |
| --color-accent-hover      | #E0B200               | Pressed state                                  |
| --color-text-primary      | #FFFFFF               | Name, headings, primary values                 |
| --color-text-secondary    | #9A9A9A               | Labels, captions, meta text                    |
| --color-text-muted        | #6B6B6B               | Inactive tab, app version, placeholder         |
| --color-text-on-accent    | #0E0E0E               | Text on yellow/accent elements (target card)   |
| --color-stat-number       | #F5C518               | "24" sesi latihan bulan ini (kuning)           |
| --color-stat-number-alt   | #FFFFFF               | "78.5" berat badan (putih)                     |
| --color-target-bg         | #F5C518               | Target card background (kuning solid)          |
| --color-target-text       | #0E0E0E               | Teks pada target card                          |
| --color-badge-member      | #F5C518               | "ELITE GOLD MEMBER" badge text                 |
| --color-badge-member-bg   | #1C1C1C               | Membership badge background                    |
| --color-logout            | #E0524D               | "Keluar dari Akun" text & icon (merah)         |
| --color-logout-border     | rgba(224,82,77,0.40)  | Border tombol logout                           |
| --color-avatar-ring       | #F5C518               | Ring melingkar di sekitar avatar               |
| --color-border-card       | #262626               | Card & panel borders                           |
| --color-border-chip       | #2A2A2A               | Badge & outline border                         |
| --color-divider           | #222222               | Divider antar baris data dalam accordion       |
| --color-tab-active        | #F5C518               | Active bottom-tab icon & label (PROFIL)        |
| --color-tab-inactive      | #6B6B6B               | Inactive bottom-tab icon & label               |
| --color-glow-cta          | rgba(245,197,24,0.45) | Glow di sekitar elemen kuning                  |
| --color-overlay-dark      | rgba(0,0,0,0.7)       | Modal backdrop                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (name & big stat)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-screen-title      | 20px | 800    | 1.1    | 0px              | "Profil Saya" header title         |
| --text-user-name         | 26px | 800    | 1.15   | -0.3px           | "Marcus Holloway" user name        |
| --text-user-email        | 14px | 400    | 1.4    | 0px              | "marcus.h@eliteathletics.com"      |
| --text-member-badge      | 12px | 700    | 1.0    | 0.8px (uppercase)| "ELITE GOLD MEMBER" badge          |
| --text-stat-label        | 10px | 600    | 1.3    | 0.8px (uppercase)| "LATIHAN BULAN INI" / "BERAT BADAN"|
| --text-stat-number       | 40px | 800    | 1.0    | -1px             | "24" big stat number               |
| --text-stat-unit         | 14px | 600    | 1.2    | 0px              | "Sesi" / "kg" unit                 |
| --text-stat-number-md    | 28px | 800    | 1.0    | -0.5px           | "78.5" berat badan number          |
| --text-target-label      | 10px | 600    | 1.3    | 1px (uppercase)  | "TARGET" supra-label di target card|
| --text-target-value      | 26px | 800    | 1.1    | -0.5px           | "Build Muscle" target value        |
| --text-section-title     | 18px | 800    | 1.2    | 0px              | "Informasi Akun" section title     |
| --text-link              | 12px | 700    | 1.0    | 0.5px (uppercase)| "EDIT SEMUA" link                  |
| --text-accordion-supra   | 10px | 600    | 1.3    | 1px (uppercase)  | "DATA PRIBADI" / "DATA KEBUGARAN"  |
| --text-accordion-title   | 16px | 700    | 1.3    | 0px              | "Informasi Identitas" / "Statistik & Target" |
| --text-data-label        | 14px | 400    | 1.4    | 0px              | "Nama Lengkap" / "Tinggi Badan"    |
| --text-data-value        | 14px | 700    | 1.4    | 0px              | "Marcus Holloway" / "182 cm"       |
| --text-logout            | 15px | 700    | 1.2    | 0.3px            | "Keluar dari Akun" button          |
| --text-version           | 11px | 500    | 1.3    | 1px (uppercase)  | "ELITE ATHLETICS V2.4.0"           |
| --text-tab-label         | 10px | 600    | 1.2    | 0.5px (uppercase)| Bottom tab labels                  |

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
| --space-2xl    | 32px  | Major block separation (avatar block)            |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Logout button, small elements                    |
| --radius-md    | 12px  | Icon thumbnail accordion, edit badge             |
| --radius-lg    | 16px  | Info cards, target card                          |
| --radius-pill  | 999px | Membership badge                                 |
| --radius-full  | 50%   | Avatar, avatar ring, notification & header avatar|

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards default               |
| --shadow-target  | 0 4px 20px rgba(245,197,24,0.35)      | Glow target card kuning     |
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
Card Gap:       20px (antar info card) / 24px (antar section)
Avatar:         120px diameter, centered, ring kuning + edit badge
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ Profil Saya              [🔔] [👤]   │  ← Header
├──────────────────────────────────────┤
│              ╭───────╮               │
│              │ AVATAR │(✎)           │  ← Avatar + ring + edit badge
│              ╰───────╯               │
│           Marcus Holloway            │  ← Name (centered)
│      marcus.h@eliteathletics.com     │  ← Email
│        [ ELITE GOLD MEMBER ]         │  ← Membership Badge
│ LATIHAN BULAN INI    BERAT BADAN     │
│ 24 Sesi              78.5 kg         │  ← Quick Stats (2)
│              ┌─────────────────────┐ │
│              │ TARGET              │ │  ← Target Card (kuning solid)
│              │ Build Muscle        │ │
│              └─────────────────────┘ │
│ Informasi Akun          EDIT SEMUA   │  ← Section header + link
│ ┌──────────────────────────────────┐ │
│ │ [👤] DATA PRIBADI             >  │ │  ← Accordion 1 header
│ │      Informasi Identitas         │ │
│ │ Nama Lengkap      Marcus Holloway│ │
│ │ Tanggal Lahir     12 Mei 1994    │ │
│ │ Jenis Kelamin     Laki-laki      │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ [⚡] DATA KEBUGARAN           >  │ │  ← Accordion 2 header
│ │      Statistik & Target          │ │
│ │ Tinggi Badan      182 cm         │ │
│ │ Berat Badan       78.5 kg        │ │
│ │ Target Utama      Hipertrofi     │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │  [→ Keluar dari Akun]            │ │  ← Logout Button (outline merah)
│ └──────────────────────────────────┘ │
│       ELITE ATHLETICS V2.4.0         │  ← App Version
├──────────────────────────────────────┤
│ 🏠     ⚡      👥      🖥️      👤    │  ← Bottom Tab Bar
│ HOME PROGRAM TRAINER MEMBERSHIP PROFIL│  ← PROFIL active
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

### 5.2 Kiri — Title
```
Text:           "Profil Saya"
Font-size:      20px, weight 800, color #F5C518
```

### 5.3 Kanan — Action Group
```
Display:        flex, align-items center, gap 12px

Notification Button:
  Size:         40px × 40px, icon-only
  Icon:         🔔 bell (outline), 20px, color #F5C518

Header Avatar (mini):
  Size:         36px × 36px, border-radius 50%
  Background:   #1C1C1C
  Object-fit:   cover
```

---

## 6. KOMPONEN: IDENTITY BLOCK (Avatar + Name)

### 6.1 Container
```
Display:        flex, flex-direction column, align-items center
Padding:        16px 16px 0
Margin-bottom:  24px
```

### 6.2 Avatar + Ring + Edit Badge
```
Avatar:
  Size:         120px × 120px
  Border-radius:50%
  Object-fit:   cover

Ring:
  Border:       3px solid #F5C518  (ring kuning melingkar, ada gap kecil ke avatar)
  Padding:      4px  (gap antara ring dan foto)

Edit Badge (absolute, bottom-right avatar):
  Size:         28px × 28px, border-radius 50%
  Background:   #F5C518
  Icon:         ✎ pencil, 14px, color #0E0E0E
  Border:       2px solid #0E0E0E  (cutout dari background)
```

### 6.3 Name + Email
```
Name:
  Text:         "Marcus Holloway"
  Font-size:    26px, weight 800, color #FFFFFF, margin-top 16px

Email:
  Text:         "marcus.h@eliteathletics.com"
  Font-size:    14px, weight 400, color #9A9A9A, margin-top 4px
```

### 6.4 Membership Badge
```
Text:           "ELITE GOLD MEMBER"
Background:     #1C1C1C
Border:         1px solid #2A2A2A  (boleh subtle kuning)
Border-radius:  999px
Padding:        8px 18px
Font-size:      12px, weight 700, uppercase, letter-spacing 0.8px
Color:          #F5C518
Margin-top:     14px
```

---

## 7. KOMPONEN: QUICK STATS + TARGET CARD

### 7.1 Layout Container
```
Display:        flex, justify-content space-between, align-items flex-start
Padding:        0 16px
Margin-bottom:  24px
```

### 7.2 Stats Group (kiri)
```
Display:        flex, gap 32px (atau stack 2 baris sesuai gambar)

Stat 1 — Latihan Bulan Ini:
  Label:        "LATIHAN BULAN INI" → 10px, weight 600, uppercase, color #9A9A9A
  Number:       "24" → 40px, weight 800, color #F5C518
  Unit:         "Sesi" → 14px, weight 600, color #9A9A9A, margin-left 4px

Stat 2 — Berat Badan:
  Label:        "BERAT BADAN" → 10px, weight 600, uppercase, color #9A9A9A
  Number:       "78.5" → 28px, weight 800, color #FFFFFF
  Unit:         "kg" → 14px, weight 600, color #9A9A9A, margin-left 4px
```

### 7.3 Target Card (kanan)
```
Background:     #F5C518  (kuning solid)
Border-radius:  16px
Padding:        18px 20px
Width:          ~50% (kanan)
Box-shadow:     0 4px 20px rgba(245,197,24,0.35)  (glow)

Supra-label:
  Text:         "TARGET" → 10px, weight 600, uppercase, letter-spacing 1px, color #0E0E0E (opacity 0.7)

Value:
  Text:         "Build Muscle"  (wrap 2 baris)
  Font-size:    26px, weight 800, color #0E0E0E, letter-spacing -0.5px, margin-top 6px
```

---

## 8. KOMPONEN: INFORMASI AKUN — SECTION HEADER

```
Display:        flex, justify-content space-between, align-items center
Padding:        0 16px
Margin-bottom:  16px

Judul:
  Text:         "Informasi Akun"  → 18px, weight 800, #FFFFFF

Link:
  Text:         "EDIT SEMUA"
  Font-size:    12px, weight 700, uppercase, letter-spacing 0.5px
  Color:        #F5C518
```

---

## 9. KOMPONEN: INFO ACCORDION CARD

### 9.1 Container
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Padding:        16px
Margin:         0 16px 20px
```

### 9.2 Accordion Header Row
```
Display:        flex, align-items center, gap 12px

Icon Thumbnail:
  Size:         44px × 44px, border-radius 12px
  Background:   #1C1C1C
  Icon:         20px, color #F5C518
                - Data Pribadi → 👤 person
                - Data Kebugaran → ⚡ dumbbell/bolt

Text block (flex 1):
  Supra:        "DATA PRIBADI" / "DATA KEBUGARAN" → 10px, weight 600, uppercase, letter-spacing 1px, color #9A9A9A
  Title:        "Informasi Identitas" / "Statistik & Target" → 16px, weight 700, color #FFFFFF

Chevron:
  Icon:         > chevron-right, 18px, color #6B6B6B  (indikator expand/navigasi)
```

### 9.3 Data Rows (di bawah header)
```
Divider:        border-top 1px solid #222222, margin 14px 0 (memisahkan header & rows)

Data Row:
  Display:      flex, justify-content space-between, align-items center
  Padding:      10px 0
  Label:        14px, weight 400, color #9A9A9A  (kiri)
  Value:        14px, weight 700, color #FFFFFF  (kanan)

  Accordion 1 (DATA PRIBADI):
    Nama Lengkap   → Marcus Holloway
    Tanggal Lahir  → 12 Mei 1994
    Jenis Kelamin  → Laki-laki

  Accordion 2 (DATA KEBUGARAN):
    Tinggi Badan   → 182 cm
    Berat Badan    → 78.5 kg
    Target Utama   → Hipertrofi
```

---

## 10. KOMPONEN: LOGOUT BUTTON

```
Display:        flex, align-items center, justify-content center, gap 10px
Background:     transparan
Border:         1px solid rgba(224,82,77,0.40)
Border-radius:  8px
Padding:        16px
Margin:         8px 16px 0

Icon:
  Icon:         → log-out/exit, 18px, color #E0524D

Text:
  Text:         "Keluar dari Akun"
  Font-size:    15px, weight 700, color #E0524D, letter-spacing 0.3px
```

---

## 11. KOMPONEN: APP VERSION

```
Text:           "ELITE ATHLETICS V2.4.0"
Font-size:      11px, weight 500, uppercase, letter-spacing 1px
Color:          #6B6B6B
Text-align:     center
Margin:         16px 0 24px
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

### 12.3 Tab Item (Active — PROFIL)
```
Icon:           22px, color #F5C518
Label-color:    #F5C518
Indicator:      highlight pill bg di belakang ikon PROFIL
                (bg rgba(245,197,24,0.12), border-radius 12px)
```

### 12.4 Daftar Tabs (5 item — sesuai gambar)
```
1. 🏠  HOME
2. ⚡  PROGRAM
3. 👥  TRAINER
4. 🖥️  MEMBERSHIP
5. 👤  PROFIL       ← ACTIVE (kuning)
```

---

## 13. GRID RECAP — RINGKASAN ZONA LAYOUT (Mobile)

| Zone                    | X Offset | Y Offset  | Width            | Height    |
|-------------------------|----------|-----------|------------------|-----------|
| Header                  | 0        | safe-top  | 100%             | ~64px     |
| Identity Block          | 16px     | ~116px    | calc(100% - 32px)| ~280px    |
| Quick Stats + Target    | 16px     | ~412px    | calc(100% - 32px)| ~140px    |
| Informasi Akun Header   | 16px     | ~568px    | calc(100% - 32px)| ~30px     |
| Info Card (DATA PRIBADI)| 16px     | ~614px    | calc(100% - 32px)| ~210px    |
| Info Card (KEBUGARAN)   | 16px     | ~844px    | calc(100% - 32px)| ~210px    |
| Logout Button           | 16px     | ~1090px   | calc(100% - 32px)| ~56px     |
| App Version             | 16px     | ~1170px   | calc(100% - 32px)| ~24px     |
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px      |

*Catatan: konten melebihi tinggi viewport (932px) → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 14. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Profile Member Screen (Active Membership, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Profile Member (Active).png
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
  --color-stat-number-alt:   #FFFFFF;
  --color-target-bg:         #F5C518;
  --color-target-text:       #0E0E0E;
  --color-badge-member:      #F5C518;
  --color-badge-member-bg:   #1C1C1C;
  --color-logout:            #E0524D;
  --color-logout-border:     rgba(224,82,77,0.40);
  --color-avatar-ring:       #F5C518;
  --color-border-card:       #262626;
  --color-border-chip:       #2A2A2A;
  --color-divider:           #222222;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.45);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-screen-title:       20px;
  --text-user-name:          26px;
  --text-user-email:         14px;
  --text-member-badge:       12px;
  --text-stat-label:         10px;
  --text-stat-number:        40px;
  --text-stat-unit:          14px;
  --text-stat-number-md:     28px;
  --text-target-label:       10px;
  --text-target-value:       26px;
  --text-section-title:      18px;
  --text-link:               12px;
  --text-accordion-supra:    10px;
  --text-accordion-title:    16px;
  --text-data-label:         14px;
  --text-data-value:         14px;
  --text-logout:             15px;
  --text-version:            11px;
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
  --shadow-target:           0 4px 20px rgba(245,197,24,0.35);
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --navbar-height:           72px;
  --card-gap:                20px;
  --card-radius:             16px;
  --avatar-size:             120px;
  --tab-count:               5;
}
```

---

## 15. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Profile Member (Active).png`. Semua teks (Profil Saya, Marcus Holloway, marcus.h@eliteathletics.com, ELITE GOLD MEMBER, LATIHAN BULAN INI, 24 Sesi, BERAT BADAN, 78.5 kg, TARGET, Build Muscle, Informasi Akun, EDIT SEMUA, DATA PRIBADI, Informasi Identitas, Nama Lengkap/Tanggal Lahir/Jenis Kelamin beserta nilainya, DATA KEBUGARAN, Statistik & Target, Tinggi/Berat Badan/Target Utama, Keluar dari Akun, ELITE ATHLETICS V2.4.0) harus persis sama dengan gambar.

2. **Mobile-First Layout**: Layar member-facing, diakses dari bottom tab "PROFIL" (kini aktif/kuning — berbeda dari layar lain yang PROGRAM aktif). Gunakan `safe-area-inset-*`.

3. **Active Membership State**: Ini varian "Active" — badge "ELITE GOLD MEMBER" tampil aktif (kuning), data lengkap terisi, target tampil. Siapkan varian lain (inactive/expired) yang akan mengubah warna badge & CTA. Status keanggotaan jadi pembeda utama antar varian profil.

4. **Identity Block Terpusat**: Avatar 120px center dengan ring kuning 3px + edit badge floating di bottom-right. Nama, email, dan membership badge di-stack center di bawahnya. Edit badge memicu flow ubah foto/profil.

5. **Avatar Ring Treatment**: Ring kuning melingkari avatar dengan gap kecil (padding 4px). Implementasi bisa via `border` pada wrapper atau `box-shadow` ring. Edit badge diberi border `#0E0E0E` agar tampak "cutout" dari ring.

6. **Quick Stats Hierarki Warna**: "24" (latihan bulan ini) kuning `40px` — metrik aktivitas utama; "78.5" (berat badan) putih `28px` — metrik netral. Bedakan warna untuk menandai metrik brand-positive vs informatif.

7. **Target Card (Kuning Solid)**: Kartu kuning solid dengan teks gelap (`#0E0E0E`) — satu-satunya elemen inverse di layar ini, jadi focal point. Supra-label "TARGET" + value "Build Muscle". Punya glow shadow. Tappable untuk ubah target.

8. **Informasi Akun Accordion**: Dua kartu expandable — "Data Pribadi / Informasi Identitas" & "Data Kebugaran / Statistik & Target". Pada gambar keduanya dalam state expanded (data rows terlihat). Chevron `>` menandai bisa di-expand/navigasi ke detail. Gunakan `aria-expanded`.

9. **Accordion Header Pattern**: Setiap kartu punya icon thumbnail 44px + supra-label + title + chevron. Icon membedakan kategori (person vs dumbbell/bolt). Konsisten dengan icon-thumbnail pattern di Latihan Mandiri (Program Tab).

10. **Data Rows Layout**: Baris label-kiri/value-kanan dengan label abu `400` dan value putih `700`. Dipisah divider tipis dari header. "EDIT SEMUA" di section header membuka edit seluruh field sekaligus; tiap accordion bisa edit per-kategori.

11. **Logout Button (Destructive)**: Tombol outline merah (`#E0524D`) dengan border transparan-merah — gaya destructive/secondary, bukan solid. Idealnya memicu konfirmasi sebelum logout. Beri `aria-haspopup="dialog"`.

12. **App Version Footer**: Teks versi "ELITE ATHLETICS V2.4.0" abu muted, center, di bawah logout. Bersifat informatif (non-interaktif). Gunakan nilai versi dinamis dari build config saat implementasi.

13. **Scroll & Padding**: Konten lebih tinggi dari viewport → scroll vertikal. Beri `padding-bottom:88px` agar app version & logout tidak tertutup tab bar. Header boleh sticky agar judul selalu terlihat.

14. **Accessibility**: Beri `aria-current="page"` pada tab PROFIL. Accordion gunakan `aria-expanded`/`aria-controls`. Edit badge, notification, EDIT SEMUA, logout beri `aria-label` jelas. Logout (destructive) gunakan konfirmasi & jangan andalkan warna saja — sertakan ikon + teks. Target card pastikan kontras teks gelap di atas kuning memenuhi WCAG AA. Touch target minimum 44×44px.

---

*Spec ini generated dari analisis visual screen Profile Member (Active).png (visual-verified).*
*Design system reference: Egg Gym — Program (PROGRAM_TAB_UI_SPEC.md), Session Detail PT/Self & Booking History (BOOKING_HISTORY_UI_SPEC.md).*
*Total sections: 15 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*
    
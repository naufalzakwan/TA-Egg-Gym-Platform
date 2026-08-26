# TRAINER_PROFILE_DASHBOARD_UI_SPEC.md
# Egg Gym App — Trainer Profile Screen (Profil Trainer, Pro Trainer Side, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Trainer App > Profil (Trainer Profile Dashboard & Account)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Trainer Profile Dashboard.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Profil Trainer (Pro Trainer) memakai sistem warna identik dengan Home PT Dashboard, Jadwal Sesi, Buat Program, Buat Sesi, Program Progress & Live Session: latar near-black dengan aksen kuning emas. Token tambahan ditambahkan untuk hero avatar + edit fab, stat card (rating/klien), capacity bar, chip spesialisasi, bio block, jadwal aktif (day dots), menu row, dan logout destructive.

| Token Name                  | HEX Value             | Usage                                            |
|-----------------------------|-----------------------|--------------------------------------------------|
| --color-bg-primary          | #0E0E0E               | App background (screen utama)                    |
| --color-bg-card             | #1A1A1A               | Stat card, spesialisasi, bio, jadwal, menu card   |
| --color-bg-card-alt         | #161616               | Inner / nested block background                   |
| --color-bg-chip             | #1C1C1C               | Chip spesialisasi background                      |
| --color-bg-fab              | #F5C518               | Background edit FAB pada avatar                   |
| --color-bg-navbar           | #121212               | Bottom tab bar background                         |
| --color-accent-primary      | #F5C518               | Brand, rating, chip text, accent, tab active      |
| --color-accent-hover        | #E0B200               | Button pressed state                              |
| --color-text-primary        | #FFFFFF               | Name, stat value, headings                        |
| --color-text-secondary      | #9A9A9A               | Email, bio text, sub-meta                         |
| --color-text-muted          | #6B6B6B               | Labels, captions, idle day, inactive tab          |
| --color-text-on-accent      | #0E0E0E               | Text/icon on yellow (edit fab, tab active)        |
| --color-brand               | #F5C518               | "EGGGYM" brand text                               |
| --color-avatar-ring         | #F5C518               | Ring lingkaran hero avatar                        |
| --color-edit-fab-icon       | #0E0E0E               | Ikon pensil pada edit FAB                         |
| --color-rating-star         | #F5C518               | Ikon bintang rating                               |
| --color-rating-value        | #F5C518               | Nilai "4.9" rating                                |
| --color-stat-icon-klien     | #F5C518               | Ikon klien (people) pada stat card                |
| --color-stat-value          | #FFFFFF               | Nilai stat "24" klien                             |
| --color-stat-total          | #6B6B6B               | "/30" kapasitas total klien                       |
| --color-capacity-track      | #2A2A2A               | Track progress bar kapasitas klien                |
| --color-capacity-fill       | #F5C518               | Fill progress bar kapasitas (24/30)               |
| --color-chip-text           | #F5C518               | Teks chip spesialisasi                            |
| --color-chip-border         | #2A2A2A               | Border chip spesialisasi                          |
| --color-day-active          | #F5C518               | Dot hari kerja aktif (SEN-JUM)                    |
| --color-day-idle            | #3A3A3A               | Dot hari libur (SAB-MIN)                          |
| --color-day-label           | #9A9A9A               | Label hari (SEN/SEL/...)                          |
| --color-edit-link           | #F5C518               | Link "Ubah" pada jadwal aktif                     |
| --color-menu-icon           | #FFFFFF               | Ikon menu (gear) Pengaturan Akun                  |
| --color-menu-chevron        | #6B6B6B               | Chevron > pada menu row                           |
| --color-logout-text         | #E0524D               | Teks & ikon "Logout" (destructive)               |
| --color-logout-border       | rgba(224,82,77,0.3)   | Border kartu Logout                              |
| --color-border-card         | #262626               | Card & panel borders                              |
| --color-tab-active          | #F5C518               | Active bottom-tab icon & label (PROFIL)          |
| --color-tab-inactive        | #6B6B6B               | Inactive bottom-tab icon & label                  |
| --color-overlay-dark        | rgba(0,0,0,0.7)       | Modal backdrop (edit profil / konfirmasi logout)  |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (brand & name)
```

### Skala Tipografi Lengkap
| Token                   | Size | Weight | Line-H | Letter-Sp         | Usage                                  |
|-------------------------|------|--------|--------|-------------------|----------------------------------------|
| --text-brand            | 20px | 800    | 1.1    | 1px (uppercase)   | "EGGGYM" brand text                    |
| --text-name             | 26px | 800    | 1.2    | -0.3px            | "Coach Adrian" trainer name            |
| --text-email            | 14px | 500    | 1.3    | 0px               | "adrian.fit@egggym.com" email          |
| --text-stat-label       | 10px | 700    | 1.2    | 0.8px (uppercase) | "RATING" / "KLIEN" stat label          |
| --text-stat-value       | 28px | 800    | 1.0    | -0.5px            | "4.9" / "24" stat value                 |
| --text-stat-sub         | 12px | 500    | 1.3    | 0px               | "128 reviews" / "/30" sub-meta         |
| --text-section-label    | 11px | 700    | 1.2    | 0.8px (uppercase) | "SPESIALISASI" / "BIO" section label   |
| --text-chip             | 13px | 700    | 1.2    | 0px               | "Powerlifting" / "Hypertrophy" chip    |
| --text-bio              | 14px | 500    | 1.6    | 0px               | Bio paragraph text                      |
| --text-schedule-title   | 20px | 800    | 1.2    | 0px               | "Jadwal Aktif" card title              |
| --text-schedule-sub     | 13px | 500    | 1.3    | 0px               | "Minggu ini • 5 Hari Kerja" sub        |
| --text-edit-link        | 14px | 700    | 1.2    | 0px               | "Ubah" link                             |
| --text-day-label        | 10px | 700    | 1.2    | 0.5px (uppercase) | "SEN"/"SEL"/... day labels             |
| --text-menu-label       | 16px | 600    | 1.3    | 0px               | "Pengaturan Akun" / "Logout" menu      |
| --text-tab-label        | 9px  | 600    | 1.2    | 0.5px (uppercase) | Bottom tab labels                       |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Chip gap, tiny gaps                               |
| --space-sm     | 8px   | Icon-text gap, label gap                          |
| --space-md     | 12px  | Inter-element gap, chip spacing                   |
| --space-base   | 16px  | Screen horizontal padding, card padding           |
| --space-lg     | 20px  | Card-to-card vertical gap                         |
| --space-xl     | 24px  | Section separation                                |
| --space-2xl    | 32px  | Major block separation (avatar → stats)           |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Chip, small element                              |
| --radius-md    | 12px  | Stat card, menu row                              |
| --radius-lg    | 16px  | Spesialisasi, bio, jadwal aktif card             |
| --radius-pill  | 999px | Chip (pill), capacity bar                         |
| --radius-full  | 50%   | Hero avatar, edit fab, day dot, mini avatar       |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards default               |
| --shadow-avatar  | 0 0 24px rgba(245,197,24,0.3)         | Glow hero avatar ring       |
| --shadow-fab     | 0 2px 8px rgba(0,0,0,0.5)             | Edit FAB elevation          |
| --shadow-navbar  | 0 -2px 12px rgba(0,0,0,0.5)           | Bottom tab bar elevation    |

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Design Canvas:  430 × 932 px (mobile portrait)
Screen Padding: 16px horizontal
Safe Area Top:  ~44px (status bar device)
Brand Header:   100% width × ~64px (brand + notif + mini avatar)
Bottom Tab Bar: 100% width × 72px (fixed bottom, + safe-area-inset-bottom)
Content Scroll: vertical, padding-bottom 88px (ruang untuk tab bar)
Hero Avatar:    140px diameter, centered, edit fab bottom-right
Stat Cards:     2 kolom (Rating | Klien), gap 12px
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ EGGGYM                  [🔔] [👤]    │  ← Brand Header
├──────────────────────────────────────┤
│              ╭─────────╮              │
│              │ (avatar) │ [✏]        │  ← Hero Avatar + Edit FAB
│              ╰─────────╯              │
│            Coach Adrian               │  ← Name
│        adrian.fit@egggym.com          │  ← Email
│ ┌──────────────┐  ┌────────────────┐ │
│ │ ★    RATING  │  │ 👥      KLIEN   │ │  ← Stat Cards
│ │ 4.9          │  │ 24 /30          │ │
│ │ 128 reviews  │  │ ▓▓▓▓▓▓▓░░       │ │  ← Capacity Bar
│ └──────────────┘  └────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ SPESIALISASI                     │ │  ← Spesialisasi Card
│ │ [Powerlifting] [Hypertrophy]     │ │
│ │ [Mobility]                       │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ BIO                              │ │  ← Bio Card
│ │ Berdedikasi untuk membantu...    │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ Jadwal Aktif            Ubah     │ │  ← Jadwal Aktif Card
│ │ Minggu ini • 5 Hari Kerja        │ │
│ │ SEN SEL RAB KAM JUM SAB MIN      │ │
│ │  ●   ●   ●   ●   ●   ·   ·       │ │  ← Day Dots
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ ⚙ Pengaturan Akun            >  │ │  ← Menu Row
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │ ⎋ Logout                         │ │  ← Logout (destructive)
│ └──────────────────────────────────┘ │
├──────────────────────────────────────┤
│ 🏠     📅     👥      ⚡      👤    │  ← Bottom Tab Bar (TRAINER)
│ HOME JADWAL KLIEN PROGRAM PROFIL     │  ← PROFIL active
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

### 5.2 Kiri — Brand
```
Text:           "EGGGYM" → 20px, weight 800, uppercase, letter-spacing 1px, color #F5C518
```

### 5.3 Kanan — Notif + Mini Avatar
```
Display:        flex, align-items center, gap 12px
Notif Icon:     🔔 bell, 22px, color #F5C518
Mini Avatar:    32px × 32px, border-radius 50%, border 1.5px solid #F5C518, object-fit cover
```

---

## 6. KOMPONEN: HERO AVATAR + IDENTITY

### 6.1 Hero Avatar
```
Container:      centered, margin 24px auto 16px, position relative
Avatar:         140px × 140px, border-radius 50%, object-fit cover
Ring:           4px solid #F5C518, glow 0 0 24px rgba(245,197,24,0.3)

Edit FAB (bottom-right avatar):
  Size:         40px × 40px, border-radius 50%, background #F5C518
  Icon:         ✏ pencil, 18px, color #0E0E0E
  Position:     absolute, bottom 4px, right calc(50% - 70px + 4px)
  Box-shadow:   0 2px 8px rgba(0,0,0,0.5)
  Behavior:     tap → ganti foto profil
```

### 6.2 Identity
```
Name:           "Coach Adrian" → 26px, weight 800, color #FFFFFF, text-align center, letter-spacing -0.3px
Email:          "adrian.fit@egggym.com" → 14px, weight 500, color #9A9A9A, text-align center, margin-top 4px
```

---

## 7. KOMPONEN: STAT CARDS (Rating & Klien)

```
Layout:         grid 2 kolom (1fr 1fr), gap 12px
Padding:        0 16px
Margin:         24px 0

Card (umum):
  Background:   #1A1A1A
  Border:       1px solid #262626
  Border-radius:12px
  Padding:      16px

Card 1 — RATING:
  Header Row (flex, justify space-between, align center):
    Icon:       ★ star, 20px, color #F5C518
    Label:      "RATING" → 10px, weight 700, uppercase, color #6B6B6B
  Value:        "4.9" → 28px, weight 800, color #F5C518, margin-top 8px
  Sub:          "128 reviews" → 12px, weight 500, color #9A9A9A, margin-top 4px

Card 2 — KLIEN:
  Header Row (flex, justify space-between, align center):
    Icon:       👥 people, 20px, color #F5C518
    Label:      "KLIEN" → 10px, weight 700, uppercase, color #6B6B6B
  Value:        "24" → 28px, weight 800, color #FFFFFF + "/30" → 12px, weight 500, color #6B6B6B
  Capacity Bar (margin-top 10px):
    Track:      height 6px, background #2A2A2A, border-radius 999px
    Fill:       width 80% (24/30), background #F5C518, border-radius 999px
```

---

## 8. KOMPONEN: SPESIALISASI CARD

```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Padding:        16px 18px
Margin:         0 16px 20px

Label:          "SPESIALISASI" → 11px, weight 700, uppercase, letter-spacing 0.8px, color #6B6B6B
Margin-bottom:  12px

Chips (flex wrap, gap 10px):
  Chip:
    Background: #1C1C1C
    Border:     1px solid #2A2A2A
    Border-radius:999px
    Padding:    10px 16px
    Text:       "Powerlifting" / "Hypertrophy" / "Mobility" → 13px, weight 700, color #F5C518
```

---

## 9. KOMPONEN: BIO CARD

```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Padding:        16px 18px
Margin:         0 16px 20px

Label:          "BIO" → 11px, weight 700, uppercase, letter-spacing 0.8px, color #6B6B6B
Margin-bottom:  10px

Text:           "Berdedikasi untuk membantu klien mencapai potensi fisik maksimal melalui pendekatan
                sains dan disiplin tinggi. Spesialis dalam transformasi tubuh dan kekuatan fungsional
                selama lebih dari 8 tahun."
                → 14px, weight 500, line-height 1.6, color #9A9A9A
```

---

## 10. KOMPONEN: JADWAL AKTIF CARD

```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Padding:        18px
Margin:         0 16px 24px

Header Row (flex, justify space-between, align baseline):
  Title:        "Jadwal Aktif" → 20px, weight 800, color #FFFFFF
  Edit Link:    "Ubah" → 14px, weight 700, color #F5C518 (tap → edit jadwal kerja)

Sub:            "Minggu ini • 5 Hari Kerja" → 13px, weight 500, color #9A9A9A, margin-top 4px

Day Row (margin-top 16px, flex justify space-between):
  Per Day (flex column, align center, gap 8px):
    Label:      "SEN"/"SEL"/"RAB"/"KAM"/"JUM"/"SAB"/"MIN" → 10px, weight 700, uppercase
                color #9A9A9A (kerja) / #6B6B6B (libur)
    Dot:        10px × 10px, border-radius 50%
                Active (SEN-JUM): background #F5C518
                Idle (SAB-MIN):   background #3A3A3A
```

---

## 11. KOMPONEN: MENU ROWS

### 11.1 Pengaturan Akun
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  12px
Padding:        16px 18px
Margin:         0 16px 12px
Display:        flex, align-items center, gap 12px

Icon:           ⚙ gear, 20px, color #FFFFFF
Label:          "Pengaturan Akun" → 16px, weight 600, color #FFFFFF, flex 1
Chevron:        > right, 18px, color #6B6B6B
Behavior:       tap → buka halaman pengaturan akun
```

### 11.2 Logout (Destructive)
```
Background:     #1A1A1A
Border:         1px solid rgba(224,82,77,0.3)
Border-radius:  12px
Padding:        16px 18px
Margin:         0 16px 24px
Display:        flex, align-items center, gap 12px

Icon:           ⎋ logout/exit, 20px, color #E0524D
Label:          "Logout" → 16px, weight 600, color #E0524D
Behavior:       tap → konfirmasi (modal overlay) → keluar akun
```

---

## 12. KOMPONEN: BOTTOM TAB BAR (TRAINER VARIANT)

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
Label:          9px, weight 600, uppercase, letter-spacing 0.5px, color #6B6B6B
```

### 12.3 Tab Item (Active — PROFIL)
```
Icon:           22px, color #F5C518
Label-color:    #F5C518
Indicator:      highlight pill bg di belakang ikon PROFIL
                (bg rgba(245,197,24,0.12), border-radius 12px)
```

### 12.4 Daftar Tabs (5 item — VERSI TRAINER)
```
1. 🏠  HOME
2. 📅  JADWAL
3. 👥  KLIEN
4. ⚡  PROGRAM
5. 👤  PROFIL    ← ACTIVE (kuning)
```

---

## 13. GRID RECAP — RINGKASAN ZONA LAYOUT (Mobile)

| Zone                    | X Offset | Y Offset  | Width            | Height     |
|-------------------------|----------|-----------|------------------|------------|
| Brand Header            | 0        | safe-top  | 100%             | ~64px      |
| Hero Avatar             | center   | ~96px     | 140px            | 140px      |
| Name + Email            | 16px     | ~250px    | calc(100% - 32px)| ~60px      |
| Stat Cards (2 col)      | 16px     | ~330px    | calc(100% - 32px)| ~110px     |
| Spesialisasi Card       | 16px     | ~480px    | calc(100% - 32px)| ~150px     |
| Bio Card                | 16px     | ~660px    | calc(100% - 32px)| ~190px     |
| Jadwal Aktif Card       | 16px     | ~880px    | calc(100% - 32px)| ~140px     |
| Pengaturan Akun Row     | 16px     | ~1050px   | calc(100% - 32px)| ~58px      |
| Logout Row              | 16px     | ~1120px   | calc(100% - 32px)| ~58px      |
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px       |

*Catatan: konten jauh melebihi tinggi viewport (932px) → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 14. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Trainer Profile Screen (Profil Trainer, Pro Trainer, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Trainer Profile Dashboard.png
   Generated: 2026-06-27
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:        #0E0E0E;
  --color-bg-card:           #1A1A1A;
  --color-bg-card-alt:       #161616;
  --color-bg-chip:           #1C1C1C;
  --color-bg-fab:            #F5C518;
  --color-bg-navbar:         #121212;
  --color-accent-primary:    #F5C518;
  --color-accent-hover:      #E0B200;
  --color-text-primary:      #FFFFFF;
  --color-text-secondary:    #9A9A9A;
  --color-text-muted:        #6B6B6B;
  --color-text-on-accent:    #0E0E0E;
  --color-brand:             #F5C518;
  --color-avatar-ring:       #F5C518;
  --color-edit-fab-icon:     #0E0E0E;
  --color-rating-star:       #F5C518;
  --color-rating-value:      #F5C518;
  --color-stat-icon-klien:   #F5C518;
  --color-stat-value:        #FFFFFF;
  --color-stat-total:        #6B6B6B;
  --color-capacity-track:    #2A2A2A;
  --color-capacity-fill:     #F5C518;
  --color-chip-text:         #F5C518;
  --color-chip-border:       #2A2A2A;
  --color-day-active:        #F5C518;
  --color-day-idle:          #3A3A3A;
  --color-day-label:         #9A9A9A;
  --color-edit-link:         #F5C518;
  --color-menu-icon:         #FFFFFF;
  --color-menu-chevron:      #6B6B6B;
  --color-logout-text:       #E0524D;
  --color-logout-border:     rgba(224,82,77,0.3);
  --color-border-card:       #262626;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-brand:              20px;
  --text-name:               26px;
  --text-email:              14px;
  --text-stat-label:         10px;
  --text-stat-value:         28px;
  --text-stat-sub:           12px;
  --text-section-label:      11px;
  --text-chip:               13px;
  --text-bio:                14px;
  --text-schedule-title:     20px;
  --text-schedule-sub:       13px;
  --text-edit-link:          14px;
  --text-day-label:          10px;
  --text-menu-label:         16px;
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
  --shadow-avatar:           0 0 24px rgba(245,197,24,0.3);
  --shadow-fab:              0 2px 8px rgba(0,0,0,0.5);
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --header-height:           64px;
  --navbar-height:           72px;
  --hero-avatar-size:        140px;
  --edit-fab-size:           40px;
  --card-radius:             16px;
  --tab-count:               5;
}
```

---

## 15. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Trainer Profile Dashboard.png`. Semua teks (EGGGYM, Coach Adrian, adrian.fit@egggym.com, RATING, 4.9, 128 reviews, KLIEN, 24, /30, SPESIALISASI, Powerlifting, Hypertrophy, Mobility, BIO + paragraf bio penuh, Jadwal Aktif, Ubah, Minggu ini • 5 Hari Kerja, SEN/SEL/RAB/KAM/JUM/SAB/MIN, Pengaturan Akun, Logout) harus persis sama dengan gambar.

2. **TRAINER SIDE (Bukan Member)**: Bagian dari keluarga Trainer-side (lihat HOME_PT_DASHBOARD, TRAINER_SCHEDULE, CREATE_PROGRAM_FORM, EDIT_TRAINING_SESSION, PROGRESSIVE_UNLOCK_TIMELINE & LIVE_TRAINING_SESSION specs). Bottom tab bar versi trainer: **HOME / JADWAL / KLIEN / PROGRAM / PROFIL** dengan **PROFIL aktif** (tab kelima). Jangan tertukar dengan tab bar member.

3. **Mobile-First Layout**: Layar profil & akun trainer, konten panjang scrollable vertikal (jauh melebihi viewport). Gunakan `safe-area-inset-*`. Brand header membawa identitas EGGGYM + notif + mini avatar.

4. **Hero Avatar + Edit FAB**: Avatar besar bulat 140px dengan ring kuning + glow, dan FAB edit kuning (pensil) di kanan bawah untuk ganti foto. FAB harus overlay tepi avatar (absolute). Touch target FAB ≥44px.

5. **Stat Cards (Rating & Klien)**: Dua kartu setara. RATING menampilkan nilai (4.9 kuning) + jumlah review. KLIEN menampilkan kapasitas terpakai "24/30" dengan progress bar kapasitas (fill 80%) — menandakan slot klien hampir penuh. Nilai stat sebaiknya dinamis dari data trainer.

6. **Capacity Bar Semantik**: Bar pada kartu KLIEN bukan progres tugas, melainkan rasio kapasitas (klien aktif / maksimal). Pertimbangkan warna peringatan bila mendekati/penuh (mis. ≥90%). "/30" pakai warna muted untuk membedakan dari angka utama.

7. **Spesialisasi Chips**: Chip pill outline dengan teks kuning (Powerlifting, Hypertrophy, Mobility) — wrap ke baris baru bila banyak. Konsisten pola chip/filter dengan layar lain, namun di sini sebagai tag statis (bukan filter). Bisa editable lewat pengaturan.

8. **Bio Block**: Paragraf naratif bio trainer dengan line-height longgar (1.6) untuk keterbacaan. Teks abu sekunder. Pertimbangkan truncation "selengkapnya" bila bio sangat panjang.

9. **Jadwal Aktif (Day Dots)**: Kartu menampilkan ringkasan hari kerja mingguan via 7 dot (SEN-MIN). Dot kuning = hari kerja (SEN-JUM, 5 hari), dot abu = libur (SAB-MIN). Konsisten dengan sub "5 Hari Kerja". Link "Ubah" membuka editor jadwal. Sinkronkan dengan TRAINER_SCHEDULE.

10. **Menu Rows**: "Pengaturan Akun" (ikon gear + chevron, navigasi ke settings) dan "Logout" (destructive, teks/ikon merah `#E0524D`, border merah subtle). Bedakan visual menu navigasi biasa vs aksi destruktif.

11. **Logout Destructive**: Logout harus memicu konfirmasi (modal overlay `rgba(0,0,0,0.7)`) sebelum keluar akun. Gunakan warna merah konsisten dengan token "Tolak" di TRAINER_SCHEDULE (`#E0524D`).

12. **Relasi Antar-Layar**: Profil ini adalah hub akun trainer. Rating & jumlah klien terhubung ke data global; Jadwal Aktif terhubung ke TRAINER_SCHEDULE (Jadwal Sesi); mini avatar di brand header konsisten muncul di layar lain. Edit profil/jadwal memperbarui data lintas layar.

13. **Scroll & Padding**: Konten (avatar + 2 stat + spesialisasi + bio + jadwal + 2 menu) jauh melebihi viewport → scroll vertikal wajib. Beri `padding-bottom:88px` agar Logout tidak tertutup tab bar. Brand header boleh sticky.

14. **Accessibility**: Beri `aria-current="page"` pada tab PROFIL. Edit FAB beri `aria-label="Ubah foto profil"`. Stat cards beri konteks (mis. "Rating 4.9 dari 128 ulasan", "Klien 24 dari 30"). Capacity bar gunakan `role="progressbar"` + `aria-valuenow/max`. Day dots jangan andalkan warna saja — sertakan label hari + state (kerja/libur) via aria. Logout beri konfirmasi & `aria-label` jelas. Kontras teks pada elemen kuning/merah penuhi WCAG AA. Touch target minimum 44×44px.

---

*Spec ini generated dari analisis visual screen Trainer Profile Dashboard.png (visual-verified).*
*Design system reference: Egg Gym — Home PT Dashboard, Trainer Schedule (TRAINER_SCHEDULE_UI_SPEC.md), Create Program Form (CREATE_PROGRAM_FORM_UI_SPEC.md), Edit Training Session (EDIT_TRAINING_SESSION_UI_SPEC.md), Progressive Unlock Timeline (PROGRESSIVE_UNLOCK_TIMELINE_UI_SPEC.md), Live Training Session (LIVE_TRAINING_SESSION_UI_SPEC.md) & Member specs. CATATAN: sisi TRAINER, bottom tab bar HOME/JADWAL/KLIEN/PROGRAM/PROFIL, PROFIL aktif (tab kelima).*
*Total sections: 15 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

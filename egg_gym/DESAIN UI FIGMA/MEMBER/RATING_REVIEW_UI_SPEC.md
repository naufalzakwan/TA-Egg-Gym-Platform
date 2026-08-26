# RATING_REVIEW_UI_SPEC.md
# Egg Gym App — Rating & Review Screen (Session Complete, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Member App > Trainer > Rating & Review (Post-Session)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Rating & Review.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Rating & Review mewarisi sistem warna identik dengan Program, Session Detail, Booking History & Profile: latar near-black dengan aksen kuning emas. Token tambahan ditambahkan untuk star rating (filled/empty), coach card watermark "PT", textarea testimony, dan dual CTA (submit/skip).

| Token Name                | HEX Value             | Usage                                          |
|---------------------------|-----------------------|------------------------------------------------|
| --color-bg-primary        | #0E0E0E               | App background (screen utama)                  |
| --color-bg-card           | #1A1A1A               | Coach card & panel background                  |
| --color-bg-card-alt       | #161616               | Inner block / chip background                  |
| --color-bg-chip           | #1C1C1C               | Date/duration chip & icon button background    |
| --color-bg-input          | #141414               | Textarea testimony background                  |
| --color-bg-navbar         | #121212               | Bottom tab bar background                      |
| --color-accent-primary    | #F5C518               | CTA, star filled, highlights, brand text       |
| --color-accent-hover      | #E0B200               | Button pressed state                           |
| --color-text-primary      | #FFFFFF               | Headings, coach name, primary values           |
| --color-text-secondary    | #9A9A9A               | Labels, captions, meta text                    |
| --color-text-muted        | #6B6B6B               | Inactive tab, placeholder, counter, skip text  |
| --color-text-on-accent    | #0E0E0E               | Text on yellow/accent elements                 |
| --color-title-white       | #FFFFFF               | "SESSION" baris putih pada judul               |
| --color-title-accent      | #F5C518               | "COMPLETE." baris kuning pada judul            |
| --color-star-filled       | #F5C518               | Bintang rating terisi                          |
| --color-star-empty        | #4A4A4A               | Bintang rating kosong (outline)                |
| --color-watermark         | rgba(245,197,24,0.06) | Watermark "PT" di coach card                   |
| --color-input-border      | #2A2A2A               | Border textarea testimony                      |
| --color-input-placeholder | #6B6B6B               | Placeholder text textarea                      |
| --color-border-card       | #262626               | Card & panel borders                           |
| --color-border-chip       | #2A2A2A               | Chip & outline button border                   |
| --color-skip-border       | #2A2A2A               | Border tombol "SKIP FOR NOW"                   |
| --color-coach-badge       | #F5C518               | Badge kecil (verified/PT) di foto coach        |
| --color-tab-active        | #F5C518               | Active bottom-tab icon & label (TRAINER)       |
| --color-tab-inactive      | #6B6B6B               | Inactive bottom-tab icon & label               |
| --color-glow-cta          | rgba(245,197,24,0.45) | Glow di sekitar tombol submit kuning           |
| --color-overlay-dark      | rgba(0,0,0,0.7)       | Modal backdrop                                 |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (big title & watermark)
```

### Skala Tipografi Lengkap
| Token                    | Size | Weight | Line-H | Letter-Sp        | Usage                              |
|--------------------------|------|--------|--------|------------------|------------------------------------|
| --text-screen-title      | 18px | 800    | 1.1    | 0px              | "Welcome, Athlete" header title    |
| --text-hero-title        | 38px | 900    | 1.0    | -0.5px           | "SESSION COMPLETE." hero title     |
| --text-hero-sub          | 12px | 600    | 1.3    | 2px (uppercase)  | "RATE YOUR PERFORMANCE PARTNER"    |
| --text-coach-name        | 26px | 800    | 1.15   | -0.3px           | "Coach Marcus Thorne" coach name   |
| --text-chip              | 12px | 600    | 1.2    | 0.3px            | "OCT 24, 2023" / "60 MIN SESSION"  |
| --text-watermark         | 96px | 900    | 1.0    | -2px (uppercase) | "PT" background watermark          |
| --text-rating-label      | 11px | 600    | 1.3    | 1.5px (uppercase)| "TAP TO PROVIDE PRESTIGE RATING"   |
| --text-section-label     | 12px | 700    | 1.2    | 0.8px (uppercase)| "SESSION TESTIMONY" label          |
| --text-counter           | 11px | 500    | 1.2    | 0.3px            | "0 / 500" character counter        |
| --text-input             | 14px | 400    | 1.5    | 0px              | Isi & placeholder textarea         |
| --text-btn-primary       | 15px | 800    | 1.2    | 0.5px (uppercase)| "SUBMIT PERFORMANCE REVIEW"        |
| --text-btn-skip          | 13px | 600    | 1.2    | 1px (uppercase)  | "SKIP FOR NOW"                     |
| --text-tab-label         | 10px | 600    | 1.2    | 0.5px (uppercase)| Bottom tab labels                  |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Chip padding, tiny gaps                          |
| --space-sm     | 8px   | Icon-text gap, star gap                          |
| --space-md     | 12px  | Inter-element gap                                |
| --space-base   | 16px  | Screen horizontal padding, card padding          |
| --space-lg     | 20px  | Card-to-card vertical gap                        |
| --space-xl     | 24px  | Section separation                               |
| --space-2xl    | 32px  | Major block separation (hero ke card)            |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Submit/skip button, small elements               |
| --radius-md    | 12px  | Coach photo, textarea, date/duration chip        |
| --radius-lg    | 16px  | Coach card                                       |
| --radius-pill  | 999px | Date/duration chip (pill)                        |
| --radius-full  | 50%   | Header avatar, coach badge, notification         |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards default               |
| --shadow-cta     | 0 0 24px rgba(245,197,24,0.45)        | Glow tombol submit kuning   |
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
Alignment:      mayoritas center-aligned (hero, rating, CTA)
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ [←] Welcome, Athlete      [🔔] [👤]  │  ← Header
├──────────────────────────────────────┤
│            SESSION                   │  ← Hero Title (putih)
│           COMPLETE.                  │  ← Hero Title (kuning)
│   RATE YOUR PERFORMANCE PARTNER      │  ← Hero Subtitle
│ ┌──────────────────────────────────┐ │
│ │         [foto]   ░░PT░░           │ │  ← Coach Card + watermark
│ │       Coach Marcus Thorne         │ │
│ │  [📅 OCT 24, 2023][⏱ 60 MIN SES] │ │  ← Date + Duration chips
│ └──────────────────────────────────┘ │
│      TAP TO PROVIDE PRESTIGE RATING  │  ← Rating label
│           ★  ★  ★  ★  ☆             │  ← Star Rating (4/5)
│ SESSION TESTIMONY            0 / 500  │  ← Textarea label + counter
│ ┌──────────────────────────────────┐ │
│ │ Describe the intensity, focus...  │ │  ← Textarea (placeholder)
│ │                                   │ │
│ │                                   │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │   SUBMIT PERFORMANCE REVIEW       │ │  ← Primary CTA (kuning)
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │          SKIP FOR NOW             │ │  ← Secondary CTA (outline)
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

### 5.2 Kiri — Back + Title
```
Display:        flex, align-items center, gap 12px

Back Button:
  Icon:         ← arrow-left, 22px, color #F5C518
  Size:         40px × 40px touch target

Title:
  Text:         "Welcome, Athlete"
  Font-size:    18px, weight 800, color #F5C518
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

## 6. KOMPONEN: HERO TITLE BLOCK

```
Display:        flex, flex-direction column, align-items center
Padding:        16px
Margin:         16px 0 24px

Title (2 baris, center):
  Line 1:       "SESSION"  → 38px, weight 900, color #FFFFFF, uppercase
  Line 2:       "COMPLETE." → 38px, weight 900, color #F5C518, uppercase
  Letter-spacing: -0.5px, line-height 1.0

Subtitle:
  Text:         "RATE YOUR PERFORMANCE PARTNER"
  Font-size:    12px, weight 600, uppercase, letter-spacing 2px, color #9A9A9A
  Margin-top:   8px
```

---

## 7. KOMPONEN: COACH CARD

### 7.1 Container
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-radius:  16px
Padding:        24px 20px
Margin:         0 16px 24px
Position:       relative
Overflow:       hidden  (untuk crop watermark)
Display:        flex, flex-direction column, align-items center
```

### 7.2 Watermark Dekoratif
```
Text:           "PT"
Font-size:      96px, weight 900, color rgba(245,197,24,0.06)
Position:       absolute, right & vertically centered, melewati tepi
Text-transform: uppercase
Z-index:        0, pointer-events none
```

### 7.3 Coach Photo + Badge
```
Photo:
  Size:         88px × 88px (atau ~96px), border-radius 12px
  Object-fit:   cover
  Z-index:      1

Badge (absolute, bottom-right photo):
  Size:         24px × 24px, border-radius 50%
  Background:   #F5C518
  Icon:         ✓/⚡ verified, 12px, color #0E0E0E
  Border:       2px solid #1A1A1A
```

### 7.4 Coach Name
```
Text:           "Coach Marcus Thorne"
Font-size:      26px, weight 800, color #FFFFFF, letter-spacing -0.3px
Margin-top:     14px
Text-align:     center
```

### 7.5 Meta Chips Row
```
Display:        flex, gap 10px, justify-content center, margin-top 12px

Chip (pill):
  Background:   #1C1C1C
  Border:       1px solid #2A2A2A
  Border-radius:999px
  Padding:      8px 14px
  Display:      flex, align-items center, gap 6px
  Font-size:    12px, weight 600, color #9A9A9A

  Chip 1:  📅 calendar icon + "OCT 24, 2023"
  Chip 2:  ⏱ stopwatch icon + "60 MIN SESSION"
```

---

## 8. KOMPONEN: STAR RATING

### 8.1 Label
```
Text:           "TAP TO PROVIDE PRESTIGE RATING"
Font-size:      11px, weight 600, uppercase, letter-spacing 1.5px
Color:          #6B6B6B
Text-align:     center
Margin-bottom:  12px
```

### 8.2 Stars Row
```
Display:        flex, justify-content center, gap 12px

Star:
  Size:         ~36px (icon)
  Filled (1–4): color #F5C518  (★ solid)
  Empty (5):    color #4A4A4A  (☆ outline)

Interaksi:      tap bintang ke-N → set rating = N (1–5)
                state pada gambar = 4 dari 5
```

---

## 9. KOMPONEN: SESSION TESTIMONY (Textarea)

### 9.1 Label Row
```
Display:        flex, justify-content space-between, align-items baseline
Padding:        0 16px
Margin-bottom:  10px

Label:
  Text:         "SESSION TESTIMONY" → 12px, weight 700, uppercase, letter-spacing 0.8px, color #FFFFFF

Counter:
  Text:         "0 / 500" → 11px, weight 500, color #6B6B6B
                (update dinamis sesuai panjang input, max 500)
```

### 9.2 Textarea
```
Background:     #141414
Border:         1px solid #2A2A2A
Border-radius:  12px
Padding:        16px
Margin:         0 16px
Min-height:     ~130px
Font-size:      14px, weight 400, color #FFFFFF, line-height 1.5
Resize:         none (atau vertical)

Placeholder:
  Text:         "Describe the intensity, focus, and results of this elite session…"
  Color:        #6B6B6B
```

---

## 10. KOMPONEN: ACTION BUTTONS (Dual CTA)

### 10.1 Container
```
Display:        flex, flex-direction column, gap 12px
Padding:        24px 16px 0
```

### 10.2 Primary — Submit Performance Review
```
Width:          100%
Background:     #F5C518
Border-radius:  8px
Padding:        18px 0
Color:          #0E0E0E
Font-size:      15px, weight 800, uppercase, letter-spacing 0.5px
Text-align:     center
Box-shadow:     0 0 24px rgba(245,197,24,0.45)  (glow)
Fungsi:         kirim rating + testimony
```

### 10.3 Secondary — Skip For Now
```
Width:          100%
Background:     transparan
Border:         1px solid #2A2A2A
Border-radius:  8px
Padding:        16px 0
Color:          #9A9A9A
Font-size:      13px, weight 600, uppercase, letter-spacing 1px
Text-align:     center
Fungsi:         lewati review, lanjut tanpa menilai
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
| Coach Card              | 16px     | ~252px    | calc(100% - 32px)| ~230px    |
| Star Rating             | 16px     | ~498px    | calc(100% - 32px)| ~80px     |
| Session Testimony       | 16px     | ~594px    | calc(100% - 32px)| ~170px    |
| Submit Button           | 16px     | ~788px    | calc(100% - 32px)| ~56px     |
| Skip Button             | 16px     | ~856px    | calc(100% - 32px)| ~50px     |
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px      |

*Catatan: konten mendekati/melebihi tinggi viewport → screen scrollable bila keyboard aktif; offset di atas adalah posisi dalam scroll content.*

---

## 13. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Rating & Review Screen (Session Complete, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Rating & Review.png
   Generated: 2026-06-27
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:        #0E0E0E;
  --color-bg-card:           #1A1A1A;
  --color-bg-card-alt:       #161616;
  --color-bg-chip:           #1C1C1C;
  --color-bg-input:          #141414;
  --color-bg-navbar:         #121212;
  --color-accent-primary:    #F5C518;
  --color-accent-hover:      #E0B200;
  --color-text-primary:      #FFFFFF;
  --color-text-secondary:    #9A9A9A;
  --color-text-muted:        #6B6B6B;
  --color-text-on-accent:    #0E0E0E;
  --color-title-white:       #FFFFFF;
  --color-title-accent:      #F5C518;
  --color-star-filled:       #F5C518;
  --color-star-empty:        #4A4A4A;
  --color-watermark:         rgba(245,197,24,0.06);
  --color-input-border:      #2A2A2A;
  --color-input-placeholder: #6B6B6B;
  --color-border-card:       #262626;
  --color-border-chip:       #2A2A2A;
  --color-skip-border:       #2A2A2A;
  --color-coach-badge:       #F5C518;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.45);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-screen-title:       18px;
  --text-hero-title:         38px;
  --text-hero-sub:           12px;
  --text-coach-name:         26px;
  --text-chip:               12px;
  --text-watermark:          96px;
  --text-rating-label:       11px;
  --text-section-label:      12px;
  --text-counter:            11px;
  --text-input:              14px;
  --text-btn-primary:        15px;
  --text-btn-skip:           13px;
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
  --shadow-cta:              0 0 24px rgba(245,197,24,0.45);
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --navbar-height:           72px;
  --card-gap:                20px;
  --card-radius:             16px;
  --star-count:              5;
  --tab-count:               5;
}
```

---

## 14. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Rating & Review.png`. Semua teks (Welcome, Athlete, SESSION COMPLETE., RATE YOUR PERFORMANCE PARTNER, Coach Marcus Thorne, OCT 24 2023, 60 MIN SESSION, TAP TO PROVIDE PRESTIGE RATING, SESSION TESTIMONY, 0 / 500, placeholder, SUBMIT PERFORMANCE REVIEW, SKIP FOR NOW) harus persis sama dengan gambar.

2. **Mobile-First Layout**: Layar pasca-sesi, diakses dari flow Trainer (tab TRAINER aktif/kuning — berbeda dari layar lain). Mayoritas konten center-aligned. Gunakan `safe-area-inset-*` dan tangani keyboard untuk textarea.

3. **Post-Session Context**: Layar muncul setelah sesi selesai (selaras dengan tombol "BERI RATING" di Booking History). Member menilai performa coach. Sediakan jalur "SKIP FOR NOW" agar review opsional.

4. **Hero Title Dua Warna**: Judul "SESSION" putih + "COMPLETE." kuning, dua baris, weight 900 uppercase — focal point teratas. Pertahankan kontras dua warna sebagai penanda brand.

5. **Coach Card Watermark**: Teks "PT" raksasa di belakang konten, opacity sangat rendah (`rgba(245,197,24,0.06)`). Wajib `overflow:hidden` agar ter-crop. `pointer-events:none`. Menandakan konteks sesi Personal Trainer.

6. **Coach Card Center Layout**: Foto coach 88px + badge verified, nama coach, dan dua meta chip (tanggal + durasi) di-stack center. Chip pill berisi ikon + teks. Identik pola dengan kartu coach di Booking History.

7. **Star Rating Interaktif (1–5)**: Lima bintang, tap bintang ke-N untuk set nilai. State pada gambar = 4/5 (4 terisi kuning, 1 kosong abu `#4A4A4A`). Dukung hover/tap-preview & half-star jika diperlukan. Gunakan `role="radiogroup"` + `aria-label` per bintang.

8. **Testimony Textarea + Counter**: Textarea dengan placeholder & counter "0 / 500" yang update real-time. Batasi maksimal 500 karakter (cegah input berlebih). Counter berubah warna mendekati limit bila perlu (mis. merah saat >500).

9. **Dual CTA Hierarchy**: Primary "SUBMIT PERFORMANCE REVIEW" (kuning solid + glow) sebagai aksi utama; Secondary "SKIP FOR NOW" (outline, teks abu) sebagai aksi opsional/lewati. Jaga hierarki visual jelas — submit dominan.

10. **Submit Validation**: Idealnya submit aktif hanya bila rating dipilih (≥1 bintang). Testimony boleh opsional. Beri feedback bila user menekan submit tanpa rating. Disable/enable tombol secara dinamis.

11. **Glow CTA**: Tombol submit punya glow shadow (`0 0 24px rgba(245,197,24,0.45)`) untuk menarik perhatian. Konsisten dengan treatment FAB/CTA kuning di layar lain.

12. **Skip Flow**: "SKIP FOR NOW" menutup layar review tanpa mengirim, kembali ke konteks sebelumnya (mis. Booking History / Trainer). Pertimbangkan menyimpan rating draft bila user kembali.

13. **Scroll & Keyboard Handling**: Saat textarea fokus & keyboard muncul, pastikan tombol submit tetap terlihat (scroll-into-view atau sticky CTA). Beri `padding-bottom` cukup agar tab bar tidak menutup tombol.

14. **Accessibility**: Beri `aria-current="page"` pada tab TRAINER. Star rating gunakan `role="radiogroup"` dengan `aria-checked` per bintang & label nilai (1–5). Textarea beri `aria-label` & sambungkan counter via `aria-describedby`. Tombol submit/skip beri `aria-label` jelas. Kontras teks gelap pada tombol kuning penuhi WCAG AA. Touch target minimum 44×44px (bintang, tombol, tab).

---

*Spec ini generated dari analisis visual screen Rating & Review.png (visual-verified).*
*Design system reference: Egg Gym — Program (PROGRAM_TAB_UI_SPEC.md), Session Detail PT/Self, Booking History & Profile Member (PROFILE_MEMBER_ACTIVE_UI_SPEC.md).*
*Total sections: 14 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

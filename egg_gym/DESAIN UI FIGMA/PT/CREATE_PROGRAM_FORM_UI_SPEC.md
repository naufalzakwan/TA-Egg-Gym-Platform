# CREATE_PROGRAM_FORM_UI_SPEC.md
# Egg Gym App — Create Program Screen (Buat Program, Pro Trainer Side, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Trainer App > Program > Buat Program (Program Builder Form)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Create Program Form.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Buat Program (Pro Trainer) memakai sistem warna identik dengan Home PT Dashboard, Jadwal Sesi & sisi Member (Editorial Athletics): latar near-black dengan aksen kuning emas. Token tambahan ditambahkan untuk form field (input/dropdown/textarea), label DRAFT, inner stat block, empty-state dashed, accent rail session, dan CTA simpan.

| Token Name                  | HEX Value             | Usage                                            |
|-----------------------------|-----------------------|--------------------------------------------------|
| --color-bg-primary          | #0E0E0E               | App background (screen utama)                    |
| --color-bg-card             | #1A1A1A               | Session structure card background                |
| --color-bg-card-alt         | #161616               | Inner stat block background                      |
| --color-bg-input            | #161616               | Form field (dropdown/input/textarea) background  |
| --color-bg-chip             | #1C1C1C               | Secondary chip / idle surface                    |
| --color-bg-navbar           | #121212               | Bottom tab bar background                        |
| --color-accent-primary      | #F5C518               | CTA, brand text, links, accent rail, tab active  |
| --color-accent-hover        | #E0B200               | Button pressed state                             |
| --color-text-primary        | #FFFFFF               | Headings, input value, session title             |
| --color-text-secondary      | #9A9A9A               | Stat values caption, secondary meta              |
| --color-text-muted          | #6B6B6B               | Field labels, placeholder, "DRAFT", inactive tab |
| --color-text-placeholder    | #6B6B6B               | Placeholder text dalam input/textarea            |
| --color-text-on-accent      | #0E0E0E               | Text on yellow elements (CTA, tab active pill)   |
| --color-label               | #6B6B6B               | Uppercase field label (PILIH KLIEN, dst)         |
| --color-accent-rail         | #F5C518               | Left accent rail di session structure card       |
| --color-link                | #F5C518               | "+ TAMBAH SESI", "Struktur Sesi" heading         |
| --color-icon-delete         | #9A9A9A               | Ikon trash (hapus sesi)                           |
| --color-empty-icon          | #6B6B6B               | Ikon dumbbell pada empty state                   |
| --color-border-card         | #262626               | Card & panel borders                             |
| --color-border-input        | #2A2A2A               | Form field border                                |
| --color-border-dashed       | #2A2A2A               | Empty-state dashed border                        |
| --color-cta-bg              | #F5C518               | Background tombol "SIMPAN PROGRAM"                |
| --color-tab-active          | #F5C518               | Active bottom-tab icon & label (PROGRAM)         |
| --color-tab-inactive        | #6B6B6B               | Inactive bottom-tab icon & label                 |
| --color-glow-cta            | rgba(245,197,24,0.35) | Glow CTA kuning                                  |
| --color-overlay-dark        | rgba(0,0,0,0.7)       | Modal backdrop (dropdown klien)                  |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Display:    "Inter", system-ui  (screen title)
```

### Skala Tipografi Lengkap
| Token                   | Size | Weight | Line-H | Letter-Sp         | Usage                                  |
|-------------------------|------|--------|--------|-------------------|----------------------------------------|
| --text-topbar-title     | 20px | 800    | 1.1    | 0px               | "Buat Program" judul top bar           |
| --text-draft-label      | 12px | 700    | 1.2    | 1px (uppercase)   | "DRAFT" status label                   |
| --text-field-label      | 11px | 700    | 1.3    | 0.8px (uppercase) | "PILIH KLIEN" / "NAMA PROGRAM" / "DESKRIPSI" |
| --text-input-value      | 16px | 500    | 1.4    | 0px               | Nilai input & dropdown value           |
| --text-input-placeholder| 16px | 400    | 1.4    | 0px               | Placeholder text input/textarea        |
| --text-section-title    | 22px | 800    | 1.2    | 0px               | "Struktur Sesi" section heading        |
| --text-section-action   | 12px | 700    | 1.2    | 0.5px (uppercase) | "+ TAMBAH SESI" action link            |
| --text-session-index    | 11px | 700    | 1.2    | 0.8px (uppercase) | "SESI 01" index label                  |
| --text-session-title    | 20px | 800    | 1.2    | 0px               | "Chest & Triceps Focus" session name   |
| --text-stat-label       | 10px | 700    | 1.2    | 0.5px (uppercase) | "TOTAL GERAKAN" / "DURASI EST."        |
| --text-stat-value       | 22px | 800    | 1.1    | -0.3px            | "6" / "75m" stat value                  |
| --text-empty-state      | 14px | 500    | 1.4    | 0px               | "Belum ada sesi tambahan"              |
| --text-cta              | 16px | 800    | 1.2    | 1px (uppercase)   | "SIMPAN PROGRAM" button                 |
| --text-tab-label        | 9px  | 600    | 1.2    | 0.5px (uppercase) | Bottom tab labels                       |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Label-to-field gap, tiny gaps                    |
| --space-sm     | 8px   | Icon-text gap, inner gap                          |
| --space-md     | 12px  | Inter-element gap, stat block gap                 |
| --space-base   | 16px  | Screen horizontal padding, card/field padding     |
| --space-lg     | 20px  | Field-to-field vertical gap                       |
| --space-xl     | 24px  | Section separation                                |
| --space-2xl    | 32px  | Major block separation (form → struktur sesi)     |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Inner stat block, small element                  |
| --radius-md    | 12px  | Form field (input/dropdown/textarea)             |
| --radius-lg    | 16px  | Session card, empty-state card, CTA button       |
| --radius-pill  | 999px | Tab active pill                                  |
| --radius-full  | 50%   | Avatar top bar, profile icon                      |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards default               |
| --shadow-cta     | 0 0 20px rgba(245,197,24,0.35)        | Glow "Simpan Program" CTA   |
| --shadow-navbar  | 0 -2px 12px rgba(0,0,0,0.5)           | Bottom tab bar elevation    |

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Design Canvas:  430 × 932 px (mobile portrait)
Screen Padding: 16px horizontal
Safe Area Top:  ~44px (status bar device)
Top Bar:        100% width × ~64px (back + title + DRAFT + avatar)
Bottom Tab Bar: 100% width × 72px (fixed bottom, + safe-area-inset-bottom)
Content Scroll: vertical, padding-bottom 88px (ruang untuk tab bar)
Form Field:     full-width, gap 20px antar field
CTA:            full-width, sticky/akhir konten sebelum tab bar
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ (←) Buat Program     DRAFT      (👤)  │  ← Top Bar
├──────────────────────────────────────┤
│ PILIH KLIEN                          │  ← Field Label
│ ┌──────────────────────────────────┐ │
│ │ Pilih klien dari daftar       ▼  │ │  ← Dropdown
│ └──────────────────────────────────┘ │
│ NAMA PROGRAM                         │
│ ┌──────────────────────────────────┐ │
│ │ Contoh: Hypertrophy Phase A      │ │  ← Text Input
│ └──────────────────────────────────┘ │
│ DESKRIPSI                            │
│ ┌──────────────────────────────────┐ │
│ │ Jelaskan tujuan dan fokus...     │ │  ← Textarea
│ │                                  │ │
│ └──────────────────────────────────┘ │
│ Struktur Sesi      (+) TAMBAH SESI   │  ← Section header
│ ┃┌─────────────────────────────────┐ │
│ ┃│ SESI 01                    [🗑] │ │  ← Session Card
│ ┃│ Chest & Triceps Focus           │ │    (rail kuning)
│ ┃│ ┌────────────┐ ┌──────────────┐ │ │
│ ┃│ │TOTAL GERAKAN││ DURASI EST.   │ │ │  ← Inner Stat Blocks
│ ┃│ │     6      ││     75m       │ │ │
│ ┃│ └────────────┘ └──────────────┘ │ │
│ ┃└─────────────────────────────────┘ │
│ ┌ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┐ │
│           [🏋]  dumbbell             │  ← Empty State (dashed)
│      Belum ada sesi tambahan         │
│ └ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┘ │
│ ┌──────────────────────────────────┐ │
│ │        SIMPAN PROGRAM            │ │  ← Primary CTA (kuning)
│ └──────────────────────────────────┘ │
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
Back Icon:      ← arrow, 22px, color #F5C518
Title:          "Buat Program" → 20px, weight 800, color #F5C518
```

### 5.3 Kanan — DRAFT Label + Avatar
```
Display:        flex, align-items center, gap 12px
DRAFT Label:    "DRAFT" → 12px, weight 700, uppercase, letter-spacing 1px, color #6B6B6B
Avatar:         36px × 36px, border-radius 50%, border 1.5px solid #F5C518, object-fit cover
```

---

## 6. KOMPONEN: FORM FIELDS

### 6.1 Field Label (umum)
```
Text:           "PILIH KLIEN" / "NAMA PROGRAM" / "DESKRIPSI"
Font-size:      11px, weight 700, uppercase, letter-spacing 0.8px, color #6B6B6B
Margin:         0 0 8px (margin-bottom ke field)
Padding:        0 16px
```

### 6.2 Dropdown — "Pilih Klien"
```
Background:     #161616
Border:         1px solid #2A2A2A
Border-radius:  12px
Padding:        16px
Margin:         0 16px 20px
Display:        flex, justify-content space-between, align-items center
Value/Placeholder: "Pilih klien dari daftar" → 16px, weight 500, color #6B6B6B (placeholder state)
Chevron:        ▼ down icon, 18px, color #9A9A9A (kanan)
Behavior:       tap → buka modal/list klien (overlay #color-overlay-dark)
```

### 6.3 Text Input — "Nama Program"
```
Background:     #161616
Border:         1px solid #2A2A2A
Border-radius:  12px
Padding:        16px
Margin:         0 16px 20px
Height:         ~56px
Placeholder:    "Contoh: Hypertrophy Phase A" → 16px, weight 400, color #6B6B6B
Value (filled): 16px, weight 500, color #FFFFFF
Focus state:    border 1px solid #F5C518 (rekomendasi)
```

### 6.4 Textarea — "Deskripsi"
```
Background:     #161616
Border:         1px solid #2A2A2A
Border-radius:  12px
Padding:        16px
Margin:         0 16px 32px
Min-height:     ~120px (multi-line, align text top)
Placeholder:    "Jelaskan tujuan dan fokus program ini..." → 16px, weight 400, color #6B6B6B
Value (filled): 16px, weight 500, color #FFFFFF, line-height 1.4
```

---

## 7. KOMPONEN: STRUKTUR SESI (Session Structure)

### 7.1 Section Header
```
Display:        flex, justify-content space-between, align-items center
Padding:        0 16px
Margin:         32px 0 16px

Judul:
  Text:         "Struktur Sesi" → 22px, weight 800, color #F5C518

Action:
  Icon+Text:    "(+) TAMBAH SESI"
  Icon:         ⊕ plus dalam lingkaran, 18px, color #F5C518
  Text:         12px, weight 700, uppercase, letter-spacing 0.5px, color #F5C518
  Behavior:     tap → tambah session card baru ke daftar
```

### 7.2 Session Card (Filled)
```
Background:     #1A1A1A
Border:         1px solid #262626
Border-left:    4px solid #F5C518   (accent rail — sesi aktif/terisi)
Border-radius:  16px
Padding:        16px
Margin:         0 16px 16px

Top Row (flex, justify-content space-between, align-items flex-start):
  Index:        "SESI 01" → 11px, weight 700, uppercase, letter-spacing 0.8px, color #F5C518
  Delete Icon:  🗑 trash, 18px, color #9A9A9A (tap → konfirmasi hapus sesi)

Session Title:
  Text:         "Chest & Triceps Focus" → 20px, weight 800, color #FFFFFF
  Margin:       4px 0 16px

Stat Row (flex, gap 12px):
  Inner Stat Block ×2 (flex 1):
    Background:   #161616
    Border-radius:8px
    Padding:      12px 14px
    Label:        "TOTAL GERAKAN" / "DURASI EST." → 10px, weight 700, uppercase, color #6B6B6B
    Value:        "6" / "75m" → 22px, weight 800, color #FFFFFF, margin-top 4px
```

### 7.3 Empty State Card (Belum Ada Sesi)
```
Background:     transparan
Border:         1.5px dashed #2A2A2A
Border-radius:  16px
Padding:        32px 16px
Margin:         0 16px 32px
Display:        flex, flex-direction column, align-items center, gap 12px

Icon:           🏋 dumbbell (outline), 28px, color #6B6B6B
Text:           "Belum ada sesi tambahan" → 14px, weight 500, color #6B6B6B, text-align center

Catatan: empty-state ditampilkan sebagai placeholder slot sesi berikutnya;
hilang/diganti card terisi setelah "Tambah Sesi" diisi.
```

---

## 8. KOMPONEN: PRIMARY CTA — SIMPAN PROGRAM

```
Width:          calc(100% - 32px)
Margin:         8px 16px 24px
Background:     #F5C518
Color:          #0E0E0E
Padding:        18px 0
Border-radius:  16px
Font:           16px, weight 800, uppercase, letter-spacing 1px, text-align center
Box-shadow:     0 0 20px rgba(245,197,24,0.35)  (glow)
Behavior:       tap → validasi form (klien & nama wajib) → simpan program
Disabled state: opacity 0.5 bila field wajib kosong (rekomendasi)
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
| Field: Pilih Klien      | 16px     | ~120px    | calc(100% - 32px)| ~80px      |
| Field: Nama Program     | 16px     | ~210px    | calc(100% - 32px)| ~80px      |
| Field: Deskripsi        | 16px     | ~300px    | calc(100% - 32px)| ~150px     |
| Struktur Sesi Header    | 16px     | ~480px    | calc(100% - 32px)| ~30px      |
| Session Card (filled)   | 16px     | ~526px    | calc(100% - 32px)| ~160px     |
| Empty State Card        | 16px     | ~700px    | calc(100% - 32px)| ~110px     |
| CTA Simpan Program      | 16px     | ~840px    | calc(100% - 32px)| ~58px      |
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px       |

*Catatan: konten melebihi tinggi viewport (932px) → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 11. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Create Program Screen (Buat Program, Pro Trainer, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Create Program Form.png
   Generated: 2026-06-27
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:        #0E0E0E;
  --color-bg-card:           #1A1A1A;
  --color-bg-card-alt:       #161616;
  --color-bg-input:          #161616;
  --color-bg-chip:           #1C1C1C;
  --color-bg-navbar:         #121212;
  --color-accent-primary:    #F5C518;
  --color-accent-hover:      #E0B200;
  --color-text-primary:      #FFFFFF;
  --color-text-secondary:    #9A9A9A;
  --color-text-muted:        #6B6B6B;
  --color-text-placeholder:  #6B6B6B;
  --color-text-on-accent:    #0E0E0E;
  --color-label:             #6B6B6B;
  --color-accent-rail:       #F5C518;
  --color-link:              #F5C518;
  --color-icon-delete:       #9A9A9A;
  --color-empty-icon:        #6B6B6B;
  --color-border-card:       #262626;
  --color-border-input:      #2A2A2A;
  --color-border-dashed:     #2A2A2A;
  --color-cta-bg:            #F5C518;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.35);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-topbar-title:       20px;
  --text-draft-label:        12px;
  --text-field-label:        11px;
  --text-input-value:        16px;
  --text-input-placeholder:  16px;
  --text-section-title:      22px;
  --text-section-action:     12px;
  --text-session-index:      11px;
  --text-session-title:      20px;
  --text-stat-label:         10px;
  --text-stat-value:         22px;
  --text-empty-state:        14px;
  --text-cta:                16px;
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
  --shadow-cta:              0 0 20px rgba(245,197,24,0.35);
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --topbar-height:           64px;
  --navbar-height:           72px;
  --field-gap:               20px;
  --card-radius:             16px;
  --tab-count:               5;
}
```

---

## 12. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Create Program Form.png`. Semua teks (Buat Program, DRAFT, PILIH KLIEN, Pilih klien dari daftar, NAMA PROGRAM, Contoh: Hypertrophy Phase A, DESKRIPSI, Jelaskan tujuan dan fokus program ini..., Struktur Sesi, TAMBAH SESI, SESI 01, Chest & Triceps Focus, TOTAL GERAKAN, 6, DURASI EST., 75m, Belum ada sesi tambahan, SIMPAN PROGRAM) harus persis sama dengan gambar.

2. **TRAINER SIDE (Bukan Member)**: Bagian dari keluarga Trainer-side (lihat HOME_PT_DASHBOARD_UI_SPEC & TRAINER_SCHEDULE_UI_SPEC). Bottom tab bar versi trainer: **HOME / JADWAL / KLIEN / PROGRAM / PROFIL** dengan **PROGRAM aktif**. Jangan tertukar dengan tab bar member.

3. **Mobile-First Layout**: Layar form pembuatan program, konten scrollable vertikal. Gunakan `safe-area-inset-*`. Top bar membawa back navigation + status DRAFT + avatar trainer.

4. **Status DRAFT**: Label "DRAFT" di top bar kanan menandai program belum disimpan/dipublikasikan. Setelah "Simpan Program", status bisa berubah (mis. "AKTIF"). Pertimbangkan auto-save draft saat field berubah.

5. **Form Fields (3 jenis)**: Dropdown (Pilih Klien), text input single-line (Nama Program), dan textarea multi-line (Deskripsi). Semua memakai bg `#161616`, border `#2A2A2A`, radius 12px. Placeholder pakai `#6B6B6B`; value terisi putih `#FFFFFF`. Beri focus state border kuning untuk kejelasan.

6. **Validasi Wajib**: "Pilih Klien" dan "Nama Program" sebaiknya field wajib; CTA "Simpan Program" disabled (opacity 0.5) sampai keduanya terisi. Deskripsi opsional.

7. **Dropdown Behavior**: Tap field "Pilih Klien" membuka modal/list klien dengan overlay `rgba(0,0,0,0.7)`. Konsisten pola overlay dengan layar lain. Gunakan native `<select>` atau custom dropdown beraksesibilitas.

8. **Struktur Sesi — Dynamic List**: Section ini daftar dinamis. "+ TAMBAH SESI" menambah session card baru. Tiap card punya index auto (SESI 01, 02, ...), judul sesi, dan dua inner stat block (TOTAL GERAKAN, DURASI EST.). Index harus re-number otomatis saat ada penghapusan.

9. **Session Card Accent Rail**: Tiap card sesi memakai `border-left:4px solid #F5C518` (accent rail) — konsisten dengan request card di TRAINER_SCHEDULE_UI_SPEC. Trash icon (kanan atas) memicu konfirmasi hapus (destructive).

10. **Inner Stat Blocks**: Dua blok `#161616` radius 8px berdampingan (flex 1 masing-masing), gap 12px. Label kecil uppercase abu + value besar putih bold. Nilai (6, 75m) idealnya dihitung otomatis dari gerakan yang ditambahkan ke sesi.

11. **Empty State (dashed)**: Card border dashed `1.5px #2A2A2A` dengan ikon dumbbell + teks "Belum ada sesi tambahan" sebagai slot placeholder sesi berikutnya. Tampil saat belum ada sesi tambahan; bisa juga jadi tap-target untuk "Tambah Sesi".

12. **Primary CTA Full-Width**: "SIMPAN PROGRAM" kuning solid full-width dengan glow, teks gelap uppercase. Berbeda dari kartu yang punya aksi ganda — di sini satu CTA dominan di akhir form. Bisa dibuat sticky di atas tab bar agar selalu terjangkau.

13. **Scroll & Padding**: Konten lebih tinggi dari viewport → scroll vertikal. Beri `padding-bottom:88px` agar CTA/empty-state tidak tertutup tab bar. Top bar boleh sticky agar back & status DRAFT selalu terlihat.

14. **Accessibility**: Beri `aria-current="page"` pada tab PROGRAM. Setiap field punya `<label>` terhubung (`for`/`id`). Dropdown beraksesibilitas (`role`/`aria-expanded`). Trash icon beri `aria-label` menyertakan nama sesi (mis. "Hapus Sesi 01 Chest & Triceps Focus") + konfirmasi. CTA disabled beri `aria-disabled`. Kontras teks gelap pada elemen kuning penuhi WCAG AA. Touch target minimum 44×44px.

---

*Spec ini generated dari analisis visual screen Create Program Form.png (visual-verified).*
*Design system reference: Egg Gym — Home PT Dashboard (HOME_PT_DASHBOARD_UI_SPEC.md), Trainer Schedule (TRAINER_SCHEDULE_UI_SPEC.md) & Member specs. CATATAN: sisi TRAINER, bottom tab bar HOME/JADWAL/KLIEN/PROGRAM/PROFIL, PROGRAM aktif.*
*Total sections: 12 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

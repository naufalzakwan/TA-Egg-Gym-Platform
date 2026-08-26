# EDIT_TRAINING_SESSION_UI_SPEC.md
# Egg Gym App — Build/Edit Session Screen (Buat Sesi, Pro Trainer Side, Mobile)
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Trainer App > Program > Buat Program > Buat Sesi (Session Exercise Builder)
# Platform: Mobile (iOS/Android), Portrait
# Viewport: 430 × 932 px (design canvas mobile)
# Last Updated: 2026-06-27
# Source of truth: Edit Training Session.png (visual-verified)

---

## 1. DESIGN TOKENS — COLOR PALETTE

Layar Buat Sesi (Pro Trainer) memakai sistem warna identik dengan Home PT Dashboard, Jadwal Sesi, Buat Program & sisi Member (Editorial Athletics): latar near-black dengan aksen kuning emas. Token tambahan ditambahkan untuk input nama sesi, exercise list item, ikon meta (sets/reps), tag muscle group, tombol edit/delete bertumpuk, opsi pilih-sumber (dashed), dan CTA simpan sesi.

| Token Name                  | HEX Value             | Usage                                            |
|-----------------------------|-----------------------|--------------------------------------------------|
| --color-bg-primary          | #0E0E0E               | App background (screen utama)                    |
| --color-bg-card             | #1F1F1F               | Exercise list item background                    |
| --color-bg-card-alt         | #161616               | Inner / nested block background                  |
| --color-bg-input            | #161616               | Input "Nama Sesi" background                      |
| --color-bg-icon-btn         | #262626               | Background tombol edit & delete (square)          |
| --color-bg-chip             | #1C1C1C               | Secondary chip / idle surface                     |
| --color-bg-navbar           | #121212               | Bottom tab bar background                         |
| --color-accent-primary      | #F5C518               | CTA, brand text, sets icon, meta count, tab active|
| --color-accent-hover        | #E0B200               | Button pressed state                              |
| --color-text-primary        | #FFFFFF               | Headings, session name, exercise name             |
| --color-text-secondary      | #9A9A9A               | Sets/reps meta text                               |
| --color-text-muted          | #6B6B6B               | Field labels, muscle tag, drag handle, inactive tab|
| --color-text-on-accent      | #0E0E0E               | Text on yellow elements (CTA, tab active pill)    |
| --color-label               | #6B6B6B               | Uppercase field label "NAMA SESI"                 |
| --color-meta-count          | #F5C518               | "3 LATIHAN" meta badge text                       |
| --color-meta-count-bg       | rgba(245,197,24,0.15) | Background badge "3 LATIHAN"                       |
| --color-icon-sets           | #F5C518               | Ikon sets (dumbbell/diamond) kuning               |
| --color-icon-reps           | #9A9A9A               | Ikon reps (loop/refresh) abu                      |
| --color-tag-muscle          | #6B6B6B               | Tag otot "QUADRICEPS"/"HAMSTRINGS" (uppercase)    |
| --color-icon-edit           | #9A9A9A               | Ikon pensil (edit exercise)                        |
| --color-icon-delete         | #9A9A9A               | Ikon trash (hapus exercise)                        |
| --color-drag-handle         | #6B6B6B               | Drag handle (⠿) reorder exercise                  |
| --color-border-card         | #262626               | Card & list item borders                          |
| --color-border-dashed       | #2A2A2A               | Border opsi "Pilih dari Database/Tambah Manual"   |
| --color-cta-bg              | #F5C518               | Background tombol "Simpan Sesi"                    |
| --color-tab-active          | #F5C518               | Active bottom-tab icon & label (PROGRAM)          |
| --color-tab-inactive        | #6B6B6B               | Inactive bottom-tab icon & label                  |
| --color-glow-cta            | rgba(245,197,24,0.45) | Glow CTA kuning                                   |
| --color-overlay-dark        | rgba(0,0,0,0.7)       | Modal backdrop (edit exercise / database picker)  |

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
| --text-topbar-title     | 20px | 800    | 1.1    | 0px               | "Buat Sesi" judul top bar              |
| --text-field-label      | 11px | 700    | 1.3    | 0.8px (uppercase) | "NAMA SESI" field label                |
| --text-input-value      | 22px | 700    | 1.3    | -0.3px            | "Leg Power Day" nilai input nama sesi  |
| --text-section-title    | 20px | 800    | 1.2    | 0px               | "Daftar Latihan" section heading       |
| --text-section-meta     | 10px | 700    | 1.1    | 0.5px (uppercase) | "3 LATIHAN" meta badge                  |
| --text-exercise-name    | 17px | 700    | 1.3    | 0px               | "Barbell Back Squat" exercise name     |
| --text-exercise-meta    | 13px | 600    | 1.3    | 0px               | "4 sets" / "8-10 reps" meta            |
| --text-muscle-tag       | 10px | 700    | 1.2    | 0.5px (uppercase) | "QUADRICEPS" / "HAMSTRINGS"            |
| --text-option-label     | 11px | 700    | 1.3    | 0.5px (uppercase) | "PILIH DARI DATABASE" / "TAMBAH MANUAL"|
| --text-cta              | 16px | 800    | 1.2    | 0.3px             | "Simpan Sesi" button                    |
| --text-tab-label        | 9px  | 600    | 1.2    | 0.5px (uppercase) | Bottom tab labels                       |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px / mobile)
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --space-xs     | 4px   | Icon-text gap, tiny gaps                          |
| --space-sm     | 8px   | Meta row gap, tag spacing                         |
| --space-md     | 12px  | Inter-element gap, exercise item gap              |
| --space-base   | 16px  | Screen horizontal padding, card padding           |
| --space-lg     | 20px  | List-to-options vertical gap                      |
| --space-xl     | 24px  | Section separation                                |
| --space-2xl    | 32px  | Major block separation (options → CTA)            |

### Border Radius
| Token          | Value | Usage                                           |
|----------------|-------|-------------------------------------------------|
| --radius-sm    | 8px   | Edit/delete icon button, small element           |
| --radius-md    | 12px  | Input nama sesi, exercise list item, option card |
| --radius-lg    | 16px  | CTA button, large container                       |
| --radius-pill  | 999px | Meta badge, tab active pill                       |
| --radius-full  | 50%   | Avatar top bar                                    |

### Box Shadows
| Token            | Value                                  | Usage                       |
|------------------|----------------------------------------|-----------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)             | Cards & list items          |
| --shadow-cta     | 0 0 20px rgba(245,197,24,0.45)        | Glow "Simpan Sesi" CTA      |
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
Exercise List:  full-width list item, gap 12px, drag-reorderable
Options:        2 kolom (Pilih Database | Tambah Manual), gap 12px
CTA:            full-width, akhir konten sebelum tab bar
```

### ASCII Layout Diagram
```
┌──────────────────────────────────────┐
│ (←) Buat Sesi                  (👤)   │  ← Top Bar
├──────────────────────────────────────┤
│ NAMA SESI                            │  ← Field Label
│ ┌──────────────────────────────────┐ │
│ │ Leg Power Day                    │ │  ← Text Input (filled)
│ └──────────────────────────────────┘ │
│ Daftar Latihan          [3 LATIHAN]  │  ← Section header + badge
│ ┌──────────────────────────────────┐ │
│ │⠿ Barbell Back Squat        [✏] │ │  ← Exercise Item
│ │   ◈ 4 sets  ⇄ 8-10 reps     [🗑] │ │    (drag handle + actions)
│ │   QUADRICEPS                     │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │⠿ Romanian Deadlift         [✏] │ │  ← Exercise Item
│ │   ◈ 3 sets  ⇄ 12 reps       [🗑] │ │
│ │   HAMSTRINGS                     │ │
│ └──────────────────────────────────┘ │
│ ┌──────────────────────────────────┐ │
│ │⠿ Leg Press                 [✏] │ │  ← Exercise Item
│ │   ◈ 3 sets  ⇄ 15 reps       [🗑] │ │
│ │   QUADRICEPS                     │ │
│ └──────────────────────────────────┘ │
│ ┌ ─ ─ ─ ─ ─ ─ ┐  ┌ ─ ─ ─ ─ ─ ─ ┐    │
│ │    🗄        │  │     ⊕         │   │  ← Source Options (dashed)
│ │ PILIH DARI   │  │  TAMBAH       │   │
│ │ DATABASE     │  │  MANUAL       │   │
│ └ ─ ─ ─ ─ ─ ─ ┘  └ ─ ─ ─ ─ ─ ─ ┘    │
│ ┌──────────────────────────────────┐ │
│ │     💾  Simpan Sesi              │ │  ← Primary CTA (kuning)
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
Back Icon:      ← arrow, 22px, color #FFFFFF
Title:          "Buat Sesi" → 20px, weight 800, color #FFFFFF
```

### 5.3 Kanan — Avatar
```
Avatar:         36px × 36px, border-radius 50%, border 1.5px solid #F5C518, object-fit cover
```

---

## 6. KOMPONEN: INPUT NAMA SESI

### 6.1 Field Label
```
Text:           "NAMA SESI"
Font-size:      11px, weight 700, uppercase, letter-spacing 0.8px, color #6B6B6B
Margin:         0 0 8px
Padding:        0 16px
```

### 6.2 Text Input
```
Background:     #161616
Border:         1px solid #262626
Border-radius:  12px
Padding:        16px 18px
Margin:         0 16px 24px
Height:         ~64px
Value (filled): "Leg Power Day" → 22px, weight 700, color #FFFFFF, letter-spacing -0.3px
Placeholder:    (mis. "Contoh: Leg Power Day") → 22px, weight 500, color #6B6B6B
Focus state:    border 1px solid #F5C518 (rekomendasi)
```

---

## 7. KOMPONEN: DAFTAR LATIHAN (Exercise List)

### 7.1 Section Header
```
Display:        flex, justify-content space-between, align-items center
Padding:        0 16px
Margin-bottom:  12px

Judul:
  Text:         "Daftar Latihan" → 20px, weight 800, color #FFFFFF

Meta Badge:
  Text:         "3 LATIHAN"
  Font:         10px, weight 700, uppercase, letter-spacing 0.5px, color #F5C518
  Background:   rgba(245,197,24,0.15), padding 5px 10px, border-radius 999px
```

### 7.2 Exercise List Item
```
Background:     #1F1F1F
Border:         1px solid #262626
Border-radius:  12px
Padding:        16px
Margin:         0 16px 12px
Display:        flex, align-items flex-start, gap 12px

Drag Handle (kiri):
  Icon:         ⠿ (6-dot grip), 16px, color #6B6B6B
  Behavior:     long-press / drag untuk reorder exercise (sortable list)

Info (flex 1):
  Name:         "Barbell Back Squat" / "Romanian Deadlift" / "Leg Press"
                → 17px, weight 700, color #FFFFFF
  Meta Row (flex, align center, gap 14px, margin-top 6px):
    Sets:       ◈ icon (kuning #F5C518) + "4 sets"/"3 sets" → 13px, weight 600, color #9A9A9A
    Reps:       ⇄ icon (abu #9A9A9A) + "8-10 reps"/"12 reps"/"15 reps" → 13px, weight 600, color #9A9A9A
  Muscle Tag:   "QUADRICEPS" / "HAMSTRINGS"
                → 10px, weight 700, uppercase, letter-spacing 0.5px, color #6B6B6B, margin-top 8px

Action Buttons (kanan, stacked vertikal, gap 8px):
  Edit Button:
    Size:       34px × 34px, background #262626, border-radius 8px
    Icon:       ✏ pencil, 16px, color #9A9A9A
    Behavior:   tap → buka editor exercise (sets/reps/notes) via modal
  Delete Button:
    Size:       34px × 34px, background #262626, border-radius 8px
    Icon:       🗑 trash, 16px, color #9A9A9A
    Behavior:   tap → konfirmasi hapus exercise (destructive)
```

---

## 8. KOMPONEN: OPSI SUMBER LATIHAN (Add Exercise Options)

```
Display:        grid 2 kolom (1fr 1fr), gap 12px
Padding:        0 16px
Margin:         8px 0 24px

Option Card (×2):
  Background:   transparan
  Border:       1.5px dashed #2A2A2A
  Border-radius:12px
  Padding:      24px 16px
  Display:      flex, flex-direction column, align-items center, gap 10px

  Card 1 — Pilih dari Database:
    Icon:       🗄 database/stack, 22px, color #6B6B6B
    Label:      "PILIH DARI DATABASE" → 11px, weight 700, uppercase, color #6B6B6B, text-align center
    Behavior:   tap → buka picker library latihan (overlay)

  Card 2 — Tambah Manual:
    Icon:       ⊕ plus-circle, 22px, color #6B6B6B
    Label:      "TAMBAH MANUAL" → 11px, weight 700, uppercase, color #6B6B6B, text-align center
    Behavior:   tap → form input exercise manual baru
```

---

## 9. KOMPONEN: PRIMARY CTA — SIMPAN SESI

```
Width:          calc(100% - 32px)
Margin:         8px 16px 24px
Background:     #F5C518
Color:          #0E0E0E
Padding:        18px 0
Border-radius:  16px
Display:        flex, align-items center, justify-content center, gap 8px
Icon:           💾 save (floppy), 18px, color #0E0E0E
Label:          "Simpan Sesi" → 16px, weight 800, letter-spacing 0.3px
Box-shadow:     0 0 20px rgba(245,197,24,0.45)  (glow)
Behavior:       tap → validasi (nama sesi & ≥1 latihan) → simpan sesi ke program
Disabled state: opacity 0.5 bila nama kosong / daftar latihan kosong (rekomendasi)
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
| Top Bar                 | 0        | safe-top  | 100%             | ~64px      |
| Field: Nama Sesi        | 16px     | ~108px    | calc(100% - 32px)| ~90px      |
| Daftar Latihan Header   | 16px     | ~220px    | calc(100% - 32px)| ~30px      |
| Exercise Item ×3        | 16px     | ~262px    | calc(100% - 32px)| ~100px each|
| Source Options (2 col)  | 16px     | ~580px    | calc(100% - 32px)| ~110px     |
| CTA Simpan Sesi         | 16px     | ~720px    | calc(100% - 32px)| ~58px      |
| Bottom Tab Bar          | 0        | bottom: 0 | 100%             | 72px       |

*Catatan: konten bisa melebihi tinggi viewport (932px) saat banyak latihan → screen scrollable; offset di atas adalah posisi dalam scroll content.*

---

## 12. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Build/Edit Session Screen (Buat Sesi, Pro Trainer, Mobile)
   CSS Custom Properties — Design Tokens
   Visual-verified: Edit Training Session.png
   Generated: 2026-06-27
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:        #0E0E0E;
  --color-bg-card:           #1F1F1F;
  --color-bg-card-alt:       #161616;
  --color-bg-input:          #161616;
  --color-bg-icon-btn:       #262626;
  --color-bg-chip:           #1C1C1C;
  --color-bg-navbar:         #121212;
  --color-accent-primary:    #F5C518;
  --color-accent-hover:      #E0B200;
  --color-text-primary:      #FFFFFF;
  --color-text-secondary:    #9A9A9A;
  --color-text-muted:        #6B6B6B;
  --color-text-on-accent:    #0E0E0E;
  --color-label:             #6B6B6B;
  --color-meta-count:        #F5C518;
  --color-meta-count-bg:     rgba(245,197,24,0.15);
  --color-icon-sets:         #F5C518;
  --color-icon-reps:         #9A9A9A;
  --color-tag-muscle:        #6B6B6B;
  --color-icon-edit:         #9A9A9A;
  --color-icon-delete:       #9A9A9A;
  --color-drag-handle:       #6B6B6B;
  --color-border-card:       #262626;
  --color-border-dashed:     #2A2A2A;
  --color-cta-bg:            #F5C518;
  --color-tab-active:        #F5C518;
  --color-tab-inactive:      #6B6B6B;
  --color-glow-cta:          rgba(245,197,24,0.45);
  --color-overlay-dark:      rgba(0,0,0,0.7);

  /* ── TYPOGRAPHY ── */
  --font-family-primary:     "Inter", "Segoe UI", -apple-system, sans-serif;
  --text-topbar-title:       20px;
  --text-field-label:        11px;
  --text-input-value:        22px;
  --text-section-title:      20px;
  --text-section-meta:       10px;
  --text-exercise-name:      17px;
  --text-exercise-meta:      13px;
  --text-muscle-tag:         10px;
  --text-option-label:       11px;
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
  --shadow-cta:              0 0 20px rgba(245,197,24,0.45);
  --shadow-navbar:           0 -2px 12px rgba(0,0,0,0.5);

  /* ── LAYOUT ── */
  --screen-padding:          16px;
  --topbar-height:           64px;
  --navbar-height:           72px;
  --list-item-gap:           12px;
  --card-radius:             12px;
  --option-cols:             2;
  --tab-count:               5;
}
```

---

## 13. CATATAN AI — IMPLEMENTATION NOTES (14 poin)

1. **Source of Truth**: Spec ini diverifikasi langsung dari `Edit Training Session.png`. Semua teks (Buat Sesi, NAMA SESI, Leg Power Day, Daftar Latihan, 3 LATIHAN, Barbell Back Squat, 4 sets, 8-10 reps, QUADRICEPS, Romanian Deadlift, 3 sets, 12 reps, HAMSTRINGS, Leg Press, 15 reps, PILIH DARI DATABASE, TAMBAH MANUAL, Simpan Sesi) harus persis sama dengan gambar.

2. **TRAINER SIDE (Bukan Member)**: Bagian dari keluarga Trainer-side (lihat HOME_PT_DASHBOARD, TRAINER_SCHEDULE & CREATE_PROGRAM_FORM specs). Bottom tab bar versi trainer: **HOME / JADWAL / KLIEN / PROGRAM / PROFIL** dengan **PROGRAM aktif**. Jangan tertukar dengan tab bar member.

3. **Relasi dengan Buat Program**: Layar ini adalah drill-down dari CREATE_PROGRAM_FORM — satu kartu "SESI 01" di Buat Program dibuka jadi editor ini. "TOTAL GERAKAN" & "DURASI EST." di Buat Program harus dihitung dari isi Daftar Latihan di sini (mis. 3 latihan → 3 gerakan). Sinkronkan data antar dua layar.

4. **Mobile-First Layout**: Layar editor sesi, konten scrollable vertikal. Gunakan `safe-area-inset-*`. Top bar membawa back navigation + avatar trainer (tanpa label DRAFT di layar ini).

5. **Input Nama Sesi**: Field tunggal besar, value bold 22px putih ("Leg Power Day"). Wajib diisi. Beri focus state border kuning untuk kejelasan editing.

6. **Daftar Latihan — Sortable List**: Daftar dinamis exercise. Meta badge "3 LATIHAN" mencerminkan jumlah item dan harus update otomatis saat tambah/hapus. Item bisa di-reorder via drag handle (⠿) di kiri — gunakan library sortable beraksesibilitas.

7. **Exercise Item Anatomy**: Tiap item = drag handle + nama exercise + meta row (sets & reps) + muscle tag + dua tombol aksi bertumpuk (edit/delete). Ikon sets memakai aksen kuning `#F5C518`; ikon reps abu `#9A9A9A`. Bedakan dua ikon ini dengan jelas.

8. **Meta Sets/Reps**: Format "N sets" dan rentang/angka reps ("8-10 reps", "12 reps", "15 reps"). Reps bisa berupa range atau nilai tunggal — dukung kedua format. Nilai ini editable lewat tombol edit.

9. **Muscle Tag**: Tag otot uppercase abu (`QUADRICEPS`, `HAMSTRINGS`) di bawah meta. Berasal dari metadata exercise (terutama bila dipilih dari database). Bila tambah manual, sediakan field muscle group.

10. **Action Buttons (stacked)**: Tombol edit (✏) & delete (🗑) ditumpuk vertikal di kanan item, masing-masing 34×34px bg `#262626` radius 8px. Edit → modal editor exercise; Delete → konfirmasi (destructive). Beri touch target memadai (≥44px area sentuh).

11. **Source Options (dashed, 2 kolom)**: Dua kartu dashed setara — "PILIH DARI DATABASE" (buka library latihan via overlay) dan "TAMBAH MANUAL" (form exercise baru). Keduanya `border:1.5px dashed #2A2A2A`, ikon + label uppercase abu, terpusat. Keduanya menambah item ke Daftar Latihan.

12. **Primary CTA Full-Width**: "Simpan Sesi" kuning solid full-width dengan ikon save + glow, teks gelap. Validasi: nama sesi terisi & minimal 1 latihan. Bisa dibuat sticky di atas tab bar agar selalu terjangkau.

13. **Scroll & Padding**: Saat latihan bertambah konten melebihi viewport → scroll vertikal. Beri `padding-bottom:88px` agar CTA/opsi tidak tertutup tab bar. Top bar boleh sticky agar back selalu terlihat.

14. **Accessibility**: Beri `aria-current="page"` pada tab PROGRAM. Drag handle beri `aria-label` + dukungan keyboard reorder. Input nama sesi punya `<label for>`. Setiap tombol edit/delete beri `aria-label` menyertakan nama exercise (mis. "Edit Barbell Back Squat", "Hapus Leg Press") + delete pakai konfirmasi. Opsi dashed gunakan elemen `<button>`. CTA disabled beri `aria-disabled`. Kontras teks gelap pada elemen kuning penuhi WCAG AA. Touch target minimum 44×44px.

---

*Spec ini generated dari analisis visual screen Edit Training Session.png (visual-verified).*
*Design system reference: Egg Gym — Home PT Dashboard, Trainer Schedule (TRAINER_SCHEDULE_UI_SPEC.md), Create Program Form (CREATE_PROGRAM_FORM_UI_SPEC.md) & Member specs. CATATAN: sisi TRAINER, bottom tab bar HOME/JADWAL/KLIEN/PROGRAM/PROFIL, PROGRAM aktif. Layar ini drill-down dari Buat Program.*
*Total sections: 13 | Detail level: ⭐⭐⭐⭐⭐ Full Detail | Zero mismatch.*

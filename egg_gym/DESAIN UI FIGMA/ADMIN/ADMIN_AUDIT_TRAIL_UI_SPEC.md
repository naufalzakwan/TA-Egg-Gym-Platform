# ADMIN_AUDIT_TRAIL_UI_SPEC.md
# Egg Gym App — Admin Audit Trail Screen
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Admin > Audit Trail (Log Aktivitas Sistem)
# Resolution: 1280 × 1466 px
# Last Updated: 2026-06-24

---

## 1. DESIGN TOKENS — COLOR PALETTE

| Token Name                    | HEX Value                      | Usage                                           |
|-------------------------------|--------------------------------|-------------------------------------------------|
| --color-bg-primary            | #1A1500                        | Main content background & hero section          |
| --color-bg-card               | #252000                        | Log entry card backgrounds                      |
| --color-bg-sidebar            | #141000                        | Sidebar background                              |
| --color-bg-header             | #1E1900                        | Top header bar background                       |
| --color-bg-input              | #2A2400                        | Search bar & filter input background            |
| --color-bg-filter-bar         | #1E1900                        | Filter bar strip background                     |
| --color-accent-primary        | #F5C300                        | Timeline dot aktif, ADMIN badge, active filter  |
| --color-accent-hover          | #E0B000                        | Button hover, tab hover                         |
| --color-text-primary          | #FFFFFF                        | Entry titles, names, primary text               |
| --color-text-secondary        | #8A8070                        | Timestamps, helper text, labels                 |
| --color-text-muted            | #5A5040                        | Placeholders, disabled state                    |
| --color-text-on-accent        | #1A1500                        | Text on yellow/accent elements                  |
| --color-status-success        | #4CAF50                        | SUCCESS, ACTIVE, ENTRY CREATED badges           |
| --color-status-warning        | #F59E0B                        | LOGGED X EXERCISES, modification badges         |
| --color-status-danger         | #EF4444                        | FAILED: ..., SYSTEM ALERT badges                |
| --color-status-info           | #3B82F6                        | TRAINER role badge text                         |
| --color-border-card           | #2E2800                        | Card borders, row dividers                      |
| --color-border-sidebar        | #2A2400                        | Sidebar dividers                                |
| --color-timeline-line         | #2E2800                        | Vertical timeline connector line                |
| --color-timeline-dot-active   | #F5C300                        | Active / recent entry timeline dot              |
| --color-timeline-dot-inactive | #5A5040                        | Older entry timeline dot                        |
| --color-role-admin-bg         | rgba(245,195,0,0.15)           | ADMIN role badge background (kuning redup)      |
| --color-role-admin-text       | #F5C300                        | ADMIN role badge text                           |
| --color-role-trainer-bg       | rgba(59,130,246,0.15)          | TRAINER role badge background (biru redup)      |
| --color-role-trainer-text     | #3B82F6                        | TRAINER role badge text                         |
| --color-role-system-bg        | rgba(239,68,68,0.15)           | SYSTEM role badge background (merah redup)      |
| --color-role-system-text      | #EF4444                        | SYSTEM role badge text                          |
| --color-watermark             | rgba(245,195,0,0.04)           | "LOGS" watermark background text tint           |
| --color-pagination-active     | #F5C300                        | Active pagination button                        |
| --color-pagination-default    | #252000                        | Default pagination button background            |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Monospace:  "JetBrains Mono", "Fira Code", monospace  (untuk action codes, IDs)
```

### Skala Tipografi Lengkap
| Token                     | Size | Weight | Line-H | Letter-Sp        | Usage                                |
|---------------------------|------|--------|--------|------------------|--------------------------------------|
| --text-hero-supra         | 10px | 700    | 1.2    | 3px (uppercase)  | "SYSTEM INTEGRITY" hero label        |
| --text-hero-title         | 36px | 800    | 1.1    | -0.5px           | "Activity Archive" H1                |
| --text-hero-subtitle      | 13px | 400    | 1.6    | 0px              | Hero descriptor paragraph            |
| --text-hero-watermark     | 160px| 900    | 1.0    | 0px              | "LOGS" background watermark          |
| --text-page-label         | 11px | 700    | 1.2    | 2px (uppercase)  | Section sub-labels                   |
| --text-section-title      | 14px | 700    | 1.3    | 0px              | Panel headings                       |
| --text-entry-action       | 14px | 600    | 1.3    | 0px              | Log entry primary action text        |
| --text-entry-detail       | 12px | 400    | 1.5    | 0px              | Log entry details / body             |
| --text-entry-meta         | 11px | 400    | 1.3    | 0.3px            | Timestamp, IP address                |
| --text-badge-role         | 9px  | 700    | 1.0    | 1.5px            | ADMIN / TRAINER / SYSTEM role badges |
| --text-badge-status       | 9px  | 700    | 1.0    | 1px              | SUCCESS / FAILED / LOGGED badges     |
| --text-filter-label       | 11px | 600    | 1.0    | 1px (uppercase)  | Filter tab labels                    |
| --text-filter-count       | 10px | 500    | 1.0    | 0px              | "(123)" count badge in filter        |
| --text-breadcrumb-main    | 18px | 700    | 1.2    | 0.08em           | "Audit Trail" header title           |
| --text-breadcrumb-sub     | 14px | 400    | 1.2    | 0px              | "/ Log Aktivitas" subtitle           |
| --text-pagination-num     | 13px | 600    | 1.0    | 0px              | Pagination page numbers              |
| --text-pagination-nav     | 11px | 700    | 1.0    | 1px (uppercase)  | "PREV" / "NEXT" labels               |
| --text-search             | 13px | 400    | 1.0    | 0px              | Search bar input text                |
| --text-nav-item           | 13px | 500    | 1.4    | 0px              | Sidebar navigation items             |
| --text-result-count       | 11px | 400    | 1.2    | 0px              | "Showing X–Y of Z results"           |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px)
| Token          | Value | Usage                                                  |
|----------------|-------|--------------------------------------------------------|
| --space-xs     | 4px   | Badge padding inner, icon gaps                         |
| --space-sm     | 8px   | Timeline dot gap, tag spacing                          |
| --space-md     | 12px  | Entry card inner padding                               |
| --space-base   | 16px  | Standard component margin                              |
| --space-lg     | 20px  | Filter bar horizontal padding, section gap             |
| --space-xl     | 24px  | Hero section padding horizontal                        |
| --space-hero-v | 28px  | Hero section padding vertical                          |
| --space-2xl    | 32px  | Major section separation                               |

### Border Radius
| Token         | Value | Usage                                                   |
|---------------|-------|---------------------------------------------------------|
| --radius-xs   | 4px   | Status badges, chips, pagination active                 |
| --radius-sm   | 6px   | Filter tabs, search bar, small buttons                  |
| --radius-md   | 10px  | Log entry cards, panels                                 |
| --radius-full | 50%   | Timeline dots, avatar circles                           |

### Box Shadows
| Token            | Value                              | Usage                         |
|------------------|------------------------------------|-------------------------------|
| --shadow-card    | 0 2px 8px rgba(0,0,0,0.4)         | Log entry card default        |
| --shadow-hover   | 0 6px 16px rgba(0,0,0,0.5)        | Card on hover                 |
| --shadow-sidebar | 2px 0 8px rgba(0,0,0,0.5)         | Sidebar right edge            |

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Total Canvas:   1280 × 1466 px
Sidebar:        220px wide × 100vh (fixed)
Header Bar:     calc(100vw - 220px) × 56px (sticky)
Hero Section:   calc(100vw - 220px) × ~130px
Filter Bar:     calc(100vw - 220px) × ~52px
Log Timeline:   calc(100vw - 220px), scrollable, padding 20px
Pagination:     calc(100vw - 220px) × ~48px
```

### ASCII Layout Diagram
```
┌─────────────────────┬────────────────────────────────────────────────────────┐
│  SIDEBAR (220px)    │  HEADER BAR (56px)                                     │
│  ───────────────    │  ────────────────────────────────────────────────────  │
│  ◈ Editorial        │  Audit Trail  / Log Aktivitas    🔍  🔔  ⚙  👤         │
│    Athletics        ├────────────────────────────────────────────────────────┤
│  ───────────────    │  HERO SECTION (~130px)                                  │
│  ⊞ Dashboard        │  ┌──────────────────────────────────────── [LOGS besar]│
│  👥 Member          │  │ SYSTEM INTEGRITY                                    │
│  📅 Slot Mgmt       │  │ Activity Archive                                    │
│  ⭐ Personal Trainer│  │ Secure, immutable ledger of all...                  │
│  📋 Booking & Sesi  │  └─────────────────────────────────────────────────── │
│  🏋 Equipment       ├────────────────────────────────────────────────────────┤
│  📃 Audit Log ◄AKTIF│  FILTER BAR (~52px)                                    │
│  📅 Slot Mng        │  [SEMUA ▼] [ADMIN] [TRAINER] [SYSTEM]  🔍  [Export]   │
│  📊 Laporan         ├────────────────────────────────────────────────────────┤
│  ───────────────    │  LOG TIMELINE (scrollable)                              │
│  [A] Admin Elite    │  ● ─ [Entry Card 1 — SUCCESS] ─ timestamp             │
│  admin@egggym.id    │  │                                                     │
│                     │  ● ─ [Entry Card 2 — FAILED] ─ timestamp              │
│                     │  │                                                     │
│                     │  ● ─ [Entry Card 3 — LOGGED] ─ timestamp              │
│                     │  │                                                     │
│                     │  ● ─ [Entry Card 4 — SUCCESS] ─ timestamp             │
│                     ├────────────────────────────────────────────────────────┤
│                     │  PAGINATION FOOTER (~48px)                              │
│                     │  Showing 1–10 of 247  [PREV] [1] [2] [3] ... [NEXT]   │
└─────────────────────┴────────────────────────────────────────────────────────┘
```

---

## 5. KOMPONEN: SIDEBAR

### 5.1 Container
```
Width:          220px
Height:         100vh
Background:     #141000
Border-right:   1px solid #2A2400
Box-shadow:     2px 0 8px rgba(0,0,0,0.5)
Position:       fixed, left: 0, top: 0
Z-index:        200
Display:        flex flex-column
Overflow-y:     auto
```

### 5.2 Logo / Brand Area
```
Padding:        16px 16px 14px
Border-bottom:  1px solid #2A2400

Logo Mark:
  Width/Height: 32px
  Fill:         #F5C300

Brand Text:
  "Editorial Athletics"
  Font-size:    14px, Weight: 700, Color: #FFFFFF
```

### 5.3 Navigation Menu Items
```
Default item:
  Height:       40px
  Padding:      10px 16px
  Icon:         16px, color #8A8070
  Text:         13px/500, color #8A8070
  Hover:        bg #1E1900, icon+text → #D4AA00

Active item (Audit Log):
  Background:   #252000
  Border-left:  3px solid #F5C300
  Padding-left: 13px
  Icon+Text:    color #F5C300, weight 600
```

### 5.4 Menu Order
```
1.  ⊞  Dashboard
2.  👥  Member
3.  📅  Slot Management
4.  ⭐  Personal Trainer
5.  📋  Booking & Sesi
6.  🏋  Equipment
7.  📃  Audit Log         ← ACTIVE
8.  📅  Slot Mng
9.  📊  Laporan
```

### 5.5 Profile Area (Bottom)
```
Padding:        12px 16px
Border-top:     1px solid #2A2400
Avatar:         36px circle, bg #F5C300, text "A" color #1A1500
Name:           13px/600, #FFFFFF
Email:          11px/400, #8A8070
```

---

## 6. KOMPONEN: TOP HEADER BAR

### 6.1 Container
```
Height:         56px
Background:     #1E1900
Border-bottom:  1px solid #2E2800
Padding:        0 20px
Display:        flex, align-items center, justify-content space-between
Position:       sticky, top 0, z-index 100
Width:          calc(100vw - 220px)
```

### 6.2 Kiri — Breadcrumb
```
Display:        flex, align-items baseline, gap 6px

"Audit Trail":
  Font-size:    18px
  Font-weight:  700
  Color:        #FFFFFF

"/ Log Aktivitas":
  Font-size:    14px
  Font-weight:  400
  Color:        #8A8070
```

### 6.3 Tengah — Search Bar
```
Width:          280px, Height: 32px
Background:     #2A2400
Border:         1px solid #2E2800
Border-radius:  6px
Padding:        0 10px, Gap: 8px

Icon: 14px, color #5A5040
Input: 13px, color #FFFFFF, placeholder "Cari log, pengguna, aksi..."
Focus: border → 1px solid #F5C300
```

### 6.4 Kanan — Icons
```
Bell:     20px, color #8A8070, badge dot 6px #EF4444
Settings: 20px, color #8A8070
Avatar:   28px circle, bg #F5C300, text "A" color #1A1500
```

---

## 7. KOMPONEN: HERO SECTION

### 7.1 Container
```
Background:     #1A1500 (sama dengan page bg — seamless)
Padding:        28px 32px
Min-height:     130px
Position:       relative
Overflow:       hidden
Display:        flex, align-items center
```

### 7.2 Konten Kiri
```
Max-width:      520px
Z-index:        1

Supra-label:
  Text:         "SYSTEM INTEGRITY"
  Font-size:    10px
  Font-weight:  700
  Color:        #8A8070
  Letter-spacing:3px (uppercase)
  Margin-bottom:8px

Main Title (H1):
  Text:         "Activity Archive"
  Font-size:    36px
  Font-weight:  800
  Color:        #FFFFFF
  Letter-spacing:-0.5px
  Margin-bottom:8px

Subtitle:
  Text:         "Secure, immutable ledger of all administrative and
                 technical actions within the Editorial Athletics ecosystem."
  Font-size:    13px
  Color:        #8A8070
  Line-height:  1.6
  Max-width:    420px
```

### 7.3 Watermark Dekoratif (Background)
```
Content:        "LOGS"
Position:       absolute
Right:          -20px
Top:            -10px
Font-size:      160px
Font-weight:    900
Color:          rgba(245,195,0,0.04)
Pointer-events: none
User-select:    none
Z-index:        0
Letter-spacing: -5px
```

---

## 8. KOMPONEN: FILTER BAR

### 8.1 Container
```
Background:     #1E1900
Border-bottom:  1px solid #2E2800
Padding:        8px 20px
Height:         ~52px
Display:        flex, align-items center, justify-content space-between
Gap:            12px
```

### 8.2 Kiri — Filter Tabs
```
Display:        flex, gap 8px

Tab Default:
  Height:       30px
  Padding:      0 14px
  Background:   #252000
  Border:       1px solid #2E2800
  Border-radius:4px
  Font-size:    11px / 600
  Color:        #8A8070
  Letter-spacing:1px (uppercase)
  Cursor:       pointer
  Transition:   all 0.15s

  Hover:
    Color:      #D4AA00
    Border:     #5A4800

Tab Active (SEMUA):
  Background:   #F5C300
  Border:       #F5C300
  Color:        #1A1500
  Font-weight:  700
```

### 8.3 Filter Tab List
```
Tab 1: "SEMUA"     ← Active (kuning)
Tab 2: "ADMIN"
Tab 3: "TRAINER"
Tab 4: "SYSTEM"
Tab 5: "MEMBER"    (jika ada)
```

### 8.4 Kanan — Actions
```
Search Input Compact:
  Width:        200px, Height: 28px
  Background:   #2A2400
  Border:       1px solid #2E2800
  Border-radius:4px
  Placeholder:  "Filter log..."
  Font-size:    12px

Export Button:
  Text:         "EXPORT"
  Font-size:    11px / 700
  Color:        #8A8070
  Background:   #252000
  Border:       1px solid #2E2800
  Border-radius:4px
  Padding:      4px 12px
  Hover: color → #FFFFFF, border → #5A4800
```

---

## 9. KOMPONEN: LOG TIMELINE

### 9.1 Container
```
Padding:        20px 24px
Display:        flex, flex-direction column
Gap:            0 (entries connected via timeline line)
Position:       relative
```

### 9.2 Timeline Line (Connector)
```
Position:       absolute
Left:           39px (aligned to center of dots)
Top:            0
Bottom:         0
Width:          1px
Background:     #2E2800
Z-index:        0
```

### 9.3 Log Entry Card — Container
```
Display:        flex, flex-direction row
Align-items:    flex-start
Gap:            16px
Padding:        0 0 20px 0
Position:       relative
Z-index:        1
```

### 9.4 Timeline Dot
```
Width:          14px
Height:         14px
Border-radius:  50%
Flex-shrink:    0
Margin-top:     14px
Position:       relative, z-index 2

Recent entry (active):
  Background:   #F5C300
  Box-shadow:   0 0 8px rgba(245,195,0,0.4)

Older entry:
  Background:   #5A5040
  Box-shadow:   none
```

### 9.5 Entry Card — Card Body
```
Flex:           1
Background:     #252000
Border:         1px solid #2E2800
Border-radius:  10px
Padding:        14px 18px
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
Transition:     border-color 0.15s

Hover:
  Border-color: rgba(245,195,0,0.3)
```

### 9.6 Entry Card — Header Row
```
Display:        flex, justify-content space-between, align-items center
Margin-bottom:  8px

Kiri:
  Display:      flex, align-items center, gap 10px

  Role Badge:
    Padding:    3px 10px
    Border-radius:4px
    Font-size:  9px / 700
    Letter-spacing:1.5px (uppercase)
    White-space:nowrap

    ADMIN:
      Background: rgba(245,195,0,0.15)
      Color:      #F5C300

    TRAINER:
      Background: rgba(59,130,246,0.15)
      Color:      #3B82F6

    SYSTEM:
      Background: rgba(239,68,68,0.15)
      Color:      #EF4444

    MEMBER:
      Background: rgba(76,175,80,0.15)
      Color:      #4CAF50

  User Name:
    Font-size:  14px / 600
    Color:      #FFFFFF

Kanan:
  Timestamp:
    Font-size:  11px / 400
    Color:      #8A8070
    White-space:nowrap
```

### 9.7 Entry Card — Action Text
```
Font-size:      13px
Font-weight:    400
Color:          #FFFFFF
Line-height:    1.5
Margin-bottom:  8px
```

### 9.8 Entry Card — Bottom Meta Row
```
Display:        flex, align-items center, gap 12px, flex-wrap wrap
Margin-top:     8px
Border-top:     1px solid #2E2800
Padding-top:    8px

Status Badge:
  Padding:      3px 10px
  Border-radius:4px
  Font-size:    9px / 700
  Letter-spacing:1px (uppercase)

  SUCCESS / ACTIVE / ENTRY CREATED:
    Background: rgba(76,175,80,0.15), Color: #4CAF50

  LOGGED X EXERCISES / MODIFIED:
    Background: rgba(245,195,0,0.15), Color: #F59E0B

  FAILED: ... / ALERT:
    Background: rgba(239,68,68,0.15), Color: #EF4444

IP Address:
  Font-size:    11px / 400
  Color:        #5A5040
  Font-family:  monospace

Module / Screen:
  Font-size:    11px / 400
  Color:        #8A8070
```

### 9.9 Data Contoh — Log Entries (4 entries)
```
ENTRY 1 (Recent - kuning dot):
  Role:         "ADMIN"    → bg rgba(245,195,0,0.15), text #F5C300
  User:         Admin Elite
  Timestamp:    "2 minutes ago · 14:32 WIB"
  Action:       "Menambahkan paket membership baru: Platinum Ultra 3 Bulan
                 dengan harga Rp 2.400.000"
  Status badge: "ENTRY CREATED" → #4CAF50
  IP:           "192.168.1.101"
  Module:       "Membership Packages"

ENTRY 2:
  Role:         "TRAINER"  → bg rgba(59,130,246,0.15), text #3B82F6
  User:         Coach Adrian
  Timestamp:    "15 minutes ago · 14:19 WIB"
  Action:       "Mencatat sesi latihan Naufal Azhar — logged 8 exercises,
                 durasi 90 menit, upper body strength"
  Status badge: "LOGGED 8 EXERCISES" → #F59E0B
  IP:           "192.168.1.45"
  Module:       "Booking & Sesi PT"

ENTRY 3:
  Role:         "SYSTEM"   → bg rgba(239,68,68,0.15), text #EF4444
  User:         SYSTEM
  Timestamp:    "32 minutes ago · 14:02 WIB"
  Action:       "Percobaan login gagal terdeteksi dari IP tidak dikenal —
                 akses ditolak setelah 3 percobaan"
  Status badge: "FAILED: MAX ATTEMPTS" → #EF4444
  IP:           "203.0.113.42"
  Module:       "Authentication"

ENTRY 4:
  Role:         "ADMIN"    → bg rgba(245,195,0,0.15), text #F5C300
  User:         Admin Elite
  Timestamp:    "1 hour ago · 13:35 WIB"
  Action:       "Mengubah data member Sarah Wijaya — update paket dari
                 Standard menjadi VIP Membership"
  Status badge: "SUCCESS" → #4CAF50
  IP:           "192.168.1.101"
  Module:       "Member Management"
```

---

## 10. KOMPONEN: PAGINATION FOOTER

### 10.1 Container
```
Padding:        12px 24px
Border-top:     1px solid #2E2800
Background:     #1A1500
Display:        flex, justify-content space-between, align-items center
Height:         ~48px
```

### 10.2 Kiri — Result Count
```
Text:           "Showing 1–10 of 247 results"
Font-size:      11px / 400
Color:          #8A8070
```

### 10.3 Kanan — Pagination Controls
```
Display:        flex, align-items center, gap 4px

PREV Button:
  Text:         "PREV"
  Font-size:    11px / 700
  Color:        #8A8070
  Background:   #252000
  Border:       1px solid #2E2800
  Border-radius:4px
  Padding:      5px 12px
  Hover:        color #FFFFFF

Page Number (default):
  Size:         30px × 28px
  Background:   #252000
  Border:       1px solid #2E2800
  Border-radius:4px
  Font-size:    13px / 600
  Color:        #8A8070

Page Number (active):
  Background:   #F5C300
  Border:       #F5C300
  Color:        #1A1500
  Font-weight:  700

Ellipsis "...":
  Font-size:    13px, color #5A5040

NEXT Button:
  Same style as PREV
  Color active: #FFFFFF when next page exists
  Color disabled: #5A5040
```

---

## 11. KOMPONEN: AI ASSISTANT BAR (Fixed Bottom)

### 11.1 Container
```
Position:       fixed, bottom 0, left 220px
Width:          calc(100vw - 220px)
Height:         44px
Background:     #141000
Border-top:     1px solid #2E2800
Padding:        0 20px
Display:        flex, align-items center, justify-content space-between
Z-index:        90
```

### 11.2 Status Indicator
```
Dot:            6px, radius 50%, bg #4CAF50, animation pulse 2s
Label:          "SISTEM AKTIF", 11px/700, #4CAF50, letter-spacing 2px uppercase
```

### 11.3 AI Message
```
Text:           "Kecerdasan buatan siap membantu analisis log dan deteksi anomali"
Font-size:      12px / 400
Color:          #8A8070
```

---

## 12. INTERACTION STATES — TIMELINE ENTRY

### 12.1 Default State
```
Border:         1px solid #2E2800
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
```

### 12.2 Hover State
```
Border-color:   rgba(245,195,0,0.3)
Box-shadow:     0 4px 12px rgba(0,0,0,0.5)
Transition:     all 0.2s ease
Cursor:         pointer
```

### 12.3 Expanded State (click to expand)
```
Max-height:     none (teknikal detail expand)
Border-color:   rgba(245,195,0,0.5)
Add section:    "DETAIL LENGKAP" dengan semua field JSON
```

---

## 13. GRID RECAP — ZONA LAYOUT

| Zone                  | X Offset | Y Offset  | Width                    | Height    |
|-----------------------|----------|-----------|--------------------------|-----------|
| Sidebar               | 0        | 0         | 220px                    | 100vh     |
| Header Bar            | 220px    | 0         | calc(100vw - 220px)      | 56px      |
| Hero Section          | 220px    | 56px      | calc(100vw - 220px)      | ~130px    |
| Filter Bar            | 220px    | 186px     | calc(100vw - 220px)      | ~52px     |
| Log Timeline          | 220px    | 238px     | calc(100vw - 220px)      | scrollable|
| Pagination Footer     | 220px    | bottom    | calc(100vw - 220px)      | 48px      |
| AI Bar (fixed)        | 220px    | bottom: 0 | calc(100vw - 220px)      | 44px      |

---

## 14. CSS VARIABLES BLOCK (Copy-Paste Ready)

```css
/* ============================================================
   EGG GYM — Admin Audit Trail
   CSS Custom Properties — Design Tokens
   Generated: 2026-06-24
   ============================================================ */

:root {
  /* ── COLORS ── */
  --color-bg-primary:           #1A1500;
  --color-bg-card:              #252000;
  --color-bg-sidebar:           #141000;
  --color-bg-header:            #1E1900;
  --color-bg-filter-bar:        #1E1900;
  --color-bg-input:             #2A2400;
  --color-accent-primary:       #F5C300;
  --color-accent-hover:         #E0B000;
  --color-text-primary:         #FFFFFF;
  --color-text-secondary:       #8A8070;
  --color-text-muted:           #5A5040;
  --color-text-on-accent:       #1A1500;
  --color-status-success:       #4CAF50;
  --color-status-warning:       #F59E0B;
  --color-status-danger:        #EF4444;
  --color-status-info:          #3B82F6;
  --color-border-card:          #2E2800;
  --color-border-sidebar:       #2A2400;
  --color-timeline-line:        #2E2800;
  --color-timeline-dot-active:  #F5C300;
  --color-timeline-dot-inactive:#5A5040;
  --color-role-admin-bg:        rgba(245,195,0,0.15);
  --color-role-admin-text:      #F5C300;
  --color-role-trainer-bg:      rgba(59,130,246,0.15);
  --color-role-trainer-text:    #3B82F6;
  --color-role-system-bg:       rgba(239,68,68,0.15);
  --color-role-system-text:     #EF4444;
  --color-watermark:            rgba(245,195,0,0.04);
  --color-pagination-active:    #F5C300;

  /* ── TYPOGRAPHY ── */
  --font-family-primary:        "Inter", "Segoe UI", -apple-system, sans-serif;
  --font-family-mono:           "JetBrains Mono", "Fira Code", monospace;
  --text-hero-title:            36px;
  --text-hero-subtitle:         13px;
  --text-entry-action:          13px;
  --text-entry-meta:            11px;
  --text-badge-role:            9px;
  --text-filter-label:          11px;
  --text-breadcrumb-main:       18px;
  --text-pagination-num:        13px;

  /* ── SPACING ── */
  --space-xs:                   4px;
  --space-sm:                   8px;
  --space-md:                   12px;
  --space-base:                 16px;
  --space-lg:                   20px;
  --space-xl:                   24px;
  --space-hero-v:               28px;
  --space-2xl:                  32px;

  /* ── BORDER RADIUS ── */
  --radius-xs:                  4px;
  --radius-sm:                  6px;
  --radius-md:                  10px;
  --radius-full:                50%;

  /* ── SHADOWS ── */
  --shadow-card:                0 2px 8px rgba(0, 0, 0, 0.4);
  --shadow-hover:               0 6px 16px rgba(0, 0, 0, 0.5);
  --shadow-sidebar:             2px 0 8px rgba(0, 0, 0, 0.5);

  /* ── LAYOUT ── */
  --sidebar-width:              220px;
  --header-height:              56px;
  --hero-height:                130px;
  --filter-bar-height:          52px;
  --pagination-height:          48px;
  --ai-bar-height:              44px;
  --timeline-dot-size:          14px;
  --timeline-line-left:         39px;
  --page-padding:               20px;
}
```

---

## 15. ANIMASI & MICROINTERACTIONS

### 15.1 Timeline Entry Hover
```css
.log-entry-card {
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}
.log-entry-card:hover {
  border-color: rgba(245, 195, 0, 0.3);
  box-shadow: var(--shadow-hover);
  cursor: pointer;
}
```

### 15.2 Status Badge Pulse (untuk entri FAILED)
```css
@keyframes badge-pulse {
  0%, 100% { opacity: 1; }
  50%       { opacity: 0.6; }
}
.badge-danger {
  animation: badge-pulse 2s infinite;
}
```

### 15.3 Timeline Dot Glow (entri terbaru)
```css
@keyframes dot-glow {
  0%, 100% { box-shadow: 0 0 4px rgba(245,195,0,0.4); }
  50%       { box-shadow: 0 0 12px rgba(245,195,0,0.8); }
}
.timeline-dot-active {
  animation: dot-glow 2s ease-in-out infinite;
}
```

---

## 16. CATATAN AI — IMPLEMENTATION NOTES (15 poin)

1. **Immutable Log Design**: Entry di halaman Audit Trail TIDAK boleh bisa diedit atau dihapus oleh siapapun termasuk admin. Tombol edit/delete tidak boleh ada di halaman ini. Setiap entry adalah permanent record yang hanya bisa ditambah, bukan diubah.

2. **Timeline Connector Line**: Garis vertikal penghubung timeline menggunakan `position: absolute; left: 39px` dari tepi kiri container. Pastikan dots di-align ke garis ini dengan `margin-left: auto/manual` agar dot center tepat di atas garis.

3. **Role Badge Color Semantics**: Warna role badge bersifat semantik dan konsisten:
   - `ADMIN` = kuning (#F5C300) → aksi administratif
   - `TRAINER` = biru (#3B82F6) → aksi coach/PT
   - `SYSTEM` = merah (#EF4444) → event otomatis/security
   - `MEMBER` = hijau (#4CAF50) → aksi self-service member

4. **Watermark Text "LOGS"**: Gunakan CSS `user-select: none; pointer-events: none; position: absolute` agar watermark tidak interfere dengan interaksi user dan tidak bisa diselect/copied.

5. **Real-time vs Paginated**: Halaman ini ideal menggunakan pendekatan hybrid: 10 entry terbaru di-stream via WebSocket real-time, entry lama diambil via paginated REST API. Implement dengan Intersection Observer untuk lazy-load saat scroll ke bawah.

6. **Filter Tab + Timeline Sync**: Saat user klik filter "ADMIN", timeline harus filter hanya entry dengan role badge ADMIN. Filter tidak reload halaman — gunakan client-side filter dengan data preloaded atau query-param-based filter yang update URL tanpa full reload.

7. **IP Address Display**: IP address ditampilkan dalam monospace font untuk readability. Pada mobile/tablet view, IP address bisa di-truncate atau dipindah ke expanded state untuk menghemat horizontal space.

8. **Timestamp Format**: Tampilkan dalam dua format sekaligus: relative time ("2 minutes ago") untuk entri < 24 jam, dan absolute ("Oct 12, 2023 · 14:32 WIB") untuk entri lebih tua. Gunakan `title` attribute untuk menampilkan absolute time saat hover pada relative timestamp.

9. **Export Functionality**: Tombol "EXPORT" membuka dropdown dengan pilihan:
   - Export as CSV (semua field)
   - Export as PDF (formatted report)
   - Export as JSON (raw data)
   Setiap export harus disertai filter yang sedang aktif — jika filter "TRAINER" aktif, export hanya data trainer.

10. **Search dalam Log**: Search bar di filter bar melakukan full-text search pada: nama user, action text, IP address, module name, status badge text. Highlight matching text menggunakan `<mark>` element dengan `background: rgba(245,195,0,0.2)`.

11. **Pagination State Management**: Maintain pagination state di URL query params (`?page=2&filter=ADMIN&q=Adrian`) agar URL shareable dan browser back/forward bekerja dengan benar tanpa kehilangan posisi.

12. **Entry Detail Expansion**: Click pada entry card expand-nya untuk menampilkan detail lengkap:
    - Full JSON payload yang dicatat
    - Browser/device info
    - Session ID
    - Delta changes (jika ini adalah update operation: before → after)
    Use CSS `max-height` transition untuk smooth expand animation (max-height: 0 → max-height: 500px).

13. **Security Alert Entry Styling**: Entry dengan role SYSTEM + status FAILED mendapatkan styling khusus:
    - Left border: 3px solid #EF4444
    - Subtle red background tint: rgba(239,68,68,0.03)
    - Status badge animated pulse
    Ini membantu admin identify security incidents secara visual dalam daftar log yang panjang.

14. **Pagination Accessibility**: Tombol pagination harus memiliki:
    - `aria-label="Go to page [N]"`
    - `aria-current="page"` pada halaman aktif
    - Keyboard navigable dengan Tab + Enter
    - Focus ring: `outline: 2px solid #F5C300; outline-offset: 2px`

15. **Log Retention & Archiving**: Tampilkan banner subtle di atas timeline jika ada log > 90 hari yang akan diarsipkan. Contoh: "⚠ Log sebelum 24 Jul 2023 akan diarsipkan dalam 7 hari. [Unduh Arsip]" — banner background rgba(245,195,0,0.08), border rgba(245,195,0,0.2), teks #F5C300.

---

*Spec ini generated dari analisis visual screen Admin Audit Trail.png*
*Design system reference: ADMIN_DASHBOARD_UI_SPEC.md*
*Total sections: 16 | Detail level: ⭐⭐⭐⭐⭐ Full Detail*

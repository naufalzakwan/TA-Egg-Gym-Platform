# ADMIN_SYSTEM_SETTINGS_UI_SPEC.md
# Egg Gym App — Admin System Settings Screen
# UI Specification for VSCode AI / Cursor / Copilot
# Screen: Admin > Pengaturan > System Settings
# Resolution: ~1060 × 1080 px
# Last Updated: 2026-06-25

---

## 1. DESIGN TOKENS — COLOR PALETTE

| Token Name                    | HEX Value              | Usage                                                       |
|-------------------------------|------------------------|-------------------------------------------------------------|
| --color-bg-primary            | #1A1500                | Main content background                                     |
| --color-bg-card               | #252000                | Form panel, payment gateway panel backgrounds               |
| --color-bg-sidebar            | #141000                | Sidebar background                                          |
| --color-bg-header             | #1A1500                | Top header (tidak ada border bawah, menyatu dg bg)          |
| --color-bg-input              | #1E1900                | Input field background (lebih gelap dari card)              |
| --color-bg-input-border       | #352E00                | Input field border default                                  |
| --color-bg-gateway-item       | #1E1900                | Payment gateway row item background                         |
| --color-bg-gateway-icon       | #2A2400                | Gateway icon container background                           |
| --color-bg-sidebar-admin      | #1E1900                | Admin Access card background (kanan atas)                   |
| --color-bg-metric             | #252000                | Metric Summary card background                              |
| --color-bg-promo              | #1A1500                | Promo / upgrade card background (foto gelap)                |
| --color-accent-primary        | #F5C300                | Active step, CTA button, active nav, section icons          |
| --color-accent-hover          | #E0B000                | Button hover                                                |
| --color-text-primary          | #FFFFFF                | Page title, card titles, input values, metric number        |
| --color-text-secondary        | #8A8070                | Body description, step labels inactive, input labels        |
| --color-text-muted            | #5A5040                | Placeholder, timestamps, subtle helper text                 |
| --color-text-on-accent        | #1A1500                | Text on yellow button (SIMPAN PENGATURAN)                   |
| --color-text-brand-right      | #F5C300                | "Editorial Athletics" text di kanan header                  |
| --color-border-card           | #352E00                | Card & panel borders                                        |
| --color-border-input          | #352E00                | Input field borders                                         |
| --color-border-input-focus    | #F5C300                | Input border on focus state                                 |
| --color-border-sidebar        | #2A2400                | Sidebar dividers                                            |
| --color-status-active         | #4CAF50                | "ACTIVE" badge (QRIS) background                           |
| --color-status-active-text    | #FFFFFF                | "ACTIVE" badge text                                        |
| --color-status-pending        | #F59E0B                | "PENDING SETUP" badge background                           |
| --color-status-pending-text   | #1A1500                | "PENDING SETUP" badge text                                 |
| --color-btn-configure         | #F5C300                | "CONFIGURE" / "ACTIVATE" button background                 |
| --color-btn-configure-text    | #1A1500                | "CONFIGURE" / "ACTIVATE" button text                       |
| --color-btn-password          | #F5C300                | "UBAH PASSWORD" button background                          |
| --color-btn-password-text     | #1A1500                | "UBAH PASSWORD" button text                                |
| --color-icon-shield           | #4CAF50                | Shield/check icon (2FA Enabled)                            |
| --color-icon-section          | #F5C300                | Section title icons (Identity, Payment, Admin Access)       |
| --color-step-active           | #F5C300                | Active step label & underline                              |
| --color-step-inactive         | #5A5040                | Inactive step labels                                       |
| --color-metric-bar-active     | #F5C300                | Metric bar chart fill active bars                          |
| --color-metric-bar-inactive   | #3A3300                | Metric bar chart fill inactive bars                        |
| --color-promo-label           | #F5C300                | "NEXT EVOLUTION" promo label                               |
| --color-storage-bar-fill      | #F5C300                | Storage usage bar fill (42.8 GB used)                      |
| --color-storage-bar-track     | #3A3300                | Storage usage bar background                               |
| --color-overlay-dark          | rgba(0,0,0,0.7)        | Modal backdrop / promo card overlay                        |

---

## 2. TIPOGRAFI

### Font Family
```
Primary:    "Inter", "Segoe UI", -apple-system, BlinkMacSystemFont, sans-serif
Monospace:  "JetBrains Mono", "Fira Code", monospace  (email, phone number input)
```

### Skala Tipografi Lengkap
| Token                        | Size | Weight | Line-H | Letter-Sp       | Usage                                         |
|------------------------------|------|--------|--------|-----------------|-----------------------------------------------|
| --text-page-title            | 36px | 900    | 1.0    | -1px            | "SYSTEM SETTINGS" mega title                  |
| --text-page-desc             | 14px | 400    | 1.5    | 0px             | Subtitle desc di bawah SYSTEM SETTINGS        |
| --text-step-number           | 11px | 700    | 1.0    | 1.5px uppercase | "STEP 01", "STEP 02", "STEP 03"               |
| --text-step-label-active     | 15px | 700    | 1.2    | 0px             | "Profile Gym" (step aktif)                    |
| --text-step-label-inactive   | 14px | 400    | 1.2    | 0px             | "Integrasi Pembayaran", "Akun Admin"           |
| --text-card-title            | 18px | 700    | 1.2    | 0px             | "Identity & Location", "Payment Gateways"     |
| --text-input-label           | 10px | 700    | 1.2    | 1.5px uppercase | "NAMA GYM / BRAND", "KONTAK EMAIL", dst       |
| --text-input-value           | 14px | 400    | 1.4    | 0px             | Nilai dalam input field                       |
| --text-gateway-name          | 15px | 700    | 1.2    | 0px             | "QRIS Dynamic Integration", "Virtual Account" |
| --text-gateway-sub           | 10px | 600    | 1.2    | 1px uppercase   | "POWERED BY MIDTRANS", "BCA, MANDIRI, BNI, BRI"|
| --text-badge-status          | 10px | 700    | 1.0    | 1px uppercase   | "ACTIVE", "PENDING SETUP"                    |
| --text-btn-action            | 11px | 700    | 1.0    | 1px uppercase   | "CONFIGURE", "ACTIVATE"                      |
| --text-btn-cta               | 14px | 700    | 1.0    | 1.5px uppercase | "SIMPAN PENGATURAN"                           |
| --text-admin-card-title      | 16px | 700    | 1.2    | 0px             | "Admin Access"                               |
| --text-admin-input-label     | 10px | 600    | 1.2    | 1.5px uppercase | "CURRENT USER", "SECURITY LEVEL"             |
| --text-admin-input-value     | 14px | 500    | 1.4    | 0px             | "alex.mercer@editorial.com", "2-Factor Auth Enabled" |
| --text-btn-password          | 13px | 700    | 1.0    | 1px uppercase   | "UBAH PASSWORD"                              |
| --text-metric-label          | 10px | 700    | 1.2    | 1.5px uppercase | "METRIC SUMMARY", "UPTIME STATUS"            |
| --text-metric-number         | 32px | 800    | 1.0    | -0.5px          | "99.9"                                       |
| --text-metric-unit           | 18px | 700    | 1.0    | 0px             | "%" (superscript setelah 99.9)               |
| --text-storage-label         | 12px | 400    | 1.3    | 0px             | "Storage Usage"                              |
| --text-storage-value         | 12px | 600    | 1.3    | 0px             | "42.8 GB / 100 GB"                           |
| --text-promo-label           | 10px | 700    | 1.2    | 2px uppercase   | "NEXT EVOLUTION"                             |
| --text-promo-title           | 16px | 900    | 1.2    | 0.5px uppercase | "UPGRADE TO MULTI-CLUB ARCHITECTURE"         |
| --text-nav-item              | 13px | 500    | 1.4    | 0px             | Sidebar nav items                            |
| --text-nav-active            | 13px | 700    | 1.4    | 0px             | "PENGATURAN" — active nav item               |
| --text-sidebar-brand         | 14px | 700    | 1.2    | 0px             | "Editorial Athletics" (sidebar)              |
| --text-sidebar-subbrand      | 10px | 500    | 1.2    | 1px uppercase   | "ELITE MANAGEMENT"                           |
| --text-header-brand-right    | 16px | 700    | 1.2    | 0px             | "Editorial Athletics" (header kanan)         |
| --text-profile-name          | 13px | 600    | 1.3    | 0px             | "Alex Mercer"                                |
| --text-profile-role          | 10px | 500    | 1.2    | 1px uppercase   | "MASTER ADMIN"                               |

---

## 3. SPACING & LAYOUT

### Spacing Scale (Base 8px)
| Token          | Value | Usage                                                        |
|----------------|-------|--------------------------------------------------------------|
| --space-xs     | 4px   | Badge padding vertical, dot gap                             |
| --space-sm     | 8px   | Input label-to-field gap, badge padding horizontal          |
| --space-md     | 12px  | Gateway row item inner padding vertical                     |
| --space-base   | 16px  | Card inner padding, input padding horizontal                |
| --space-lg     | 20px  | Gap between cards, step-to-form gap                        |
| --space-xl     | 24px  | Card padding all sides                                      |
| --space-2xl    | 32px  | Page title-to-stepper gap                                   |
| --space-3xl    | 48px  | Section title gap (SYSTEM SETTINGS to stepper)             |

### Border Radius
| Token          | Value | Usage                                                        |
|----------------|-------|--------------------------------------------------------------|
| --radius-xs    | 4px   | Status badges (ACTIVE, PENDING SETUP)                       |
| --radius-sm    | 6px   | Action buttons (CONFIGURE, ACTIVATE), input fields          |
| --radius-md    | 10px  | Gateway row items, Admin Access sub-fields                  |
| --radius-lg    | 14px  | Main form panels (Identity, Payment Gateways)               |
| --radius-xl    | 16px  | Admin Access card, Metric Summary card, Promo card          |
| --radius-full  | 50%   | Avatar circles, shield icon container                       |
| --radius-btn   | 8px   | "SIMPAN PENGATURAN" CTA button                              |
| --radius-btn-pw| 8px   | "UBAH PASSWORD" button                                      |

### Box Shadows
| Token              | Value                              | Usage                                |
|--------------------|------------------------------------|--------------------------------------|
| --shadow-card      | 0 2px 8px rgba(0,0,0,0.4)         | Main form panels default             |
| --shadow-hover     | 0 8px 20px rgba(0,0,0,0.6)        | Card hover state                     |
| --shadow-btn-cta   | 0 4px 16px rgba(245,195,0,0.35)   | "SIMPAN PENGATURAN" button           |
| --shadow-btn-pw    | 0 2px 8px rgba(245,195,0,0.2)     | "UBAH PASSWORD" button               |
| --shadow-sidebar   | 2px 0 8px rgba(0,0,0,0.5)         | Sidebar right edge                   |
| --shadow-input-focus | 0 0 0 3px rgba(245,195,0,0.15)  | Input field focus ring               |

---

## 4. LAYOUT UTAMA

### Dimensi Global
```
Total Canvas:     ~1060 × 1080 px
Sidebar:          200px wide × 100vh (fixed)
Header Bar:       calc(100vw - 200px) × 56px
Main Content:     calc(100vw - 200px), padding: 24px
Content Gap:      20px
Left Column:      ~57% content width (form panels)
Right Column:     ~38% content width (Admin Access, Metric, Promo)
Right Column Gap: 16px
```

### ASCII Layout Diagram
```
┌──────────────────────┬─────────────────────────────────────────────────────────┐
│  SIDEBAR (200px)     │  HEADER (56px)                                          │
│  ────────────────    │  [🔍 Cari pengaturan...]         🔔  ❓  Editorial Athletics│
│  ◈ Editorial         ├─────────────────────────────────────────────────────────┤
│    Athletics         │                                                          │
│    ELITE MGMT        │  SYSTEM SETTINGS                    [faded "GYM" bg]    │
│  ────────────────    │  Configure your gym's core infrastructure...             │
│  ⊞ Dashboard         │                                                          │
│  👥 Member           │  STEP 01           STEP 02              STEP 03          │
│  📅 Paket Membership │  Profile Gym ▼     Integrasi Pembayaran  Akun Admin      │
│  ⭐ Personal Trainer  │  ─────────────                                           │
│  📋 Booking & Sesi   │  ┌─────────────────────────────┐  ┌───────────────────┐  │
│  💰 Pembayaran       │  │ 🏢 Identity & Location       │  │ 🔐 Admin Access   │  │
│  🏋 Alat Gym         │  │ NAMA GYM / BRAND             │  │                   │  │
│  🔍 Audit Trail      │  │ [Editorial Athletics - Elite] │  │ CURRENT USER      │  │
│  📊 Laporan          │  │ ALAMAT LENGKAP               │  │ [alex.mercer@ ✏️] │  │
│  ⚙  Pengaturan ◄AKTIF│  │ [Jl. Prestise No.88, SCBD..] │  │ SECURITY LEVEL    │  │
│  ────────────────    │  │ KONTAK EMAIL  | PHONE NUMBER  │  │ [2-Factor Auth 🛡] │  │
│  [👤] Alex Mercer    │  │ [ops@edit..] | [+62 21 555..] │  │                   │  │
│       MASTER ADMIN   │  └─────────────────────────────┘  │ [UBAH PASSWORD]   │  │
│                      │                                    └───────────────────┘  │
│                      │  ┌─────────────────────────────┐  ┌───────────────────┐  │
│                      │  │ 💳 Payment Gateways          │  │ METRIC SUMMARY    │  │
│                      │  │ ┌─────────────────────────┐ │  │ 99.9%  📊bar chart│  │
│                      │  │ │[Q] QRIS Dynamic  ACTIVE  │ │  │ UPTIME STATUS     │  │
│                      │  │ │    CONFIGURE             │ │  │ ─────────────     │  │
│                      │  │ └─────────────────────────┘ │  │ Storage Usage     │  │
│                      │  │ ┌─────────────────────────┐ │  │ 42.8 GB / 100 GB  │  │
│                      │  │ │[🏛] Virtual Account(VA)  │ │  └───────────────────┘  │
│                      │  │ │    PENDING SETUP ACTIVATE│ │  ┌───────────────────┐  │
│                      │  │ └─────────────────────────┘ │  │ [foto gym gelap]  │  │
│                      │  └─────────────────────────────┘  │ NEXT EVOLUTION    │  │
│                      │                                    │ UPGRADE TO        │  │
│                      │       [  SIMPAN PENGATURAN  🖫 ]   │ MULTI-CLUB...     │  │
│                      │                                    └───────────────────┘  │
└──────────────────────┴─────────────────────────────────────────────────────────┘
```

---

## 5. KOMPONEN: SIDEBAR

### 5.1 Container
```
Width:          200px
Height:         100vh
Background:     #141000
Border-right:   1px solid #2A2400
Box-shadow:     2px 0 8px rgba(0,0,0,0.5)
Position:       fixed, left: 0, top: 0
Z-index:        200
Display:        flex flex-column
```

### 5.2 Area Brand
```
Padding:        16px 16px 14px
Border-bottom:  1px solid #2A2400

Logo Icon:
  Width/Height: 28px
  Fill:         #F5C300

Brand Name:
  Text:         "Editorial Athletics"
  Font-size:    14px
  Font-weight:  700
  Color:        #FFFFFF

Sub-brand:
  Text:         "ELITE MANAGEMENT"
  Font-size:    10px
  Color:        #8A8070
  Letter-spacing:1px
  Text-transform:uppercase
```

### 5.3 Navigation Items (Urutan)
```
1.  ⊞  Dashboard
2.  👥  Member
3.  📅  Paket Membership
4.  ⭐  Personal Trainer
5.  📋  Booking & Sesi PT
6.  💰  Pembayaran
7.  🏋  Alat Gym
8.  🔍  Audit Trail
9.  📊  Laporan
10. ⚙   Pengaturan     ← ACTIVE
```

### 5.4 Menu Item Active (Pengaturan)
```
Background:     #252000
Border-left:    3px solid #F5C300
Padding-left:   13px
Icon:           ⚙ gear, color #F5C300
Text:           "PENGATURAN"
Font-size:      13px
Font-weight:    700
Color:          #F5C300
```

### 5.5 Profile Area (Bottom)
```
Padding:        12px 16px
Border-top:     1px solid #2A2400

Avatar:
  Width/Height: 36px
  Border-radius:50%
  Object-fit:   cover (illustrated portrait)

Name:
  Text:         "Alex Mercer"
  Font-size:    13px
  Font-weight:  600
  Color:        #FFFFFF

Role:
  Text:         "MASTER ADMIN"
  Font-size:    10px
  Color:        #8A8070
  Letter-spacing:1px
  Text-transform:uppercase
```

---

## 6. KOMPONEN: TOP HEADER BAR

### 6.1 Container
```
Height:         56px
Background:     #1A1500
Border-bottom:  1px solid #2A2400
Padding:        0 24px
Display:        flex, align-items center, justify-content space-between
Position:       sticky, top: 0
Z-index:        100
Width:          calc(100vw - 200px)
```

### 6.2 Kiri — Search Bar (posisi kiri, bukan center)
```
Container:
  Width:        320px
  Height:       34px
  Background:   #252000
  Border:       1px solid #352E00
  Border-radius:6px
  Padding:      0 12px
  Display:      flex, align-items center, gap 8px

Search Icon:
  Width:        14px
  Color:        #5A5040

Input:
  Placeholder:  "Cari pengaturan..."
  Font-size:    13px
  Color:        #FFFFFF
  Placeholder-color: #5A5040
  Background:   transparent
  Border:       none

  Focus state:
    Border (parent): 1px solid #F5C300
    Box-shadow (parent): 0 0 0 3px rgba(245,195,0,0.1)
```

### 6.3 Kanan — Icons + Brand Name
```
Display:        flex, align-items center, gap 16px

Notification Bell:
  Icon-size:    20px
  Color:        #8A8070
  Hover-color:  #F5C300

Help / Question:
  Icon-size:    20px
  Color:        #8A8070
  Hover-color:  #F5C300

Brand Text:
  Text:         "Editorial Athletics"
  Font-size:    16px
  Font-weight:  700
  Color:        #F5C300
  (Catatan: screen ini tidak tampilkan avatar di header kanan,
   melainkan brand name teks kuning)
```

---

## 7. KOMPONEN: PAGE HEADER

### 7.1 Area Judul
```
Position:       relative
Margin-bottom:  24px

Background Watermark:
  Text:         "GYM" (atau "SYSTEM")
  Font-size:    ~120px
  Font-weight:  900
  Color:        rgba(245,195,0,0.05)
  Position:     absolute, right: 0, top: -20px
  Z-index:      0
  User-select:  none
  Pointer-events:none

Page Title:
  Text:         "SYSTEM SETTINGS"
  Font-size:    36px
  Font-weight:  900
  Color:        #FFFFFF
  Letter-spacing:-1px
  Text-transform:uppercase
  Position:     relative, z-index: 1

Description:
  Text:         "Configure your gym's core infrastructure, payment gateways, and administrative access levels."
  Font-size:    14px
  Font-weight:  400
  Color:        #8A8070
  Max-width:    520px
  Line-height:  1.5
  Margin-top:   8px
```

---

## 8. KOMPONEN: STEP INDICATOR (WIZARD NAVIGATION)

### 8.1 Container
```
Display:        flex, flex-direction row
Gap:            40px
Margin-bottom:  24px
Border-bottom:  1px solid #352E00
Padding-bottom: 0
```

### 8.2 Step Item — Active (Step 01: Profile Gym)
```
Display:        flex, flex-direction column, gap 4px
Cursor:         pointer

Step Number:
  Text:         "STEP 01"
  Font-size:    11px
  Font-weight:  700
  Color:        #F5C300
  Letter-spacing:1.5px
  Text-transform:uppercase

Step Label:
  Text:         "Profile Gym"
  Font-size:    15px
  Font-weight:  700
  Color:        #FFFFFF

Underline:
  Height:       2px
  Background:   #F5C300
  Width:        100%
  Margin-top:   8px
  Border-radius:1px
```

### 8.3 Step Item — Inactive (Step 02, Step 03)
```
Step Number:
  Color:        #5A5040

Step Label:
  Font-size:    14px
  Font-weight:  400
  Color:        #5A5040

Underline:      none (tidak ada)

Hover state:
  Step Label color: #8A8070
  Cursor: pointer
```

### 8.4 Data Steps
```
Step 01: "STEP 01"  →  "Profile Gym"          ← ACTIVE
Step 02: "STEP 02"  →  "Integrasi Pembayaran"
Step 03: "STEP 03"  →  "Akun Admin"
```

---

## 9. KOMPONEN: FORM PANEL — IDENTITY & LOCATION

### 9.1 Container
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  14px
Padding:        24px
Margin-bottom:  20px
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
```

### 9.2 Panel Header
```
Display:        flex, align-items center, gap 12px
Margin-bottom:  20px

Section Icon:
  Icon:         🏢 / grid / building icon
  Width:        28px
  Height:       28px
  Color:        #F5C300
  Background:   rgba(245,195,0,0.1)
  Border-radius:6px
  Padding:      6px

Title:
  Text:         "Identity & Location"
  Font-size:    18px
  Font-weight:  700
  Color:        #FFFFFF
```

### 9.3 Input Field — Full Width
```
Container:
  Margin-bottom:16px

Label:
  Font-size:    10px
  Font-weight:  700
  Color:        #8A8070
  Letter-spacing:1.5px
  Text-transform:uppercase
  Margin-bottom:6px

Input:
  Width:        100%
  Height:       44px
  Background:   #1E1900
  Border:       1px solid #352E00
  Border-radius:6px
  Padding:      0 14px
  Font-size:    14px
  Font-weight:  400
  Color:        #FFFFFF

  Focus state:
    Border-color: #F5C300
    Box-shadow:  0 0 0 3px rgba(245,195,0,0.15)
    Outline:     none

  Placeholder:  --color-text-muted (#5A5040)
```

### 9.4 Textarea — Alamat Lengkap
```
Width:          100%
Min-height:     72px
Background:     #1E1900
Border:         1px solid #352E00
Border-radius:  6px
Padding:        10px 14px
Font-size:      14px
Font-weight:    400
Color:          #FFFFFF
Resize:         vertical
Line-height:    1.5
Margin-bottom:  16px

Focus state:    sama dengan input field
```

### 9.5 Input Row — 2 Kolom (Kontak Email & Phone)
```
Display:        grid
Grid-template-columns: 1fr 1fr
Gap:            16px

Masing-masing kolom: input full-width seperti 9.3
```

### 9.6 Data Form (Pre-filled)
```
NAMA GYM / BRAND:     "Editorial Athletics - Elite Club"
ALAMAT LENGKAP:       "Jl. Prestise No. 88, SCBD District, Jakarta Selatan, 12190"
KONTAK EMAIL:         "ops@editorialathletics.com"
PHONE NUMBER:         "+62 21 555 0192"
```

---

## 10. KOMPONEN: FORM PANEL — PAYMENT GATEWAYS

### 10.1 Container
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  14px
Padding:        24px
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
Position:       relative
```

### 10.2 Panel Header
```
Display:        flex, align-items center, gap 12px
Margin-bottom:  20px

Section Icon:
  Icon:         💳 / payment terminal icon
  Width:        28px
  Height:       28px
  Color:        #F5C300
  Background:   rgba(245,195,0,0.1)
  Border-radius:6px

Title:
  Text:         "Payment Gateways"
  Font-size:    18px
  Font-weight:  700
  Color:        #FFFFFF

Decorative Watermark (kanan):
  Icon:         besar payment/coin icon (abstract)
  Opacity:      0.06
  Position:     absolute, right: 16px, top: 16px
  Width:        80px
  Color:        #F5C300
  Pointer-events:none
```

### 10.3 Gateway Row Item
```
Display:        flex, align-items center, gap 14px
Background:     #1E1900
Border:         1px solid #352E00
Border-radius:  10px
Padding:        14px 16px
Margin-bottom:  12px
Last-child:     margin-bottom 0

Hover state:
  Border-color: #F5C300
  Transition:   0.2s
```

### 10.4 Gateway Icon Container
```
Width:          48px
Height:         48px
Background:     #2A2400
Border:         1px solid #352E00
Border-radius:  8px
Display:        flex center
Flex-shrink:    0

Icon:
  Width:        24px
  Height:       24px
  Color:        #F5C300
  (QRIS: scan/QR icon; Virtual Account: bank building icon)
```

### 10.5 Gateway Info
```
Flex: 1

Name:
  Font-size:    15px
  Font-weight:  700
  Color:        #FFFFFF

Sub-name:
  Font-size:    10px
  Font-weight:  600
  Color:        #8A8070
  Letter-spacing:1px
  Text-transform:uppercase
  Margin-top:   3px
```

### 10.6 Gateway Actions (kanan row)
```
Display:        flex, align-items center, gap 8px
```

### 10.7 Status Badge
```
ACTIVE badge:
  Background:   #4CAF50
  Color:        #FFFFFF
  Font-size:    10px
  Font-weight:  700
  Padding:      4px 8px
  Border-radius:4px
  Letter-spacing:1px
  Text-transform:uppercase

PENDING SETUP badge:
  Background:   #F59E0B
  Color:        #1A1500
  Font-size:    10px
  Font-weight:  700
  Padding:      4px 8px
  Border-radius:4px
  Letter-spacing:1px
  Text-transform:uppercase
```

### 10.8 Action Button (CONFIGURE / ACTIVATE)
```
Background:     #F5C300
Color:          #1A1500
Font-size:      11px
Font-weight:    700
Padding:        6px 12px
Border-radius:  6px
Border:         none
Letter-spacing: 1px
Text-transform: uppercase
Cursor:         pointer

Hover state:
  Background:   #E0B000
  Box-shadow:   0 2px 8px rgba(245,195,0,0.3)
```

### 10.9 Data Gateway
```
Gateway 1:
  Icon:         QR/scan icon
  Name:         "QRIS Dynamic Integration"
  Sub:          "POWERED BY MIDTRANS"
  Status:       ACTIVE
  Action:       "CONFIGURE"

Gateway 2:
  Icon:         bank building icon
  Name:         "Virtual Account (VA)"
  Sub:          "BCA, MANDIRI, BNI, BRI"
  Status:       PENDING SETUP
  Action:       "ACTIVATE"
```

---

## 11. KOMPONEN: ADMIN ACCESS CARD (KANAN ATAS)

### 11.1 Container
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  16px
Padding:        20px
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
Margin-bottom:  16px
```

### 11.2 Card Header
```
Display:        flex, align-items center, gap 10px
Margin-bottom:  16px

Icon:
  🔐 / shield-lock icon
  Width:        22px
  Color:        #F5C300

Title:
  Text:         "Admin Access"
  Font-size:    16px
  Font-weight:  700
  Color:        #FFFFFF
```

### 11.3 Info Field (Current User & Security Level)
```
Container:
  Background:   #1E1900
  Border:       1px solid #352E00
  Border-radius:8px
  Padding:      10px 14px
  Margin-bottom:10px

Label:
  Font-size:    10px
  Font-weight:  600
  Color:        #8A8070
  Letter-spacing:1.5px
  Text-transform:uppercase
  Margin-bottom:4px

Value + Icon Row:
  Display:      flex, justify-content space-between, align-items center

Value:
  Font-size:    14px
  Font-weight:  500
  Color:        #FFFFFF
```

### 11.4 Current User Field
```
Label:          "CURRENT USER"
Value:          "alex.mercer@editorial.com"

Edit Icon (kanan):
  Icon:         ✏️ pencil
  Width:        14px
  Color:        #8A8070
  Cursor:       pointer
  Hover-color:  #F5C300
```

### 11.5 Security Level Field
```
Label:          "SECURITY LEVEL"
Value:          "2-Factor Auth Enabled"

Shield Icon (kanan):
  Icon:         🛡 shield-check
  Width:        18px
  Color:        #4CAF50  (hijau = aman/aktif)
```

### 11.6 UBAH PASSWORD Button
```
Display:        block
Width:          100%
Padding:        12px
Background:     #F5C300
Color:          #1A1500
Font-size:      13px
Font-weight:    700
Letter-spacing: 1px
Text-transform: uppercase
Border-radius:  8px
Border:         none
Cursor:         pointer
Text-align:     center
Margin-top:     4px

Hover state:
  Background:   #E0B000
  Box-shadow:   0 4px 12px rgba(245,195,0,0.3)
```

---

## 12. KOMPONEN: METRIC SUMMARY CARD

### 12.1 Container
```
Background:     #252000
Border:         1px solid #352E00
Border-radius:  16px
Padding:        20px
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
Margin-bottom:  16px
```

### 12.2 Card Label
```
Text:           "METRIC SUMMARY"
Font-size:      10px
Font-weight:    700
Color:          #8A8070
Letter-spacing: 2px
Text-transform: uppercase
Margin-bottom:  12px
```

### 12.3 Uptime Display
```
Display:        flex, align-items flex-end, justify-content space-between

Left — Uptime Number:
  Number:       "99.9"
  Font-size:    32px
  Font-weight:  800
  Color:        #FFFFFF

  Unit:
    Text:       "%"
    Font-size:  18px
    Font-weight:700
    Color:      #FFFFFF
    Vertical-align:super (superscript style)

  Sub-label:
    Text:       "UPTIME STATUS"
    Font-size:  10px
    Font-weight:600
    Color:      #8A8070
    Letter-spacing:1.5px
    Text-transform:uppercase
    Margin-top: 4px

Right — Mini Bar Chart:
  Display:      flex, align-items flex-end, gap 3px
  Height:       36px

  Bar (5 bars):
    Width:      8px
    Border-radius:2px top
    Background varies:
      Bars 1-3: #F5C300 (aktif/tinggi)
      Bar 4:    #F5C300 (sedikit lebih pendek)
      Bar 5:    #F5C300 (paling pendek kanan)
    (All bars visible/active — menunjukkan uptime tinggi konsisten)
```

### 12.4 Divider
```
Height:         1px
Background:     #352E00
Margin:         16px 0
```

### 12.5 Storage Usage Row
```
Display:        flex, justify-content space-between, align-items center
Margin-bottom:  8px

Label:
  Text:         "Storage Usage"
  Font-size:    12px
  Color:        #8A8070

Value:
  Text:         "42.8 GB / 100 GB"
  Font-size:    12px
  Font-weight:  600
  Color:        #FFFFFF
```

### 12.6 Storage Progress Bar
```
Height:         6px
Background:     #3A3300  (track)
Border-radius:  3px

Fill:
  Width:        ~43%  (42.8/100)
  Background:   #F5C300
  Border-radius:3px
```

---

## 13. KOMPONEN: PROMO / UPGRADE CARD

### 13.1 Container
```
Position:       relative
Border-radius:  16px
Overflow:       hidden
Min-height:     140px
Box-shadow:     0 2px 8px rgba(0,0,0,0.4)
```

### 13.2 Background Photo
```
Position:       absolute, inset 0
Width:          100%
Height:         100%
Object-fit:     cover
Filter:         brightness(0.35)
Z-index:        0
Content:        [foto interior gym / industrial style, dark tone]
```

### 13.3 Content Overlay
```
Position:       relative, z-index: 1
Padding:        20px

Label:
  Text:         "NEXT EVOLUTION"
  Font-size:    10px
  Font-weight:  700
  Color:        #F5C300
  Letter-spacing:2px
  Text-transform:uppercase
  Margin-bottom:8px

Title:
  Text:         "UPGRADE TO MULTI-CLUB ARCHITECTURE"
  Font-size:    16px
  Font-weight:  900
  Color:        #FFFFFF
  Text-transform:uppercase
  Letter-spacing:0.5px
  Line-height:  1.2
```

---

## 14. KOMPONEN: CTA BUTTON — SIMPAN PENGATURAN

### 14.1 Positioning
```
Display:        flex, justify-content center
Margin-top:     28px
```

### 14.2 Button Spec
```
Background:     #F5C300
Color:          #1A1500
Font-size:      14px
Font-weight:    700
Letter-spacing: 1.5px
Text-transform: uppercase
Padding:        14px 40px
Border-radius:  8px
Border:         none
Cursor:         pointer
Display:        flex, align-items center, gap 10px
Box-shadow:     0 4px 16px rgba(245,195,0,0.35)
Width:          fit-content
Min-width:      240px

Icon (kanan teks):
  Icon:         💾 / save/floppy disk icon
  Width:        18px
  Color:        #1A1500

Hover state:
  Background:   #E0B000
  Box-shadow:   0 6px 20px rgba(245,195,0,0.45)
  Transform:    translateY(-1px)

Active/pressed state:
  Transform:    translateY(0)
  Box-shadow:   0 2px 8px rgba(245,195,0,0.25)

Transition:     all 0.2s ease
```

---

## 15. STATES & INTERACTIONS

### 15.1 Step Navigation
```
Click step inactive → navigasi ke step tersebut:
  Active step underline slide animasi: width 0 → 100% (300ms ease)
  Form content fade-out → fade-in (200ms)
  Step label warna: #5A5040 → #FFFFFF
  Step number warna: #5A5040 → #F5C300
```

### 15.2 Input Fields
```
Default:        border #352E00
Focus:          border #F5C300, box-shadow 0 0 0 3px rgba(245,195,0,0.15)
Error:          border #EF4444, box-shadow 0 0 0 3px rgba(239,68,68,0.15)
Disabled:       opacity 0.5, cursor not-allowed
Transition:     border-color 0.15s, box-shadow 0.15s
```

### 15.3 Gateway Row Hover
```
Default:        border #352E00
Hover:          border #F5C300, transition 0.2s
```

### 15.4 SIMPAN PENGATURAN — Loading State
```
Saat klik:
  Button text → "MENYIMPAN..."
  Icon → spinner (rotate 360deg, 0.8s linear infinite)
  Background: #E0B000
  Pointer-events: none

Success state (setelah save):
  Icon → checkmark ✓
  Text → "TERSIMPAN!"
  Background: #4CAF50
  Durasi: 2000ms → kembali ke state normal
```

### 15.5 Edit Icon (Current User)
```
Default:        ✏️ icon, opacity 0.5
Hover di parent field: opacity 1, color #F5C300
Click: buka inline edit mode / modal edit email
```

### 15.6 UBAH PASSWORD
```
Click: buka modal / navigate ke halaman change password
Hover: background #E0B000, box-shadow
```

---

## 16. DATA MODEL

### 16.1 Gym Profile
```typescript
interface GymProfile {
  id: string;
  namaGym: string;               // "Editorial Athletics - Elite Club"
  alamatLengkap: string;         // "Jl. Prestise No. 88, SCBD District..."
  kontakEmail: string;           // "ops@editorialathletics.com"
  phoneNumber: string;           // "+62 21 555 0192"
  updatedAt: Date;
}
```

### 16.2 Payment Gateway
```typescript
type GatewayStatus = 'active' | 'pending_setup' | 'inactive' | 'error';

interface PaymentGateway {
  id: string;
  name: string;                  // "QRIS Dynamic Integration"
  provider: string;              // "POWERED BY MIDTRANS"
  type: 'qris' | 'virtual_account' | 'credit_card' | 'ewallet';
  bankList?: string[];           // ["BCA", "MANDIRI", "BNI", "BRI"]
  status: GatewayStatus;
  configuredAt?: Date;
}
```

### 16.3 Admin Access
```typescript
interface AdminAccess {
  currentUser: string;           // "alex.mercer@editorial.com"
  role: 'master_admin' | 'super_admin' | 'admin';
  twoFactorEnabled: boolean;     // true
  securityLevel: string;         // "2-Factor Auth Enabled"
  lastPasswordChange: Date;
}
```

### 16.4 System Metrics
```typescript
interface SystemMetrics {
  uptimePercent: number;         // 99.9
  uptimeTrend: number[];         // [95, 98, 99, 97, 99.9] (5 titik data chart)
  storageUsedGB: number;         // 42.8
  storageTotalGB: number;        // 100
  lastChecked: Date;
}
```

### 16.5 Settings Form State
```typescript
interface SettingsFormState {
  activeStep: 1 | 2 | 3;
  isDirty: boolean;              // true jika ada perubahan belum disimpan
  isSaving: boolean;
  savedAt?: Date;
  errors: Record<string, string>;
}
```

---

## 17. AKSESIBILITAS (A11Y)

```
1. Step Wizard:
   - role="tablist" untuk container steps
   - Tiap step: role="tab", aria-selected="true/false"
   - aria-controls="step-panel-1" (mengarah ke panel form)
   - Panel form: role="tabpanel", aria-labelledby="step-1-tab"

2. Form Inputs:
   - Tiap input: <label htmlFor="input-id"> yang terkoneksi
   - Textarea alamat: aria-label="Alamat Lengkap Gym"
   - Error state: aria-invalid="true", aria-describedby="error-msg-id"

3. Gateway Actions:
   - Button CONFIGURE: aria-label="Configure QRIS Dynamic Integration"
   - Button ACTIVATE: aria-label="Activate Virtual Account (VA)"
   - Status badge: role="status", aria-label="Status: Active"

4. Admin Access:
   - Edit icon: aria-label="Edit email admin", role="button", tabIndex=0
   - Shield icon: aria-label="2-Factor Authentication Active"

5. CTA Button:
   - Loading state: aria-busy="true", aria-label="Menyimpan pengaturan..."
   - Success state: aria-live="polite" announcement "Pengaturan berhasil disimpan"

6. Storage Progress Bar:
   - role="progressbar"
   - aria-valuenow="42.8"
   - aria-valuemin="0"
   - aria-valuemax="100"
   - aria-label="Storage usage: 42.8 GB dari 100 GB"

7. Color Contrast:
   - Teks putih di #252000 background: rasio ≥ 7:1 ✓
   - Teks #1A1500 di #F5C300 button: rasio ≥ 9:1 ✓
   - Teks #8A8070 di #252000: perlu dicek (mungkin < 4.5:1 untuk teks kecil)
```

---

## 18. CATATAN AI — IMPLEMENTATION NOTES (15 poin)

1. **Multi-Step Form (Wizard) State**: Gunakan state management (Zustand/Redux atau React Context) untuk mengelola `activeStep`, `isDirty`, dan form data lintas steps. Saat pindah step, validasi step aktif dulu sebelum allow navigasi ke step berikutnya. Tampilkan visual error inline jika validasi gagal.

2. **Search Bar Header "Cari pengaturan..."**: Ini adalah search khusus settings-scope, bukan global search. Implementasikan fuzzy search di sisi client (Fuse.js) yang mencocokkan query dengan label setting (contoh: "password" → highlight field Security Level). Highlightnya harus muncul dalam tampilan yang sedang aktif.

3. **Input Pre-fill dari API**: Saat halaman mount, fetch `/api/settings/gym-profile` dan populate semua input secara otomatis. Gunakan `react-hook-form` dengan `defaultValues` dari API response untuk manajemen form yang efisien.

4. **SIMPAN PENGATURAN — Partial Save per Section**: Pertimbangkan menyimpan data per section (bukan semua sekaligus) untuk UX yang lebih baik. Identity & Location disimpan ke `/api/settings/gym-profile`, Payment Gateways ke `/api/settings/payment`, Admin Access ke `/api/settings/admin`. Tombol SIMPAN di halaman ini menyimpan section yang aktif berdasarkan `activeStep`.

5. **Payment Gateway CONFIGURE Flow**: Klik CONFIGURE pada QRIS → buka drawer/modal dengan form konfigurasi API key Midtrans (merchant_id, client_key, server_key, environment: sandbox/production). Jangan tampilkan server_key dalam plaintext di UI — gunakan masked input `****` dengan toggle show/hide.

6. **Payment Gateway ACTIVATE Flow**: Klik ACTIVATE pada Virtual Account → buka stepper modal: (1) Pilih bank, (2) Input callback URL, (3) Verifikasi, (4) Aktif. Update status badge di row secara optimistic UI setelah step 4 sukses.

7. **Metric Summary Real-Time**: Uptime data (`99.9%`) dan mini bar chart di-fetch dari monitoring API (misal: UptimeRobot atau internal healthcheck endpoint). Polling setiap 30 detik. Bar chart menampilkan 5 data point terakhir. Bar height = `(value / 100) * maxBarHeight`.

8. **Storage Usage**: Storage data di-fetch dari API server stats. Progress bar fill width = `(storageUsedGB / storageTotalGB) * 100 + '%'`. Jika usage > 80%, ubah fill color ke `#F59E0B` (warning); jika > 95%, ubah ke `#EF4444` (danger) dengan animasi pulse.

9. **UBAH PASSWORD Modal**: Implementasikan sebagai modal dialog (bukan navigate away) dengan 3 field: Current Password, New Password, Confirm New Password. Validasi: minimum 8 karakter, minimal 1 huruf besar, 1 angka, 1 simbol. Tampilkan strength meter. Submit ke `/api/auth/change-password`.

10. **Watermark Background Text**: Teks "GYM" di belakang SYSTEM SETTINGS judul adalah elemen dekoratif CSS murni: `position: absolute; font-size: 120px; opacity: 0.04; right: 0; top: -20px; pointer-events: none; user-select: none; color: #F5C300; font-weight: 900`. Tidak perlu implementasi JS.

11. **Promo Card "UPGRADE TO MULTI-CLUB"**: Card ini adalah CTA untuk feature upsell. Simpan data promo di CMS (Contentful/Sanity) agar bisa diubah tanpa deploy ulang. Background foto di-lazy load. Klik card → navigate ke `/admin/upgrade` atau buka pricing modal.

12. **Edit Email Admin (✏️ icon)**: Klik edit icon pada field Current User → input field berubah dari read-only menjadi editable (inline edit pattern). Tampilkan tombol ✓ Save dan ✕ Cancel di kanan input. Submit → panggil `/api/admin/update-email` + kirim verification email ke alamat baru.

13. **2FA Status Display**: Field "2-Factor Auth Enabled" dengan shield icon hijau adalah read-only status display. Tambahkan tooltip saat hover shield icon: "2FA aktif via Authenticator App". Untuk manage 2FA, arahkan user ke Step 03 "Akun Admin" yang memiliki dedicated 2FA management section.

14. **Right Column Stack**: Tiga panel di kanan (Admin Access, Metric Summary, Promo) menggunakan `display: flex; flex-direction: column; gap: 16px`. Di tablet (≤ 1024px), right column collapse ke bawah left column. Di mobile (≤ 640px), semua panel stack full-width secara vertikal.

15. **Unsaved Changes Guard**: Saat user mencoba navigate away dari halaman settings dengan `isDirty = true`, tampilkan konfirmasi dialog: "Ada perubahan yang belum disimpan. Tinggalkan halaman ini?" Implementasikan via `beforeunload` event listener (web) atau `useBlocker` (React Router v6) / `router.beforeEach` (Next.js).

---

*Spec ini generated dari analisis visual screen Admin_System_Settings.png*
*Design system reference: ADMIN_EQUIPMENT_MANAGEMENT_UI_SPEC.md + ADMIN_DASHBOARD_OVERVIEW_UI_SPEC.md*
*Total sections: 18 | Detail level: ⭐⭐⭐⭐⭐ Full Detail*

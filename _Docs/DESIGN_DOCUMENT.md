# Habitra — UI / UX Tasarım Dokümanı
**Versiyon:** 1.0  
**Tarih:** Mart 2026  
**Platform:** Flutter (Android, iOS, Web)  
**Tema:** Material 3, Dark & Light Mode  

---

## 1. Renk Sistemi

### 1.1 Ana Renkler (Primary)
| Token | Hex | RGB | Kullanım Alanı |
|-------|-----|-----|----------------|
| `primary` | `#6C63FF` | 108, 99, 255 | Butonlar, seçili tab/nav, FAB, linkler, badge'ler |
| `primaryLight` | `#9D97FF` | 157, 151, 255 | Dark mode primary, gradient bitiş noktası |
| `primaryDark` | `#4A42D4` | 74, 66, 212 | Login gradient ortası, aktif buton pressed state |

### 1.2 Vurgu Renkleri (Accent)
| Token | Hex | Kullanım |
|-------|-----|----------|
| `accent` | `#FF6B6B` | Bildirim badge, dikkat çekici öğeler |
| `accentLight` | `#FF9B9B` | Dark mode accent tonu |

### 1.3 Anlamssal Renkler (Semantic)
| Token | Hex | Kullanım |
|-------|-----|----------|
| `success` | `#4CAF50` | Tamamlama onayı, SnackBar başarı, takvim marker |
| `warning` | `#FF9800` | Seri uyarısı, süresi yaklaşan hedefler |
| `error` | `#F44336` | Hata mesajları, silme butonları, çıkış yap |
| `info` | `#2196F3` | Bilgi tooltip, ipucu kartları |

### 1.4 Nötr Renkler — Light Theme
| Token | Hex | Kullanım |
|-------|-----|----------|
| `background` | `#F8F9FE` | Scaffold arka planı |
| `surface` | `#FFFFFF` | Kart, dialog, bottom bar yüzeyi |
| `surfaceVariant` | `#F0F0F8` | Input alanları, alternatif yüzey |
| `textPrimary` | `#1A1A2E` | Ana metin, başlıklar |
| `textSecondary` | `#6B7280` | Açıklamalar, alt metin |
| `textHint` | `#9CA3AF` | Placeholder, deaktif metin |
| `divider` | `#E5E7EB` | Ayırıcı çizgiler, border |

### 1.5 Nötr Renkler — Dark Theme
| Token | Hex | Kullanım |
|-------|-----|----------|
| `darkBackground` | `#0F0F1A` | Scaffold arka planı |
| `darkSurface` | `#1A1A2E` | Kart, AppBar, BottomBar |
| `darkSurfaceVariant` | `#252540` | Yükseltilmiş yüzeyler |
| `darkTextPrimary` | `#F8F9FE` | Ana metin |

### 1.6 Alışkanlık Renk Paleti (12 renk)
Kullanıcı alışkanlık oluştururken seçebilir:

| # | Hex | Renk Adı |
|---|-----|----------|
| 1 | `#6C63FF` | Mor (varsayılan) |
| 2 | `#FF6B6B` | Kırmızı |
| 3 | `#4CAF50` | Yeşil |
| 4 | `#FF9800` | Turuncu |
| 5 | `#2196F3` | Mavi |
| 6 | `#E91E63` | Pembe |
| 7 | `#9C27B0` | Koyu Mor |
| 8 | `#00BCD4` | Turkuaz |
| 9 | `#8BC34A` | Açık Yeşil |
| 10 | `#FF5722` | Koyu Turuncu |
| 11 | `#607D8B` | Gri-Mavi |
| 12 | `#FFC107` | Sarı |

### 1.7 Gradient Setleri
| İsim | Başlangıç → Bitiş | Kullanım |
|------|--------------------|----------|
| Primary | `#6C63FF → #9D97FF` | Profil seviye badge, davet kartı |
| Login | `#6C63FF → #4A42D4 → #2D2696` | Login ekranı arka planı (topLeft→bottomRight) |
| Header | `#6C63FF → #4A42D4` | Home header, liderlik tablosu header |
| Accent | `#FF6B6B → #FFAB91` | Bildirim kartları |
| Success | `#4CAF50 → #81C784` | Tamamlama efektleri |
| Info | `#2196F3 → #64B5F6` | İpucu kartları |
| Pink | `#E91E63 → #F48FB1` | Sosyal özellikler |
| Cyan | `#00BCD4 → #80DEEA` | Takvim vurgular |

---

## 2. Tipografi

### 2.1 Font Ailesi
**Poppins** (Google Fonts) — tüm uygulama boyunca tek font.
- Modern, geometrik sans-serif
- Mükemmel Türkçe karakter desteği (ç, ş, ğ, ı, ö, ü)
- Light'tan ExtraBold'a geniş ağırlık yelpazesi

### 2.2 Font Ölçek Tablosu

| Boyut | Ağırlık | Kullanım Yeri |
|-------|---------|---------------|
| 42px | w800 | Splash ekran uygulama adı |
| 38px | w800 | Login ekranı "Habitra" yazısı |
| 28px | w700 | Alışkanlık detay ilerleme sayıları |
| 26px | w700 | Home header selamlama ("Günaydın! 👋") |
| 22px | w700 | Profil ismi, alışkanlık detay başlık |
| 20px | w800 | İstatistik büyük sayılar (XP, seri, toplam) |
| 18px | w600 | AppBar başlıklar, section header ("Bugünkü Alışkanlıklar") |
| 16px | w700 | Kart başlıkları, buton text, section alt başlıkları |
| 15px | w600 | Form input text, habit card isim, body text |
| 14px | w600 | Toggle link ("Giriş Yap" ↔ "Kayıt Ol"), info row değerleri |
| 13px | italic | Motivasyon sözleri, alt metin, top player isimleri |
| 12px | w500 | Badge metin, secondary bilgi, progress text, subtitle |
| 11px | w400 | Takvim gün isimleri, stat etiketleri, navbar label |
| 10px | w400-w600 | Navbar text, mood label, minimal etiketler |

### 2.3 Metin Stilleri
- **Başlıklar:** Poppins Bold/ExtraBold, `textPrimary` rengi
- **Body:** Poppins Regular, `textPrimary`
- **Açıklama:** Poppins Regular, `textSecondary`
- **Placeholder:** Poppins Regular, `textHint`
- **Link/Toggle:** Poppins Bold, `primary` veya `Colors.white`
- **Üstü Çizili:** Tamamlanmış alışkanlık ismi `TextDecoration.lineThrough`

---

## 3. Spacing, Layout & Geometri

### 3.1 Genel Spacing
| Token | Değer | Kullanım |
|-------|-------|----------|
| 2px | - | NavItem icon-label arası |
| 4px | xs | Minimal öğeler arası boşluk |
| 6px | - | Progress bar-text arası, kart iç öğeler |
| 8px | sm | Liste öğeleri arası (margin-bottom), chip spacing |
| 10px | - | Preset tile bottom padding, feature row arası |
| 12px | md | Kart iç padding, habit card öğeleri arası, input arası |
| 14px | - | Kart padding, stat box padding, input content padding |
| 16px | lg | Ana sayfa padding, section arası, form field arası |
| 20px | xl | Sayfa padding (horizontal & all), container padding |
| 24px | xxl | Major section arası, dialog padding, form section arası |
| 28px | - | Profil section'lar arası |
| 32px | xxxl | Login input-buton arası, sabit alt boşluklar |
| 40px | - | Empty state padding, bottom scroll space |
| 48px | - | Login ekranı üst boşluk |

### 3.2 Border Radius
| Değer | Kullanım |
|-------|----------|
| 3px | Progress bar bar radius |
| 4px | XP LinearProgressIndicator |
| 6px | Bar chart çubukları (sadece üst köşeler) |
| 8px | Podium blokları (sadece üst), streak badge |
| 12px | Butonlar, input alanları, liste öğeleri, friend tile, SnackBar |
| 14px | Habit card iç icon container, stat kutucukları |
| 16px | Kartlar (CardTheme), empty state, alışkanlık detay progress container |
| 20px | Feature kartları, takvim container, arkadaş davet kartı |
| 24px | Dialog shape |
| 28px | Login logo/icon container, home header alt köşeler |
| 30px | CircleAvatar (tam yuvarlak) |

### 3.3 Elevation & Gölge
| Bileşen | Elevation | Gölge Detayı |
|---------|-----------|-------------|
| Kartlar | 0 | Flat design, border veya shadow ile derinlik |
| FAB | 4 | Material 3 varsayılan |
| BottomAppBar | 12 | Belirgin alt navigasyon ayrımı |
| Genel Kart Gölge | - | `BoxShadow(color: black 4%, blur: 12, offset: (0,4))` |
| Tamamlanmış Kart | - | `BoxShadow(color: habitColor 5%, blur: 10, offset: (0,4))` |
| Renk Seçici (seçili) | - | `BoxShadow(color: habitColor 40%, blur: 8)` |

---

## 4. Ekranlar ve Akış

### 4.1 Navigasyon Yapısı

```
/login ─────────────── Login/Register Ekranı
    │
    ▼ (auth başarılı)
MainShell (BottomAppBar + FAB)
    ├── / ──────────── Home (Ana Sayfa)
    ├── /calendar ──── Takvim
    ├── /leaderboard ─ Liderlik Tablosu
    └── /profile ───── Profil
    
Full-Screen Routes (ShellRoute dışı):
    ├── /add-habit ──── Alışkanlık Ekle
    ├── /habit/:id ──── Alışkanlık Detay
    └── /friends ────── Arkadaşlar
```

### 4.2 Auth Guard
- `redirect` fonksiyonu her route değişiminde çalışır
- Giriş yapmamış → `/login`'e yönlendirilir
- Giriş yapmış + `/login`'deyse → `/`'e yönlendirilir

---

### 4.3 Ekran Detayları

#### 4.3.1 Login Ekranı (`/login`)
**Amaç:** Kayıt ve giriş işlemleri

**Layout:**
- Full screen gradient arka plan (`#6C63FF → #4A42D4 → #2D2696`)
- ScrollView içinde ortalanmış dikey düzen
- FadeTransition animasyonu (1500ms ease-in-out)

**Bileşenler:**
- **Logo Container:** 100x100, `white 15% opacity`, radius 28, `track_changes_rounded` icon (56px)
- **Başlık:** "Habitra" 38px w800, beyaz
- **Alt Başlık:** Dinamik (kayıt/giriş moduna göre değişir)
- **Form Alanları:** Yarı saydam (`white 12%`), beyaz text, beyaz border on focus
  - İsim (sadece kayıt modunda)
  - E-posta (email keyboard type)
  - Şifre (toggle visibility)
- **Submit Butonu:** 56px yükseklik, beyaz arka plan, primary renk text
- **Toggle Linki:** "Hesabın yok mu? **Kayıt Ol**" / "Zaten hesabın var mı? **Giriş Yap**"
- **Feature Satırları:** (sadece giriş modunda) 3 adet icon + text

**Akış:**
```
Kayıt Ol → signUp() → SnackBar "Kayıt başarılı!" → Giriş moduna geç
Giriş Yap → signIn() → context.go('/') → Home ekranı
```

---

#### 4.3.2 Ana Sayfa — Home (`/`)
**Amaç:** Günlük alışkanlık takibi ve genel bakış

**Layout (CustomScrollView, BouncingScrollPhysics):**

**1. Header Bölümü (Gradient Container)**
- Gradient: `primary → primaryDark`
- Alt köşeler: radius 28
- Padding: SafeArea.top + 16, horizontal 20

İçerik:
- **Selamlama Satırı:** Saate göre dinamik ("Günaydın!", "İyi Günler!", "İyi Akşamlar!") + 👋 emoji, 26px bold beyaz
- **Motivasyon Sözü:** Rastgele seçilen Türkçe alıntı, 13px italic, `white 80%`
- **Arkadaşlar Butonu:** `people_outline` icon, sağ üst
- **Haftalık İstatistik:** CircularPercentIndicator (radius 36, 5px kalınlık) + "Bu Hafta" / "X / Y tamamlandı"

**2. Haftalık Grafik (WeeklyChart Widget)**
- BarChart (fl_chart) — 7 çubuk (Pzt-Paz)
- Çubuk genişliği: 20px, üst köşeler radius 6
- Bugünkü gün: primary renk, diğerleri: `primary 30%`
- Tooltip: `tooltipBgColor: primary`
- Gün isimleri: bugün bold + primary, diğerleri normal + textSecondary

**3. Alışkanlık Listesi**
- Section başlığı: "Bugünkü Alışkanlıklar" + "X aktif" badge
- Sliver list, her öğe `HabitCard` widget
- Pull-to-refresh ile veri yenileme

**4. Empty State**
- Daire icon container (100x100, `primary 10%`, circle)
- `add_task_rounded` icon, 48px, primary
- "Henüz alışkanlık eklemediniz" + açıklama

**Check-in Mekanizması:**
- %30 olasılıkla, 2 saniye sonra `CheckInDialog` gösterilir

---

#### 4.3.3 Alışkanlık Kartı (`HabitCard` Widget)
**Amaç:** Tek bir alışkanlığın günlük durumunu gösterir

**Layout:** Row yapısı (Icon + Bilgi + Aksiyon)

**Sol:** 48x48 icon container, radius 14, `habitColor 15%`, icon renk: habitColor
**Orta:**
- İsim: 15px w600 (tamamlandıysa üstü çizili + textSecondary)
- Seri badge: (streak > 0 ise) 🔥 emoji + sayı, turuncu, `orange 10%` arka plan, radius 8
- Progress bar: LinearPercentIndicator, 6px yükseklik, radius 3
- Değer text: "X/Y birim", 12px textSecondary

**Sağ:** 40x40 aksiyon butonu, radius 12
- Tamamlanmamış: `habitColor 10%` arka plan, `+` icon
- Tamamlanmış: tam habitColor arka plan, `✓` icon, beyaz

**Durumlar:**
| Durum | Arka Plan | Border | Gölge |
|-------|-----------|--------|-------|
| Normal | surface | divider, 1.5px | black 5% |
| Tamamlanmış | `habitColor 10%` | `habitColor 30%`, 1.5px | `habitColor 5%` |

**Animasyon:** `AnimatedContainer`, 300ms geçiş süresi

---

#### 4.3.4 Check-in Dialog
**Amaç:** Kullanıcının duygusal durumunu toplamak

**Layout:** Dialog, radius 24, padding 24

**Bileşenler:**
- Emoji: 💭 (40px)
- Soru: Supabase'den rastgele çekilen Türkçe prompt (18px w600)
- **Mood Seçici:** 5 adet emoji satırı (😞 😕 😐 🙂 😄)
  - Her biri: tap ile seçilebilir
  - Seçili: `primary 15%` arka plan, `primary` border 2px, radius 12
  - Label: 10px, "Çok Kötü" → "Harika"
- **Butonlar:** "Sonra" (TextButton) + "Kaydet" (ElevatedButton, mood seçili olunca aktif)

**Animasyon:** Seçim animasyonu 200ms

---

#### 4.3.5 Alışkanlık Ekle (`/add-habit`)
**Amaç:** Yeni alışkanlık oluşturma (şablondan veya özel)

**Layout:** TabBarView (2 tab)

**Tab 1: Hazır Şablonlar**
- "⭐ Popüler" section → popüler preset'ler
- "Tümü" section → diğer preset'ler
- Her preset: ListTile, radius 14, `presetColor 6%` arka plan
  - Sol: 44x44 icon container, radius 12, `presetColor 15%`
  - Başlık: Türkçe isim (bold)
  - Alt metin: Türkçe açıklama (12px)
  - Sağ: hedef miktarı + birim text

**Tab 2: Özel Oluştur**
- İsim TextField + Açıklama TextField
- Hedef (number) + Birim (text) yan yana
- **Sıklık:** SegmentedButton ("Günlük" / "Haftalık" / "Özel")
  - Özel seçilince: 7 adet FilterChip (Pzt-Paz)
- **Renk Seçici:** 12 renk, 40x40, radius 12, seçili: beyaz border 3px + glow gölge + check icon
- **Hatırlatıcı:** SwitchListTile → TimePicker açılır
- **Bitiş Tarihi:** ListTile → DatePicker açılır
- **Liderlik Tablosu:** SwitchListTile (public toggle)
- **Oluştur Butonu:** 52px yükseklik, full-width

---

#### 4.3.6 Alışkanlık Detay (`/habit/:id`)
**Amaç:** Tekil alışkanlık istatistikleri ve ilerleme yönetimi

**Layout (CustomScrollView):**

**1. SliverAppBar (expandedHeight: 200, pinned)**
- FlexibleSpaceBar: gradient arka plan (`habitColor → habitColor 70%`)
- Ortalanmış: CircularPercentIndicator (radius 50, 8px) + isim (22px w700 beyaz)
- PopupMenuButton (Düzenle / Arşivle / Sil)

**2. İstatistik Kartları (3'lü Row)**
| Kart | Emoji | İçerik |
|------|-------|--------|
| Mevcut Seri | 🔥 | currentStreak |
| En İyi Seri | 🏆 | bestStreak |
| Toplam | ✅ | totalCompletions |

Her kart: padding 14, radius 14, `habitColor 6%`, sayı 22px w800

**3. Bugünkü İlerleme Bölümü**
- Container: `habitColor 6%`, radius 16, padding 20
- Başlık: "Bugünkü İlerleme", habitColor renk
- Sayaç: `−` butonu + "X / Y birim" (28px w800) + `+` butonu
- `-` buton: `habitColor 15%`, foreground habitColor
- `+` buton: habitColor filled, beyaz icon

**4. Açıklama + Meta Bilgi**
- Açıklama text (varsa)
- Info satırları: Sıklık, Başlangıç, Bitiş, Tamamlama Oranı

**Silme Dialogu:**
- AlertDialog: "Bu işlem geri alınamaz" uyarısı
- "İptal" + "Sil" (kırmızı) butonları

---

#### 4.3.7 Takvim (`/calendar`)
**Amaç:** Aylık takvim görünümünde alışkanlık geçmişi

**Layout (Column):**

**1. TableCalendar Widget**
- Container: surface renk, radius 20, gölge
- Locale: `tr_TR`, başlangıç: Pazartesi
- Bugün: `primary 30%` circle
- Seçili gün: `primary` solid circle
- Event marker: `success` yeşil, 6px, max 3 adet
- Header: format butonu gizli, ortlı başlık, 16px w600

**2. Seçili Gün Detayları (Expanded ListView)**
- Boş gün: `event_busy_rounded` icon (48px) + "Bu gün için kayıt yok"
- Kayıtlı gün: Her entry bir kart
  - Tamamlanmış: `habitColor 8%` arka plan, `habitColor 20%` border
  - Tamamlanmamış: cardColor, divider border
  - Sol: check_circle (tamamlanmış, habitColor) veya radio_button_unchecked (hint)
  - Orta: isim (tamamlandıysa üstü çizili) + "X/Y birim"
  - Sağ: mood emoji (varsa)

---

#### 4.3.8 Liderlik Tablosu (`/leaderboard`)
**Amaç:** XP bazlı kullanıcı sıralaması

**Layout (CustomScrollView):**

**1. Podyum (Top 3)**
- Gradient arka plan: `primary 10%` → transparent
- 3'lü Row, crossAxisAlignment: end (podium efekti)

| Sıra | Madalya | Avatar | Podium Yüksekliği | Renk |
|------|---------|--------|-------------------|------|
| 1 (orta) | 🥇 | radius 36 | 90px | amber |
| 2 (sol) | 🥈 | radius 28 | 70px | grey 400 |
| 3 (sağ) | 🥉 | radius 28 | 60px | brown 300 |

Podium blok: 80px genişlik, gradient (`renk 30%` → `renk 10%`), üst köşeler radius 8
İsim: 13px w600 + "XP" text: 12px w700 madalya rengi

**2. Liste (4. sıradan itibaren)**
- Sıra numarası: #N, 30px genişlik, w700, textSecondary
- Avatar: radius 18
- İsim + "Seviye X"
- Sağ: "XP" text (w700 primary) + "🔥 streak" text

**Empty State:** 🏆 (64px) + "Henüz sıralama yok" + açıklama

---

#### 4.3.9 Profil (`/profile`)
**Amaç:** Kullanıcı profili, istatistikler, takip edilen profiller

**Layout (ListView):**

**1. Profil Bilgi (Center)**
- Avatar: CircleAvatar radius 50 (avatar varsa resim, yoksa baş harf 36px w700)
- İsim: 22px w700
- Bio: textSecondary (varsa)
- Seviye Badge: gradient (`primary → primaryLight`), radius 20, padding h14/v6
  - "Seviye X - {levelTitle}" beyaz, 13px w600

**2. İstatistik Grid (3'lü Row)**
| Stat | Icon | Renk |
|------|------|------|
| XP | star_rounded | amber |
| Toplam | check_circle | success |
| En İyi Seri | local_fire_department | orange |

Her kutu: padding 14, radius 14, `renk 8%` arka plan, değer 20px w800

**3. XP Progress Bar**
- Container: `primary 6%`, radius 14
- "Seviye X" sol + "X/100 XP" sağ
- LinearProgressIndicator: 8px yükseklik, radius 4

**4. Takip Edilen Profiller**
- Başlık + "Ekle" TextButton.icon
- Boş state: surfaceVariant, radius 12, açıklama metni
- Liste: ListTile → avatar (baş harf) + isim + ilişki

**5. Profil Düzenleme Modu**
- İsim TextField, Bio TextField (3 satır), Cinsiyet Dropdown
- "İptal" OutlinedButton + "Kaydet" ElevatedButton

**6. Çıkış Butonu**
- OutlinedButton.icon: error renk border + "Çıkış Yap"

**Çıkış Dialogu:**
- "Çıkış yapmak istediğinize emin misiniz?"
- "İptal" + "Çıkış" (error renk)

---

#### 4.3.10 Arkadaşlar (`/friends`)
**Amaç:** Sosyal özellikler, davet kodu sistemi

**Layout (ListView):**

**1. Davet Kartı**
- Container: gradient (`primary → primaryDark`), radius 20, padding 20
- `group_add_rounded` icon (36px beyaz)
- "Arkadaşlarını Davet Et!" 18px w700 beyaz
- Alt metin: `white 80%`, 13px
- 2 buton: "Davet Kodu Paylaş" (beyaz) + "Kod Gir" (yarı saydam beyaz)

**2. Bekleyen İstekler**
- Başlık: "Bekleyen İstekler (N)"
- Her istek: `orange 6%` arka plan, `orange 20%` border, radius 12
- Avatar + isim + ✅ kabul + ❌ red butonları

**3. Arkadaş Listesi**
- Başlık: "Arkadaşlarım"
- Her arkadaş: ListTile, radius 12
  - Avatar (baş harf) + İsim
  - "Seviye X · Y tamamlama"
  - "🔥 streak" sağda

**Kod Girme Dialogu:**
- TextField: "ABCD1234" hint, `vpn_key_rounded` icon
- textCapitalization: characters, maxLength: 8
- "İptal" + "Kullan" butonları

**Paylaşma Akışı:**
```
Davet Kodu Paylaş → createInviteCode() → Share.share() (sistem paylaşım menüsü)
Mesaj: "Habitra'da alışkanlıklarımızı birlikte takip edelim! 🎯\nDavet kodum: XXXXXXXX"
```

---

## 5. Bottom Navigation & FAB

### 5.1 BottomAppBar
- Shape: `CircularNotchedRectangle` (FAB için çentik)
- `notchMargin: 8`
- Yükseklik: 60px
- Light: surface renk, Dark: darkSurface renk
- Elevation: 12

### 5.2 Navigasyon Öğeleri
| Index | Icon | Label | Route |
|-------|------|-------|-------|
| 0 | `home_rounded` | Ana Sayfa | `/` |
| 1 | `calendar_month_rounded` | Takvim | `/calendar` |
| — | (FAB boşluğu, 48px) | — | — |
| 2 | `leaderboard_rounded` | Sıralama | `/leaderboard` |
| 3 | `person_rounded` | Profil | `/profile` |

**Aktif:** primary renk, w600  
**Pasif:** textHint renk, w400  
**Icon:** 24px, Label: 10px

### 5.3 FAB (Floating Action Button)
- `FloatingActionButtonLocation.centerDocked`
- Renk: primary
- Icon: `add_rounded`, 28px, beyaz
- Elevation: 4
- Route: `/add-habit`

---

## 6. Dialog & Popup'lar

| Dialog | Tetiklenme | Shape | İçerik |
|--------|------------|-------|--------|
| Check-in Dialog | Home açılışında %30 olasılıkla | radius 24 | Mood seçici (5 emoji) + soru |
| Profil Ekle Dialog | Profil → "Ekle" | AlertDialog | İsim + İlişki dropdown |
| Çıkış Dialogu | Profil → "Çıkış Yap" | AlertDialog | Onay sorusu |
| Silme Dialogu | Alışkanlık Detay → Sil | AlertDialog | Geri alınamaz uyarısı |
| Kod Gir Dialogu | Arkadaşlar → "Kod Gir" | AlertDialog | 8 haneli kod girişi |
| TimePicker | Alışkanlık Ekle → Hatırlatıcı | Material | Saat seçimi |
| DatePicker | Alışkanlık Ekle → Bitiş Tarihi | Material | Tarih seçimi (1 yıla kadar) |

---

## 7. SnackBar Stilleri

| Tür | Renk | Örnek Mesaj |
|-----|------|-------------|
| Başarı | `AppColors.success` | "✅ Su İç eklendi!", "🎉 Alışkanlık tamamlandı!" |
| Hata | `AppColors.error` | "Giriş hatası: ...", "Kayıt hatası: ..." |
| Bilgi | varsayılan | "Teşekkürler! 😄" (mood kayıt) |

Tüm SnackBar'lar: `behavior: SnackBarBehavior.floating`, `shape: radius 12`

---

## 8. Animasyonlar

### 8.1 Mevcut Animasyonlar
| Animasyon | Widget | Süre | Curve | Detay |
|-----------|--------|------|-------|-------|
| Login FadeIn | FadeTransition | 1500ms | easeInOut | Tüm login formu yukarıdan fade |
| Habit Card State | AnimatedContainer | 300ms | - | Normal ↔ tamamlanmış geçişi (renk, border, gölge) |
| Aksiyon Butonu | AnimatedContainer | 300ms | - | + ↔ ✓ icon geçişi, arka plan rengi |
| Mood Seçimi | AnimatedContainer | 200ms | - | Seçili emoji vurgu geçişi |
| Renk Seçici | AnimatedContainer | 200ms | - | Seçili renk glow + check animasyonu |

### 8.2 Önerilen Ek Animasyonlar
| Animasyon | Açıklama | Öneri |
|-----------|----------|-------|
| Tamamlama Konfeti | Alışkanlık tamamlandığında ekranda konfeti | `confetti` paketi (zaten pubspec'te) |
| Seri Kutlama | Yeni seri rekoru kırıldığında | Lottie animasyonu + haptic feedback |
| Liste Giriş | Habit kartları sırayla girmesi | `flutter_animate` staggered fade+slide |
| Podyum Giriş | Leaderboard top 3 aşağıdan yukarı | Staggered scale + bounce |
| XP Kazanma | +10 XP kazanıldığında floating text | Yukarı kayan ve solan "+10 XP" text |
| Tab Geçişi | Add Habit tab değişimi | Smooth cross-fade |
| Pull-to-refresh | Yenileme animasyonu | Custom Lottie spinner |
| Takvim Marker | Gün tamamlandığında pulse | Scale + opacity pulse |
| Empty → Dolu | İlk alışkanlık eklendiğinde | Empty state fade out + liste fade in |
| Level Up | Seviye atladığında | Full screen overlay + parıltı efekti |

---

## 9. İkon Sistemi

### 9.1 Material Icons (Uygulama Geneli)
| İkon | Kullanım |
|------|----------|
| `track_changes_rounded` | Uygulama logosu |
| `home_rounded` | Nav: Ana Sayfa |
| `calendar_month_rounded` | Nav: Takvim |
| `leaderboard_rounded` | Nav: Sıralama |
| `person_rounded` | Nav: Profil |
| `add_rounded` | FAB, artırma butonu |
| `check_rounded` | Tamamlama onayı |
| `close_rounded` | Modal/sayfa kapatma |
| `edit_rounded` | Düzenleme modu |
| `more_vert` | Popup menü |
| `people_outline` | Arkadaşlar linki |
| `group_add_rounded` | Davet kartı |
| `person_add_rounded` | Arkadaş ekle |
| `share_rounded` | Paylaş |
| `vpn_key_rounded` | Davet kodu girişi |
| `star_rounded` | XP stat |
| `check_circle` | Toplam tamamlama stat |
| `local_fire_department` | Seri stat |
| `add_task_rounded` | Empty state |
| `event_busy_rounded` | Takvim boş gün |
| `logout_rounded` | Çıkış |

### 9.2 Alışkanlık İkonları (Habit Card Mapping)
| Icon String | Material Icon | Kategori |
|-------------|---------------|----------|
| `water_drop` | Icons.water_drop | Sağlık |
| `fitness_center` | Icons.fitness_center | Fitness |
| `menu_book` | Icons.menu_book | Eğitim |
| `self_improvement` | Icons.self_improvement | Zihinsel |
| `alarm` | Icons.alarm | Sağlık |
| `edit_note` | Icons.edit_note | Üretkenlik |
| `directions_walk` | Icons.directions_walk | Fitness |
| `restaurant` | Icons.restaurant | Beslenme |
| `translate` | Icons.translate | Eğitim |
| `spa` | Icons.spa | Kişisel Bakım |
| `brush` | Icons.brush | Yaratıcılık |
| `phone_disabled` | Icons.phone_disabled | Zihinsel |
| `medication` | Icons.medication | Sağlık |
| `savings` | Icons.savings | Finans |
| `check_circle` | Icons.check_circle | Varsayılan |
| `favorite` | Icons.favorite | Sağlık (kategori) |
| `star` | Icons.star | Genel |

### 9.3 Emoji Kullanımı
| Emoji | Bağlam |
|-------|--------|
| 👋 | Home selamlama |
| 💭 | Check-in dialog başlığı |
| 😞 😕 😐 🙂 😄 | Mood seçici (1-5) |
| 🔥 | Seri badge |
| ⭐ | Popüler şablonlar section |
| ✅ | SnackBar başarı mesajı prefix |
| 🎉 | Tamamlama kutlaması |
| 🏆 | Leaderboard empty + en iyi seri |
| 👥 | Arkadaş listesi empty state |
| 🎯 | Davet mesajı |
| 🥇 🥈 🥉 | Podyum madalyaları |

---

## 10. Gamification Sistemi

### 10.1 XP & Seviye
- Her tamamlama: **+10 XP**
- Her seviye: **100 XP**
- Seviye = `xp / 100` (integer division)

### 10.2 Seviye Unvanları (ProfileModel'den)
| Seviye | Unvan |
|--------|-------|
| 1-2 | Başlangıç |
| 3-4 | Kararlı |
| 5-9 | Azimli |
| 10-19 | Uzman |
| 20+ | Efsane |

### 10.3 Başarımlar (7 adet)
| İsim | Koşul | XP Ödülü |
|------|-------|----------|
| İlk Adım | 1 alışkanlık oluştur | 10 |
| Üç Gün Seri | 3 günlük seri | 25 |
| Haftalık Şampiyon | 7 günlük seri | 50 |
| Aylık Efsane | 30 günlük seri | 200 |
| Yüz Tamamlama | 100 toplam tamamlama | 100 |
| Alışkanlık Ustası | 5 aktif alışkanlık | 75 |
| Sosyal Kelebek | 3 arkadaş ekle | 50 |

---

## 11. Responsive & Platform Notları

### 11.1 Mevcut Durum
- Tasarım öncelikle **mobil** odaklı (tek kolon layout)
- Web build mevcut (GitHub Pages deploy)
- Dark mode: sistem teması takip edilir (`ThemeMode.system`)

### 11.2 Önerilen İyileştirmeler
| Alan | Öneri |
|------|-------|
| Tablet | 2-kolon grid layout (home + takvim yan yana) |
| Web | Max-width constraint (600-800px), centered layout |
| Landscape | Adaptive layout, split view |
| Accessibility | Semantic labels, contrast oranları kontrolü |
| iOS | Cupertino adaptif widgetlar (DatePicker, TimePicker) |

---

## 12. Dosya Yapısı (UI İlgili)

```
lib/
├── core/
│   ├── constants/
│   │   ├── app_constants.dart     ← Gamification, mood, motivasyon
│   │   ├── color_constants.dart   ← Tüm renk tanımları
│   │   └── supabase_constants.dart
│   ├── router/
│   │   └── app_router.dart        ← Tüm route + auth guard
│   ├── theme/
│   │   └── app_theme.dart         ← Light/Dark tema tanımları
│   └── utils/
│       └── icon_utils.dart        ← İkon mapping yardımcıları
├── features/
│   ├── auth/screens/
│   │   └── login_screen.dart      ← Kayıt/Giriş
│   ├── home/
│   │   ├── screens/
│   │   │   ├── home_screen.dart   ← Ana sayfa
│   │   │   └── main_shell.dart    ← BottomNav + FAB shell
│   │   └── widgets/
│   │       ├── checkin_dialog.dart ← Mood check-in popup
│   │       ├── habit_card.dart    ← Alışkanlık kart bileşeni
│   │       └── weekly_chart.dart  ← Haftalık bar chart
│   ├── habits/screens/
│   │   ├── add_habit_screen.dart  ← Şablon + özel ekleme
│   │   └── habit_detail_screen.dart ← Detay + sayaç
│   ├── calendar/screens/
│   │   └── calendar_screen.dart   ← Aylık takvim
│   ├── leaderboard/screens/
│   │   └── leaderboard_screen.dart ← Podyum + sıralama
│   ├── friends/screens/
│   │   └── friends_screen.dart    ← Davet + arkadaş listesi
│   └── profile/screens/
│       └── profile_screen.dart    ← Profil + düzenle + çıkış
└── shared/
    ├── models/
    │   └── profile_model.dart     ← Level title hesaplama
    └── widgets/                   ← Ortak widgetlar
```

# Habitra — Proje Handover Dokümanı
**Amaç:** Bu doküman, projeye devam edecek AI asistanına (Gemini) tüm bağlamı aktarmak için hazırlanmıştır.

---

## 1. Proje Özeti

**Habitra** — Flutter tabanlı alışkanlık takip uygulaması (Türkçe UI).

| Alan | Detay |
|------|-------|
| Platform | Flutter (Android APK + Web) |
| Backend | Supabase (PostgreSQL + Auth) |
| State | Riverpod |
| Routing | go_router |
| Tema | Material 3, Dark/Light mode |
| Font | Poppins (Google Fonts) |
| Dil | Türkçe (locale: tr_TR) |
| Auth | E-posta / Şifre (Supabase built-in) |

---

## 2. Repo & Altyapı

| Kaynak | URL / Bilgi |
|--------|-------------|
| **GitHub Repo** | https://github.com/stargazercoder/dont-break-the-chain |
| **Branch** | `main` (tek branch) |
| **Supabase Proje** | `jbpokrgowwpapmirgigl` (eu-central-1 Frankfurt) |
| **Supabase URL** | https://jbpokrgowwpapmirgigl.supabase.co |
| **Supabase Anon Key** | eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImpicG9rcmdvd3dwYXBtaXJnaWdsIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NzI2MTg3NDMsImV4cCI6MjA4ODE5NDc0M30.dc_97RIB0DikQuld_b99mprY3aAfo64fjm5of6ReBPY |
| **GitHub Pages** | https://stargazercoder.github.io/dont-break-the-chain/ |
| **CI/CD** | GitHub Actions (`.github/workflows/build.yml`) |
| **Flutter Versiyon** | 3.27.4 stable |
| **Java** | Zulu JDK 17 |

---

## 3. Proje Dosya Yapısı

```
habitra/
├── _Docs/
│   └── DESIGN_DOCUMENT.md        ← UI/UX tasarım dokümanı (renkler, fontlar, ekranlar, animasyonlar)
├── .github/workflows/
│   └── build.yml                 ← CI/CD: Web deploy (GitHub Pages) + APK build + Release
├── lib/
│   ├── main.dart                 ← Entry point, Supabase init, locale init (tr_TR)
│   ├── core/
│   │   ├── constants/
│   │   │   ├── app_constants.dart      ← Gamification, mood emojis, motivasyon sözleri
│   │   │   ├── color_constants.dart    ← Tüm renk tanımları (AppColors)
│   │   │   └── supabase_constants.dart ← URL + anon key
│   │   ├── router/
│   │   │   └── app_router.dart         ← GoRouter, auth guard, tüm route tanımları
│   │   ├── services/
│   │   │   ├── auth_service.dart       ← signUp, signIn, signOut, resetPassword
│   │   │   ├── checkin_service.dart    ← Mood check-in prompt
│   │   │   ├── friend_service.dart     ← Arkadaşlık, davet kodu sistemi
│   │   │   ├── habit_service.dart      ← CRUD alışkanlık, entry upsert, istatistik
│   │   │   ├── profile_service.dart    ← Profil güncelleme, managed profiles
│   │   │   └── supabase_service.dart   ← Supabase client singleton
│   │   ├── theme/
│   │   │   └── app_theme.dart          ← Light + Dark ThemeData
│   │   └── utils/
│   │       └── icon_utils.dart
│   ├── features/
│   │   ├── auth/
│   │   │   ├── providers/auth_provider.dart
│   │   │   └── screens/login_screen.dart      ← E-posta kayıt/giriş
│   │   ├── home/
│   │   │   ├── providers/home_provider.dart    ← activeHabits, todayEntries, weeklyStats
│   │   │   ├── screens/
│   │   │   │   ├── home_screen.dart            ← Ana sayfa
│   │   │   │   └── main_shell.dart             ← BottomAppBar + FAB
│   │   │   └── widgets/
│   │   │       ├── checkin_dialog.dart          ← Mood popup
│   │   │       ├── habit_card.dart              ← Alışkanlık kart widget
│   │   │       └── weekly_chart.dart            ← fl_chart bar grafik
│   │   ├── habits/
│   │   │   ├── models/habit_model.dart          ← HabitModel, HabitEntryModel, PresetHabitModel
│   │   │   └── screens/
│   │   │       ├── add_habit_screen.dart         ← Şablon + özel oluştur (TabBar)
│   │   │       └── habit_detail_screen.dart      ← Detay, sayaç, sil/arşivle
│   │   ├── calendar/screens/
│   │   │   └── calendar_screen.dart              ← TableCalendar + gün detayları
│   │   ├── leaderboard/
│   │   │   ├── providers/leaderboard_provider.dart
│   │   │   └── screens/leaderboard_screen.dart   ← Podyum + sıralama listesi
│   │   ├── friends/
│   │   │   ├── providers/friend_provider.dart
│   │   │   └── screens/friends_screen.dart        ← Davet kodu, arkadaş listesi
│   │   └── profile/
│   │       ├── providers/profile_provider.dart
│   │       └── screens/profile_screen.dart        ← Profil, istatistik, managed profiles
│   └── shared/
│       ├── models/profile_model.dart              ← ProfileModel, level title
│       └── widgets/
├── pubspec.yaml
└── assets/
    ├── images/
    └── icons/
```

---

## 4. Supabase Veritabanı Şeması

### Tablolar

| Tablo | Açıklama |
|-------|----------|
| `profiles` | Kullanıcı profilleri (auth.users ile 1:1, trigger ile otomatik oluşur) |
| `managed_profiles` | Takip edilen profiller (çocuk, eş vb.) |
| `habit_categories` | 10 kategori (Sağlık, Fitness, Eğitim vb.) |
| `preset_habits` | 15 hazır şablon alışkanlık (Türkçe/İngilizce) |
| `habits` | Kullanıcı alışkanlıkları |
| `habit_entries` | Günlük alışkanlık kayıtları (value, target, mood, notes) |
| `friendships` | Arkadaşlık ilişkileri (pending/accepted/rejected) |
| `friend_invites` | 8 haneli davet kodları (24 saat geçerli) |
| `challenges` | Grup challenge'ları |
| `challenge_participants` | Challenge katılımcıları |
| `notifications` | Bildirimler |
| `achievements` | 7 başarım tanımı |
| `user_achievements` | Kazanılmış başarımlar |
| `checkin_prompts` | 8 mood check-in sorusu (TR/EN) |

### Önemli Fonksiyonlar & Trigger'lar
- `handle_new_user()` — Yeni kayıtta otomatik profil oluşturur
- `update_habit_streak()` — Entry tamamlandığında seri günceller
- `update_updated_at()` — updated_at otomatik güncelleme
- `generate_invite_code()` — 8 haneli rastgele davet kodu
- `get_habit_leaderboard()` — XP bazlı sıralama fonksiyonu
- `leaderboard_view` — Sıralama view'ı

### Güvenlik
- **RLS** tüm 14 tabloda aktif
- Her tablo için SELECT/INSERT/UPDATE/DELETE policy'leri tanımlı
- Fonksiyonlarda `SET search_path = public`
- Leaderboard view: `security_invoker = true`

---

## 5. CI/CD Pipeline

**Workflow:** `.github/workflows/build.yml`

| Job | İşlev | Çıktı |
|-----|-------|-------|
| `build-web` | Flutter web build + GitHub Pages deploy | `gh-pages` branch'e deploy |
| `build-apk` | Flutter APK debug build | GitHub Release + artifact |

**Tetiklenme:** `push to main` veya `workflow_dispatch`

**Base href:** `/dont-break-the-chain/` (GitHub Pages subpath)

---

## 6. Paketler (pubspec.yaml)

Ana bağımlılıklar:
- `supabase_flutter` — Backend
- `flutter_riverpod` — State management
- `go_router` — Routing
- `fl_chart` — Grafik (v0.66.2, `tooltipBgColor` API'si)
- `table_calendar` — Takvim widget
- `google_fonts` — Poppins font
- `percent_indicator` — Circular/linear progress
- `cached_network_image` — Avatar caching
- `share_plus` — Sistem paylaşım menüsü
- `intl` — Türkçe locale desteği
- `confetti` — Kutlama efekti (henüz kullanılmıyor)

---

## 7. Bilinen Sorunlar & TODO'lar

### Kod İçi TODO'lar
- `weekly_chart.dart` — "Replace with real data" (şu an mock veri)
- `checkin_dialog.dart` — "Save mood to entries" (mood kaydedilmiyor)
- `habit_card.dart` — Icon mapping sınırlı (17 icon tanımlı)

### Eksik Özellikler
- [ ] Bildirim sistemi (local notifications)
- [ ] Başarım popup'ları
- [ ] Konfeti animasyonu entegrasyonu
- [ ] Alışkanlık düzenleme ekranı
- [ ] Challenge sistemi UI
- [ ] Profil fotoğrafı yükleme
- [ ] Google OAuth (ertelendi, email auth aktif)
- [ ] Offline mod / local cache
- [ ] Widget test'leri

### Dikkat Edilmesi Gerekenler
- `fl_chart` v0.66.2 kullanılıyor — `getTooltipColor` YOK, `tooltipBgColor` kullanılmalı
- `num` yerine `double` kullanılmalı (Dart strict typing)
- Supabase email confirmation KAPALI olmalı (test kolaylığı için)
- Flutter 3.27.4 — daha eski versiyonlar `app_links` paketi ile uyumsuzluk yaratır

---

## 8. Gamification Değerleri

| Parametre | Değer |
|-----------|-------|
| XP per completion | 10 |
| XP per level | 100 |
| Max active habits | 20 |
| Max managed profiles | 5 |
| Mood emojis | 😞 😕 😐 🙂 😄 |
| Mood labels | Çok Kötü, Kötü, Normal, İyi, Harika |

---

## 9. Motivasyon Sözleri (Türkçe)

Home ekranında rastgele gösterilir:
1. Her uzun yolculuk tek bir adımla başlar.
2. Bugün yaptıkların, yarınını şekillendirir.
3. Küçük adımlar, büyük değişimler yaratır.
4. Tutarlılık, başarının anahtarıdır.
5. Kendine inan, yapabilirsin!
6. Alışkanlıkların kaderini belirler.
7. Bugün en iyi versiyonun ol.
8. Her yeni gün, yeni bir başlangıç.
9. Disiplin, özgürlüğe giden yoldur.

---

## 10. v2.0 Güncellemesi (Mart 2026)

### Tema Değişikliği
Tüm uygulama **mor (#6C63FF)** → **turuncu (#FF6B2C)** olarak güncellendi.
Detaylar: `lib/core/constants/color_constants.dart`

Yeni renk tokenları eklendi: `streakFire`, `streakGold`, `section*` (fihrist renkleri), `reminder*` (hatırlatma türü renkleri)

### Yeni Supabase Tabloları (11 tablo)

| Tablo | Açıklama |
|-------|----------|
| `notebook_sections` | Not defteri bölümleri (fihrist) |
| `notebook_entries` | Not kayıtları (text/checklist/table) |
| `calendar_events` | Takvim etkinlikleri |
| `reminders` | Tekrarlayan hatırlatmalar (ilaç/su/uyku) |
| `reminder_logs` | Hatırlatma geçmişi |
| `water_logs` | Su tüketim kayıtları |
| `sleep_logs` | Uyku/uyanma kayıtları |
| `goals` | Hedefler (yıllık/aylık/haftalık, self-referencing) |
| `streak_rewards` | Streak ödül tanımları |
| `user_rewards` | Kazanılmış ödüller |
| `stickers` | Sticker tanımları |
| `user_stickers` | Kullanıcı sticker'ları |
| `themes` | Tema tanımları |
| `user_themes` | Açılmış temalar |
| `daily_questions` | Günlük soru havuzu (60 soru) |
| `daily_question_answers` | Kullanıcı cevapları |

### Seed Data
- **10 streak ödülü:** 3 gün (rozet) → 365 gün (tüm ödüller)
- **7 tema:** Turuncu Enerji (varsayılan), Okyanus Mavisi, Orman Yeşili, Gece Moru, Gül Kurusu, Altın Sarısı, Gökkuşağı
- **60 günlük soru:** 6 kategori (öz-farkındalık, hedef, minnettarlık, motivasyon, ilişkiler, alışkanlıklar)
- **Otomatik trigger:** Yeni kullanıcıya 7 varsayılan not defteri bölümü oluşturulur

### Tam PRD
Detaylı ürün gereksinimleri: `_Docs/PRD_V2.md`

### Henüz Flutter Kodu Yazılmamış Modüller
Aşağıdaki modüller için DB tabloları hazır ama Flutter ekranları/servisleri henüz yok:
- [ ] Not Defteri ekranı + fihrist UI
- [ ] Takvim etkinlik ekleme/düzenleme
- [ ] Hatırlatıcı yönetimi (ilaç, su, uyku)
- [ ] Hedef sistemi ekranları
- [ ] Streak ödül popup'ları
- [ ] Günlük soru akışı (sabah/akşam)
- [ ] Tema değiştirme ekranı
- [ ] Sticker sistemi
- [ ] Bottom nav güncelleme (Defter tabı ekleme)

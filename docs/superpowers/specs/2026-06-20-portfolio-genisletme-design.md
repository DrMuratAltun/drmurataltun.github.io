# Portfolyo Genişletme — Tasarım Dokümanı

**Tarih:** 2026-06-20
**Dosya:** `index.html` (tek dosya, Tailwind CDN + vanilla JS)
**Amaç:** Mevcut portfolyoyu daha kapsamlı hale getirmek; WordPress (altunmurat.wordpress.com) ve diğer kaynaklardaki eksik verileri eklemek. Yön: hem içerik derinliği hem görsel/etkileşim ("ikisi de").

## Kısıtlar
- Tek dosya `index.html` yapısı korunur. Yeni framework/build adımı yok.
- Mevcut görsel dil korunur: cyan (#06b6d4) / koyu slate tema, glassmorphism, parçacık ağı, typewriter, reveal-on-scroll.
- Türkçe özel karakter kuralı: tüm user-visible metinde ö ü ş ı ğ ç İ Ö Ü Ş Ğ Ç doğru kullanılır.
- Yalnızca doğrulanmış veriler eklenir. Doğrulanmamış sosyal handle eklenmez.

## Bölüm Yapısı (anchor sırası)

1. **Ana Sayfa** (mevcut) — typewriter rollerine ekleme: "Akademisyen", "Robotik Eğitmeni".
2. **Hakkımda** (mevcut) — hafif zenginleştirme; veri madenciliği vurgusu.
3. **Akademik Çalışmalar** *(YENİ)*
   - Doktora tezi: TR "Veri Madenciliği ile Öğrenci Akademik Performans Tahmini" + İng. "Model Proposal Related To Predicting Student Academic Performance: A Study Based On Data Mining"
   - Odak alanları: Veri Madenciliği, Eğitsel Veri Madenciliği, Veri Analizi
   - ResearchGate profil linki (mevcut)
4. **Deneyim & Eğitim** (mevcut) — değişmez.
5. **Verdiğim Dersler** *(YENİ)* — Akdeniz Üniversitesi kompakt liste:
   - Korkuteli MYO (2011–2018): Nesne Yönelimli Programlama I/II, Görsel Programlama (VB), Mikrobilgisayar Sistemleri, Bilgisayar Donanımı, Yazılım Mimarileri, Açık Kaynak/Sunucu İşletim Sistemleri, Programlama Teknikleri, Çoklu Ortam Uygulamaları, Grafik ve Animasyon II
   - UBF YBS (2019–): Robotik Uygulamaları Dersi
6. **Kitaplar** (mevcut, ayrı bölüm) — sanal kütüphane iframe + 6 kitap kartı korunur.
7. **Eğitim Çalışmaları & Referanslar** (mevcut Padlet galerisi) — değişmez.
8. **Araç & Teknoloji** *(YENİ)* — rozet/ikon ızgarası: Python, LLM/GPT, Pandas, scikit-learn, mBot, mBlock, Scratch, TinkerCAD, Arduino, IoT. Hover glow/tilt efekti.
9. **Topluluk & Üyelikler** *(YENİ)* — DuckieTown Türkiye Temsilcisi; Antalya BTE Derneği (Bilişim Teknolojileri Eğitimcileri Derneği) üyeliği.
10. **İletişim** (mevcut, genişletilir)
    - Sosyal medya kompakt ızgara — doğrulanmış: Email, LinkedIn (`/in/drmurataltun`), Instagram (`/drmurataltun`), ResearchGate, Linktree, **GitHub (`github.com/DrMuratAltun`)**.
    - **Threads** (`threads.net/@drmurataltun`) — desen tutarlılığıyla eklenir, "doğrula" notu ile.
    - Projeler kompakt şerit (mevcut): Derin Öğrenme Bootcamp, VB-YZ-90, Yapay Zeka Okulum, GencYZ, YZ Araçları, ScholarAI.

## Etkileşim / Animasyon Eklemeleri
- **Count-up sayaçlar:** Hakkımda istatistiklerinde (6+ kitap, 600+ saat) viewport'a girince sayma animasyonu.
- **Timeline çizgisi:** Akademik Çalışmalar ve Verdiğim Dersler bölümlerinde dikey çizgi + nokta işaretçileri.
- **Araç rozetleri:** hover'da glow + hafif scale.
- Tüm yeni bölümler mevcut `reveal-on-scroll` IntersectionObserver desenini kullanır.

## Navigasyon
- Masaüstü navbar ve mobil menü güncellenir. Yer darlığı nedeniyle: Ana Sayfa, Hakkımda, Akademik, Deneyim, Dersler, Kitaplar, İletişim (Araç/Topluluk anchor olarak var ama navbar'da gruplanabilir / mobilde tam liste).

## SEO / Yapısal Veri
- JSON-LD `Person` güncellenir: `sameAs` listesine GitHub + Threads eklenir; `alumniOf` korunur. Tez başlığı `description`'a yansıtılabilir.
- `og:description` ve meta açıklama güncellenmez (zaten kapsayıcı) — gerekirse küçük rötuş.

## Test / Doğrulama
- Tarayıcıda görsel kontrol (Chrome DevTools MCP veya yerel açma): tüm bölümler render oluyor, mobil menü çalışıyor, count-up tetikleniyor, iframe'ler yükleniyor.
- Türkçe karakter taraması.
- Tüm yeni linkler hedeflere gidiyor (Threads doğrulama notu hariç).

## Kapsam Dışı (YAGNI)
- Blog/teknik içerik bölümü (kullanıcı seçmedi — WordPress yazıları 2019-2020, eski).
- Backend, form gönderimi, çoklu sayfa, i18n.

## Açık Not (doğrulanacak)
- Threads handle `@drmurataltun` varsayım; kullanıcı doğrulayınca kalır/kaldırılır.

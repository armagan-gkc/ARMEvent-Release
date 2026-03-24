<p align="center">
  <img src="https://img.shields.io/badge/Minecraft-1.21.1-brightgreen?style=for-the-badge&logo=minecraft&logoColor=white" alt="Minecraft 1.21.1"/>
  <img src="https://img.shields.io/badge/Paper-API-blue?style=for-the-badge" alt="Paper API"/>
  <img src="https://img.shields.io/badge/Java-21-orange?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java 21"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-gold?style=for-the-badge" alt="Version 1.0.0"/>
</p>

<h1 align="center">⚔ ARMEvent</h1>

<p align="center">
  <b>22 farklı etkinlik türü ile Minecraft sunucunuzu canlı ve eğlenceli tutun.</b><br/>
  Profesyonel etkinlik yönetim sistemi — zamanlama, ödül, sıralama ve çoklu dil desteği.
</p>

<p align="center">
  <a href="#-kurulum">Kurulum</a> •
  <a href="#-etkinlikler">Etkinlikler</a> •
  <a href="#-komutlar">Komutlar</a> •
  <a href="#-yapılandırma">Yapılandırma</a> •
  <a href="#-placeholderapi">PlaceholderAPI</a> •
  <a href="#-bağımlılıklar">Bağımlılıklar</a>
</p>

---

## 📥 Kurulum

1. [Releases](https://github.com/armagan-gkc/ARMEvent-Release/releases) bölümünden `ARMEvent-1.0.0.jar` dosyasını indirin
2. JAR dosyasını sunucunuzun `plugins/` klasörüne kopyalayın
3. Sunucuyu yeniden başlatın
4. `plugins/ARMEvent/config.yml` dosyasından ayarları özelleştirin

> **Gereksinim:** Paper 1.21.1+ ve Java 21+

---

## 🎮 Etkinlikler

ARMEvent, **11 sohbet tabanlı** ve **11 aksiyon tabanlı** olmak üzere toplam **22 benzersiz etkinlik** sunar.

### 💬 Sohbet Tabanlı Etkinlikler

| Etkinlik | Açıklama |
|:---------|:---------|
| **🗳️ Oyuncu Oylama** | Oyuncular sohbette oy kullanır |
| **🧠 Mantık Soru** | Mantık soruları cevaplanır |
| **📝 Kelime Yarışması** | Doğru kelimeyi ilk yazan kazanır |
| **🔢 Matematik Yarışı** | Matematik problemleri çözülür |
| **🎯 Sayı Tahmin** | Gizli bir sayıyı tahmin edin |
| **🔄 Tersine Kelime** | Ters çevrilmiş kelimeleri doğru yazın |
| **😀 Emoji Tahmin** | Emojilerin neyi temsil ettiğini tahmin edin |
| **❓ Bilgi Yarışması** | Genel kültür soruları yarışması |
| **⌨️ Hızlı Yazma** | Verilen metni en hızlı yazın |
| **🔗 Kelime Zinciri** | Son harfle başlayan kelime zinciri oluşturun |
| **🎨 Renk Söyle** | Görüntülenen metnin rengini doğru söyleyin |

### ⚔️ Aksiyon Tabanlı Etkinlikler

| Etkinlik | Açıklama |
|:---------|:---------|
| **📦 Envanter Dağıtım** | Envanter tabanlı item dağıtımı |
| **🗺️ Hazine Avı** | Dünyada gizlenmiş sandığı bulun |
| **⛏️ Kaynak Toplama** | Belirtilen kaynakları toplayın |
| **🗡️ Mob Avı** | Belirtilen mobları avlayın |
| **🎣 Olta Yarışması** | Rekabetçi balık tutma |
| **🍖 Yemek Yarışı** | En hızlı yemek pişirin |
| **🌾 Hasat Yarışı** | Ekin hasadı yarışması |
| **✨ XP Yarışı** | En çok XP kazanın |
| **🪓 Ağaç Kesme** | En çok odun kesin |
| **🔨 Crafting Yarışı** | Belirtilen itemleri üretin |
| **🐾 Evcilleştirme** | Hayvanları evcilleştirme yarışı |

---

## 🛠️ Komutlar

Tüm komutlar `/armevent` altında çalışır. Yetki: `armevent.admin`

| Komut | Açıklama |
|:------|:---------|
| `/armevent yardim` | Komut yardım menüsü |
| `/armevent baslat <tür>` | Etkinlik başlat |
| `/armevent hizli <tür>` | Hızlı etkinlik başlat (bekleme yok) |
| `/armevent durdur` | Aktif etkinliği durdur |
| `/armevent liste` | Tüm etkinlikleri listele |
| `/armevent yenile` | Ayarları yeniden yükle |
| `/armevent istatistik` | Kişisel istatistikler |
| `/armevent siralama [sayı]` | Sıralama tablosu (varsayılan: 10) |
| `/armevent zamanlama` | Zamanlama bilgisi |
| `/armevent setspawn <tür> <no>` | Spawn noktası ayarla |
| `/armevent delspawn <tür> <no>` | Spawn noktası sil |
| `/armevent spawnlar <tür>` | Spawn noktalarını listele |

---

## ⚙️ Yapılandırma

### Dosya Yapısı

```
plugins/ARMEvent/
├── config.yml              # Ana yapılandırma
├── spawns.yml              # Spawn noktaları (otomatik)
├── database.db             # SQLite veritabanı (otomatik)
├── events/
│   ├── player-vote.yml     # Her etkinlik için ayrı config
│   ├── treasure-hunt.yml
│   ├── math-race.yml
│   └── ... (22 dosya)
└── languages/
    ├── tr.yml              # Türkçe
    └── en.yml              # İngilizce
```

### config.yml Örneği

```yaml
# Dil seçimi: tr veya en
language: tr

# Etkinlik başlatmak için minimum oyuncu
min-players: 2

# Zamanlama ayarları
schedule:
  math-race:
    enabled: true
    interval-minutes: 30       # Her 30 dakikada bir
    times: ["14:00", "20:00"]  # Sabit saatler
```

### Etkinlik Config Örneği

```yaml
# events/treasure-hunt.yml
enabled: true
duration: 120
hint-interval: 20
reward:
  material: DIAMOND
  amount: 5
  display-name: "&b✦ Hazine Ödülü"
```

---

## 📊 PlaceholderAPI

| Placeholder | Açıklama |
|:------------|:---------|
| `%armevent_events_joined%` | Katılınan etkinlik sayısı |
| `%armevent_events_won%` | Kazanılan etkinlik sayısı |
| `%armevent_total_rewards%` | Toplam alınan ödül |
| `%armevent_active_event%` | Aktif etkinlik adı |

---

## 📦 Bağımlılıklar

| Eklenti | Durum | Açıklama |
|:--------|:------|:---------|
| [Paper](https://papermc.io/) 1.21.1+ | **Zorunlu** | Sunucu yazılımı |
| [Vault](https://github.com/MilkBowl/Vault) | İsteğe Bağlı | Ekonomi ödülleri |
| [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) | İsteğe Bağlı | Placeholder desteği |
| [DecentHolograms](https://www.spigotmc.org/resources/decentholograms.96927/) | İsteğe Bağlı | Hologram desteği |

---

## 🔑 Öne Çıkan Özellikler

- **22 Etkinlik** — Sohbet ve aksiyon tabanlı çeşitli etkinlikler
- **Otomatik Zamanlama** — Sabit saat veya aralık tabanlı otomatik etkinlik başlatma
- **15 Dakika Uyarısı** — Planlanan etkinliklerden önce otomatik bildirim
- **Çoklu Dil** — Türkçe ve İngilizce tam dil desteği
- **SQLite Veritabanı** — Kalıcı oyuncu istatistikleri ve geçmiş
- **Sıralama Sistemi** — En iyi oyuncuların sıralaması
- **Ödül Sistemi** — Item ve ekonomi ödülleri, etkinlik başına özelleştirilebilir
- **Spawn Yönetimi** — Etkinlik bazlı çoklu spawn noktası desteği
- **Sohbet Engeli** — Etkinlik süresince sohbet otomatik engellenir
- **Tab Tamamlama** — Tüm komutlarda akıllı tab tamamlama
- **Havai Fişek** — Hazine avı kazananlara özel kutlama efektleri
- **Hot Reload** — Sunucu yeniden başlatmadan ayar yükleme

---

## 📜 Sürüm Geçmişi

### v1.0.0
> İlk kararlı sürüm

- 22 benzersiz etkinlik türü
- Tam zamanlama ve ödül sistemi
- Türkçe ve İngilizce dil desteği
- PlaceholderAPI entegrasyonu
- SQLite veritabanı ile kalıcı istatistikler
- Spawn noktası yönetim sistemi

---

<p align="center">
  <b>Geliştirici:</b> Armağan Gökce<br/>
  <b>Discord:</b> thepaygo<br/>
  <b>Web:</b> <a href="https://www.armagangokce.com">armagangokce.com</a>
</p>

<p align="center">
  <sub>Paper 1.21.1 • Java 21 • Made with ❤️</sub>
</p>

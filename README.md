# aysmenu

**Restoranlar için QR menü, masa siparişi ve online ödeme platformu.**  
[AysTech](https://aystech.com.tr) tarafından geliştirilmiştir.

Misafir masadaki QR’ı okutur → menüyü açar → kendi adına sipariş verir → hesabını PayTR ile öder.  
Garson, mutfak ve yönetim aynı anda, gerçek zamanlı çalışır. Her işletme kendi adresinde:  
`https://{slug}.aysmenu.com.tr`

---

## Canlı demo

| | |
|--|--|
| Landing | [aysmenu.com.tr](https://aysmenu.com.tr) |
| Müşteri menü | [demo.aysmenu.com.tr/m/t1](https://demo.aysmenu.com.tr/m/t1) |
| Firma paneli | [demo.aysmenu.com.tr/admin](https://demo.aysmenu.com.tr/admin) |
| Garson | [demo.aysmenu.com.tr/garson](https://demo.aysmenu.com.tr/garson) |
| Mutfak | [demo.aysmenu.com.tr/mutfak](https://demo.aysmenu.com.tr/mutfak) |

Demo işletme: **Lezzet Durağı** · slug `demo`  
Panel: `demo@aysmenu.com.tr` *(şifre için iletişime geçin veya ekibe sorun)*

---

## Ne sunuyor?

### Misafir
- Masa QR ile menü; kişi bazlı katılım ve sepet
- Garson çağırma, Wi‑Fi bilgisi, karşılama / güle güle deneyimi
- Kendi hesabını görme ve PayTR ile ödeme (split bill)

### Garson
- Mobil masa → kişi → ürün ekleme
- Canlı adisyon, mutfak durumu, çağrı kapatma
- Anlık uyarı (bildirim + ses + titreşim)

### Mutfak
- Sipariş kuyruğu: bekliyor → hazırlanıyor → hazır
- “Hazır” olduğunda garsona otomatik uyarı

### Firma yönetimi
- Kategori / ürün / masa / markalı QR
- Tema, özellik bayrakları, personel rolleri
- Kasa, cihaz / POS, PayTR ayarları, adisyon e‑postası

### Merkez (HQ)
- Çok kiracılı bayi modeli, firmalar, CRM lead, faturalama
- Ortak SMTP / PayTR varsayılanları

---

## Öne çıkanlar

- **Çok kiracılı mimari** — her restoran kendi subdomain’inde
- **Tek kullanımlık QR token** — link paylaşımıyla uzaktan sızmayı engeller
- **Kişi bazlı adisyon** — her misafir yalnız kendi hesabını görür ve öder
- **Gerçek zamanlı ops** — admin, garson ve mutfak aynı Firestore akışını dinler
- **PayTR + POS köprüsü** — online ödeme ve yerel ÖKC / ESC‑POS yazıcı desteği
- **Wildcard HTTPS** — `aysmenu.com.tr` ve `*.aysmenu.com.tr` (Google Trust Services)

---

## Bayilik URL’leri

Kanonik: **`https://{slug}.aysmenu.com.tr`**

| Yol | Açıklama |
|-----|----------|
| `/admin` | Firma paneli |
| `/garson` | Mobil garson |
| `/mutfak` | Mutfak ekranı |
| `/m/{tableId}?t=TOKEN` | Müşteri menü |
| `/go/{tableId}` | Markalı QR giriş |
| `/pay/{sessionId}` | Kişi ödemesi |

Apex polyfill: `/f/{slug}/admin`, `/m/{slug}/{tableId}`  
DNS: `*.aysmenu.com.tr` → App Hosting (`aysmenu`)

---

## QR güvenlik

- Masa başına token havuzu
- Tarama sonrası kısa yenileme penceresi
- Süre bitince masadaki QR’ın tekrar okutulması gerekir
- Demo ortamında kolay deneme için token zorunluluğu gevşetilebilir

---

## İletişim

- Ürün: [aysmenu.com.tr](https://aysmenu.com.tr)
- Şirket: [aystech.com.tr](https://aystech.com.tr)

© AysTech · aysmenu

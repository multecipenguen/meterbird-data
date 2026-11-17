# meterbird-data

[MeterBird](https://github.com/multecipenguen/meterbird) uygulamasının kullandığı **resmî tarife ve limit verisi**.

- **Kullanıcı verisi içermez.** Yalnızca herkese açık resmî kaynaklardan alınan fiyat ve limitler vardır.
- Her dosya kaynağını (`source.name`, `source.url`) ve kontrol tarihini (`source.checkedAt`) taşır.
- `manifest.json`: tüm dosyaların yolu, `sha256`'sı ve boyutu. Uygulama günde en fazla bir kez
  manifest'i indirir, değişen dosyaları indirir ve kendi doğrulayıcısından geçirir (geçersiz dosya reddedilir).

## İçerik
| Yol | Açıklama | Kaynak |
|---|---|---|
| `limits/gas/TR/<YYYY-AA>.json` | Konut doğalgazı il bazlı aylık limit (Sm³), 81 il | [BOTAŞ](https://www.botas.gov.tr/Sayfa/satis-fiyat-tarifesi/439) |

Şema ve doğrulama kuralları uygulama deposundadır (`lib/domain/tier_limits.dart`, `lib/domain/tariff_file.dart`).

## Uyarı
Veri bilgilendirme amaçlıdır; fatura hesabı için resmî kaynaklar esastır. Fiyatlar her ay değişebilir.

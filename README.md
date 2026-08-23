# futbol-veri-aynasi

[football-data.co.uk](https://www.football-data.co.uk/) tarafından kamuya açık ve ücretsiz
yayımlanan lig CSV dosyalarının günlük aynası.

## Neden

`football-data.co.uk` Türkiye'den erişime engelli (Spor Toto Teşkilat Başkanlığı,
24/05/2021 tarih ve 40 sayılı karar). HTTPS'te sahte sertifika, HTTP'de engel sayfası
dönüyor. Bu repo, dosyaları Türkiye dışındaki bir GitHub runner'ında indirip saklar;
böylece `raw.githubusercontent.com` üzerinden okunabilir hale gelir.

Yapılan iş scraping değil, yayımlanmış dosyaların indirilmesidir. Veri kaynağı
football-data.co.uk'tir ve tüm hakları onlara aittir.

## Yapı

```
data/fd/<sezon>/<lig>.csv     ör. data/fd/2526/T1.csv
```

Sezon kodu football-data.co.uk biçimindedir: `2526` = 2025-2026.

Ligler: T1 (Süper Lig), E0, E1, SP1, D1, I1, F1, N1, P1, B1, G1, SC0.

## Kullanım

```
https://raw.githubusercontent.com/<kullanici>/futbol-veri-aynasi/main/data/fd
```

adresini tüketen uygulamada `FD_MIRROR_BASE` olarak tanımlayın.

## Güncelleme

`.github/workflows/mirror-football-data.yml` her gün 05:17 UTC'de çalışır.
Geçmiş sezonları doldurmak için Actions sekmesinden elle tetikleyip
sezon kodlarını boşlukla ayırarak girin (ör. `1920 2021 2122`).

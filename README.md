# Modern Yedek Update Feed

Bu repo Modern Yedek uygulamasinin otomatik guncelleme akisi icindir.

Dosyalar:

- `MYedekSetup.exe`: Son kullanici installer dosyasi. Calistiginda `latest.json` dosyasindan en guncel release ZIP'ini indirir, SHA256 ile dogrular ve kurar.
- `latest.json`: Uygulamanin acilista okudugu manifest.
- `releases/ModernYedek-*.zip`: Publish klasorunden uretilen uygulama paketleri.

Manifest URL:

```txt
https://raw.githubusercontent.com/kul72107/Yedek-app/main/latest.json
```

Yeni patch yayinlama:

1. Ana uygulamada version artir.
2. Release publish al.
3. `publish/ModernYedek/*` icerigini ZIP yap.
4. ZIP SHA256 hashini hesapla.
5. ZIP'i `releases/` altina koy.
6. `latest.json` icindeki `version`, `url`, `sha256`, `notes` alanlarini guncelle.
7. Commit ve push yap.

`mandatory: true` olursa uygulama guncellemeden devam etmez.

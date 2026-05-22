# ⚔️ KatanaFlow: Quantitative Trend Analysis System

![Pine Script](https://img.shields.io/badge/Language-Pine%20Script%20v6-blue)
![Platform](https://img.shields.io/badge/Platform-TradingView-black)
![Type](https://img.shields.io/badge/Category-Algorithmic%20Trading-success)

<img width="2030" height="1180" alt="image" src="https://github.com/user-attachments/assets/7279da93-3479-4793-8cfb-b3f8d78cab0c" />
<img width="2037" height="1176" alt="image" src="https://github.com/user-attachments/assets/3053b322-18f4-4ab2-a560-ab9cd37bb1bd" />

> *Figure 1: KatanaFlow executing a trend reversal signal in Expert Mode.*

# 📈 KatanaFlow - TradingView İndikatörü

Teknik analiz çalışırken klasik hareketli ortalamaların (Moving Average) gecikmeli ve hatalı sinyallerinden sıkıldığım için Pine Script ile geliştirdiğim bir TradingView indikatörüdür. 

Temelde "Twin Range Filter" (TRF) matematiğini kullanarak piyasadaki gereksiz gürültüyü (küçük fiyat dalgalanmalarını) filtrelemeyi ve daha temiz trend dönüş sinyalleri yakalamayı amaçlar.

## ✨ Öne Çıkan Özellikler

* **Repaint Yapmaz:** Bir indikatörde en sinir bozucu şey sinyalin sonradan kaybolmasıdır. KatanaFlow'da mum (bar) kapandığında ekrana basılan KATA Long / Short sinyalleri kalıcıdır. Bu sayede geçmişe dönük (backtest) analizleri güvenle yapılabilir.
* **Twin Range Filter (TRF):** Çift yumuşatılmış dalgalanma filtresi kullanır. Fiyatın ortalamadan sapmasını hesaplayarak sahte kırılımları eler.
* **İkili Görünüm Modu:**
  * *Temel Mod:* Grafiği kalabalıklaştırmamak için sadece al/sat sinyallerini gösterir.
  * *Uzman Mod:* Arka planda çalışan dinamik destek/direnç bantlarını ve trend çizgilerini de ekrana yansıtır.
* **Bot Otomasyonu:** Algoritmik trade ile uğraşanlar için `alertcondition()` fonksiyonları eklidir; 3Commas veya kendi yazdığınız Python botlarına webhook ile alarm gönderebilirsiniz.

## 🛠️ Nasıl Kullanılır?

1. Bu repodaki `KatanaFlow.pine` dosyasının içindeki kodun tamamını kopyalayın.
2. TradingView'ı açın ve alt kısımdaki **Pine Editör** sekmesine gelin.
3. Kodu yapıştırın ve **"Grafiğe Ekle"** (Add to Chart) butonuna basın.

## 🎛️ Ayarlar Ne İşe Yarar?

İndikatörün ayarlar penceresinden kendi stratejinize göre şu değişiklikleri yapabilirsiniz:
- **Fast Period (Hızlı Periyot):** Kısa vadeli dalgalanma hassasiyetini ayarlar. Sayıyı küçültürseniz daha çok (ama daha riskli) sinyal alırsınız.
- **Slow Period (Yavaş Periyot):** Uzun vadeli ana trendin temelini belirler.
- **Multiplier (Çarpan):** Hatalı sinyalleri (Fakeout) engellemek için filtre bandının genişliğini ayarlar.

---
*Not: Bu proje tamamen kişisel gelişim ve eğitim amacıyla yazılmıştır. Finansal piyasalar risk içerir, buradaki sinyaller yatırım tavsiyesi (YTD) değildir.*

**Geliştiren:** Hasan Mert Yavuz - *Bilgisayar Mühendisliği Öğrencisi*

[![KatanaFlow Analysis](https://img.youtube.com/vi/z4b2ntVZgUw/0.jpg)](https://www.youtube.com/watch?v=z4b2ntVZgUw)

> *Note: The video walkthrough provides a comprehensive overview of the signal logic.*

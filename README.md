# React Native ile API Tabanlı E-Ticaret Uygulaması (`eticaret-lab`)

Bu proje, **Karabük Üniversitesi Yazılım Mühendisliği - Mobil Programlama** dersi laboratuvar çalışması kapsamında **React Native**, **Expo** ve **Expo Router** kullanılarak geliştirilmiş üç sayfalı bir mobil e-ticaret uygulamasıdır.

- **Öğrenci:** ABDLLH ALDAIEF (Abdullah Aldaief)
- **Öğrenci No:** 2210238506

---

## Uygulama Özellikleri

1. **Ürün Listeleme ve Arama (`app/index.js`):**
   - [DummyJSON Products API](https://dummyjson.com/products) üzerinden gerçek ürün verileri `fetch` ve `async/await` kullanılarak çekilir.
   - `TextInput` ile gerçek zamanlı ürün arama (`/products/search?q=...`) yapılabilir.
   - Üst kısımdaki sepet butonunda sepetteki toplam ürün adedi (`Sepetim (X)`) dinamik olarak gösterilir.

2. **Yeniden Kullanılabilir Ürün Kartı (`components/UrunKarti.js`):**
   - Her ürün için ürün görseli, başlığı, fiyatı ve kullanıcı puanı (`rating`) `props` aracılığıyla aktarılır ve listelenir.

3. **Dinamik Ürün Detay Sayfası (`app/urun/[id].js`):**
   - Expo Router dinamik rota parametresi (`useLocalSearchParams`) kullanılarak seçilen ürünün detayları görüntülenir.
   - API'den gelen `discountPercentage` değeri ile ürünün indirim oranı ve indirimli fiyatı hesaplanarak gösterilir.
   - `React Fragment` (`<>...</>`) yapısı ile ekran başlığı ve içerik bir arada sunulur.

4. **Context API ile Sepet Yönetimi (`context/SepetContext.js` & `app/sepet.js`):**
   - Tüm ekranlar arasında ortak sepet durumu (`state`) `createContext`, `useContext` ve özel `useSepet` Hook'u ile yönetilir.
   - Sepete ürün ekleme, ürün silme, ürün adedini artırma/azaltma ve toplam tutarı (`reduce`) hesaplama işlemleri desteklenir.

---

## Proje Klasör Yapısı

```text
eticaret-lab/
├── app/
│   ├── _layout.js       # Stack navigasyon ve SepetProvider yapılandırması
│   ├── index.js         # Ana sayfa (Ürün listesi ve arama)
│   ├── sepet.js         # Sepet ekranı
│   └── urun/
│       └── [id].js      # Dinamik ürün detay ekranı
├── components/
│   └── UrunKarti.js     # Yeniden kullanılabilir ürün kartı bileşeni
├── context/
│   └── SepetContext.js  # Context API tabanlı global sepet yönetimi
├── app.json
└── package.json
```

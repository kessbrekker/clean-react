# shadcn/ui (Radix + Tailwind) Kapsamlı Kullanım Rehberi

shadcn/ui, geleneksel bir component kütüphanesi değil; kopyala-yapıştır mantığıyla çalışan, projenize doğrudan dahil olan ve üzerinde tam kontrol sahibi olduğunuz bir **bileşen koleksiyonudur.** Radix UI'ın erişilebilirlik gücünü ve Tailwind CSS'in esnekliğini birleştirir.

---

## 1. Temel Kurulum ve Mimari

shadcn/ui'ı her projede (Next.js, Vite, Remix vb.) standart bir yapıyla kurmak, sürdürülebilirliği artırır.

### Kurulum (CLI)
```bash
pnpm dlx shadcn@latest init
```
Bu komut `components.json` dosyasını oluşturur ve `src/components/ui` klasörünü hazırlar. UI bileşenleri buraya iner; sizin yazdığınız iş mantığı içeren bileşenler ise `src/components/` altında kalmalıdır.



---

## 2. Proje Türlerine Göre Stratejik Kullanım

### A. E-Ticaret Projeleri (Dinamik ve Veri Odaklı)
E-ticaret sitelerinde kullanıcı etkileşimi ve hız kritiktir.

* **Sepet Deneyimi (`Sheet`):** Sağdan açılan (Drawer/Sheet) bir sepet yapısı için `Sheet` bileşenini kullanın.
* **Ürün Filtreleme (`Slider` & `Checkbox`):** Fiyat aralığı için Radix tabanlı `Slider`, kategoriler için `Checkbox` idealdir.
* **Ürün Görselleri (`Carousel`):** Ürün detay sayfasında kaydırılabilir alanlar için shadcn/ui'ın Embla Carousel tabanlı bileşenini ekleyin.
* **Sipariş Takibi (`DataTable`):** TanStack Table ile entegre olan `DataTable` bileşeni, binlerce siparişi filtrelemek ve sıralamak için en güçlü araçtır.

### B. Kurumsal ve Tanıtım Siteleri (Estetik ve Bilgi Odaklı)
Landing page yapılarında görsel hiyerarşi ve SSS bölümleri öne çıkar.

* **SSS (FAQ) Bölümü (`Accordion`):** Yer kaplamayan, temiz bir soru-cevap alanı için.
* **Harekete Geçirici Mesaj (CTA) (`Button`):** Shadcn'in `variant` yapısını kullanarak `outline`, `ghost` veya `destructive` butonlar oluşturun.
* **Navigasyon (`NavigationMenu`):** Karmaşık dropdown menüler ve "Mega Menu" yapıları için Radix'in erişilebilir menü yapısını kullanın.

### C. Blog ve İçerik Platformları (Okunabilirlik Odaklı)
İçerik yoğun projelerde tipografi ve yükleme hızları önemlidir.

* **Yazar Kartları (`Avatar`):** Yazarların profil fotoğraflarını placeholder desteğiyle sunar.
* **Okuma Süresi & Etiketler (`Badge`):** İçerik kategorilerini ve metadataları şık bir şekilde gösterir.
* **Yükleme Durumları (`Skeleton`):** İçerik yüklenirken "layout shift" olmaması için içerik bloklarının taslağını gösterin.

---

## 3. Özelleştirme ve Temalandırma (Best Practices)

shadcn/ui'ın en büyük avantajı, stilin `globals.css` içindeki **CSS Variables** üzerinden yönetilmesidir.

### Renk Paletini Değiştirme
`themes` kısmından projenin kurumsal renklerini `primary`, `secondary`, `accent` gibi değişkenlere atayın:

```css
@layer base {
  :root {
    --primary: 221.2 83.2% 53.3%; /* Marka rengi */
    --radius: 0.5rem;
  }
}
```

### Component Seviyesinde Değişiklik
`src/components/ui/button.tsx` dosyasını açıp doğrudan Tailwind class'larını değiştirebilirsiniz. Bu, kütüphaneyi "fork" etmek gibidir; kütüphane size değil, siz kütüphaneye hükmedersiniz.

---

## 4. Gelişmiş İpuçları

1.  **Form Yönetimi:** `Form` bileşeni `react-hook-form` ve `zod` ile tam uyumludur. Client-side validation için mutlaka bu üçlüyü kullanın.
2.  **Erişilebilirlik:** Radix UI alt yapısı sayesinde klavye navigasyonu ve ekran okuyucu desteği (ARIA) otomatik gelir. Bileşenleri modifiye ederken bu yapıları bozmamaya özen gösterin.
3.  **Performans:** Sadece kullandığınız bileşenleri `pnpm dlx shadcn@latest add [component-name]` ile projenize ekleyin. Tüm kütüphaneyi yükleyerek bundle size'ı şişirmemiş olursunuz.

---

## 5. Bakım ve Güncelleme
shadcn/ui bir paket olmadığı için `npm update` ile güncellenmez. Yeni sürümleri takip etmek için:
* CLI'ı kullanarak mevcut bileşeni üzerine yazdırabilir (dikkat: manuel değişiklikleriniz silinebilir) 
* Veya shadcn/ui dökümantasyonundaki yeni kodları kopyalayıp ilgili dosyaya yapıştırabilirsiniz.

Bu rehber, projenizin türü ne olursa olsun başlangıçtan yayına kadar shadcn/ui'ı en verimli şekilde kullanmanızı sağlayacaktır.

# SEO İçin Semantik HTML Rehberi

Semantik HTML, içeriğin sadece nasıl göründüğünü değil, ne anlama geldiğini hem tarayıcılara hem de arama motoru botlarına (Googlebot gibi) anlatan yapısal bir dildir. Doğru bir semantik yapı, sitenizin taranabilirliğini artırır ve sıralamanıza doğrudan katkı sağlar.

---

## 1. Doküman Yapısı ve Metadata (`<head>`)

Arama motorlarının ilk baktığı yer burasıdır. Sayfanın kimliğini burada tanımlarsınız.

*   **`<title>`**: Sayfanın en önemli SEO etiketidir. Anahtar kelimeyi içermeli ve 60 karakteri geçmemelidir.
*   **`<meta name="description">`**: Arama sonuçlarında sayfanın altında görünen özettir.
*   **`<link rel="canonical">`**: Yinelenen içerik sorununu önlemek için sayfanın "asıl" versiyonunu belirtir.

---

## 2. Sayfa Düzeni Etiketleri (Layout)

Bu etiketler, sayfanın bölümlerini mantıksal olarak ayırır.

*   **`<header>`**: Sayfanın veya bir bölümün giriş kısmıdır. Genellikle logo, site ismi ve ana navigasyonu içerir.
*   **`<nav>`**: Ana menü ve navigasyon bağlantıları için kullanılır. Google bu alanı sitenizin haritasını anlamak için kullanır.
*   **`<main>`**: Sayfanın **ana ve özgün** içeriğini kapsar. Her sayfada yalnızca bir tane bulunmalıdır.
*   **`<footer>`**: Sayfa altı bilgilerini (iletişim, telif hakkı, sosyal medya linkleri) içerir.

---

## 3. İçerik Hiyerarşisi ve Bölümleme

İçeriğinizi parçalara ayırırken şu yapıyı kullanmalısınız:

### Başlık Etiketleri (`<h1>` - `<h6>`)
Başlıklar bir ağaç yapısı gibi olmalıdır.
*   **`<h1>`**: Sayfanın ana başlığıdır. Her sayfada **sadece bir adet** olmalıdır.
*   **`<h2>` - `<h6>`**: Alt başlıklar. `<h2>`'den sonra doğrudan `<h4>`'e geçilmemeli, hiyerarşi korunmalıdır.

### Bölümleme Etiketleri
*   **`<section>`**: Tematik olarak birbirine bağlı içerik gruplarını ifade eder (Örn: "Hizmetlerimiz" bölümü).
*   **`<article>`**: Kendi başına anlam ifade eden, bağımsız içeriklerdir (Blog yazıları, haberler, forum mesajları).
*   **`<aside>`**: Ana içerikle dolaylı yoldan ilgili olan yan içeriklerdir (Sidebar, reklamlar, ilgili yazılar).



---

## 4. Metin ve Medya Semantiği

*   **`<p>`**: Metin paragrafları için kullanılır.
*   **`<ul>` / `<ol>` / `<li>`**: Listeler. Google, liste yapısındaki içerikleri (özellikle "nasıl yapılır" içeriklerini) sever ve "Öne Çıkan Snippet" olarak gösterebilir.
*   **`<strong>`**: Metnin önemli olduğunu belirtir (SEO açısından anahtar kelimeleri vurgulamak için kullanılır).
*   **`<em>`**: Vurgulanması gereken yerleri belirtir.
*   **`<figure>` ve `<figcaption>`**: Görselleri ve onlara ait açıklamaları gruplamak için kullanılır.

---

## 5. SEO İçin Kritik Nitelikler

Semantik etiketlerin içinde kullanılan bazı öznitelikler hayati önem taşır:

*   **`alt` (img içinde)**: Görselin ne olduğunu metin olarak anlatır. Görsel aramalarında çıkmanızı sağlar.
*   **`href` (a içinde)**: Bağlantının nereye gittiğini belirtir.
*   **`rel="nofollow"`**: Güvenmediğiniz veya otoritenizi devretmek istemediğiniz dış linkler için kullanılır.

---

## Örnek Bir Semantik Yapı
```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <title>SEO Rehberi: Semantik HTML Nedir?</title>
    <meta name="description" content="Semantik HTML etiketleri ile sitenizi Google dostu yapın.">
</head>
<body>
    <header>
        <nav>
            <!-- Ana Menü -->
        </nav>
    </header>

    <main>
        <article>
            <h1>Semantik HTML'in SEO Üzerindeki Etkisi</h1>
            <section>
                <h2>Başlık Etiketlerinin Kullanımı</h2>
                <p>Doğru hiyerarşi kurmak SEO için kritiktir...</p>
            </section>
            
            <figure>
                <img src="seo-yapisi.jpg" alt="Semantik HTML şeması">
                <figcaption>Şekil 1: Sayfa yapısı örneği.</figcaption>
            </figure>
        </article>

        <aside>
            <h3>Benzer Yazılar</h3>
            <!-- Yan İçerik -->
        </aside>
    </main>

    <footer>
        <p>&copy; 2024 SEO Uzmanı</p>
    </footer>
</body>
</html>
```

# Jekyll Portfolyo & Blog Teması (Catppuccin Stili)

[![Lisans: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Jekyll için Catppuccin Mocha teması ve Tailwind CSS ile stillendirilmiş, duyarlı, iki dilli (İngilizce varsayılan & Türkçe) bir portfolyo ve blog temasıdır. Kolayca özelleştirilebilmesi ve GitHub Pages üzerinde yayınlanabilmesi için oluşturulmuştur.

[Demoyu Görüntüle](https://sahinmuhammetabdullah.github.io/portfolio/tr/) <!-- Kendi demo linkinizle değiştirin -->
| [English Documentation (İngilizce Açıklama)](#english-documentation-i̇ngilizce-açıklama) <!-- README.md'ye link -->

## ✨ Özellikler

*   **İki Dil Desteği:** Jekyll Polyglot kullanarak içeriği kolayca İngilizce (varsayılan) ve Türkçe olarak yönetin.
*   **Duyarlı Tasarım:** Masaüstü, tablet ve mobil cihazlarda harika görünür.
*   **Catppuccin Mocha Teması:** Güzel, dinlendirici koyu tema.
*   **Tailwind CSS:** Kolay özelleştirme için yardımcı program öncelikli CSS çatısı.
*   **Proje Vitrini:** Projelerinizi modal içinde detaylarıyla sergilemek için özel bölüm.
    *   Proje kartları için kapak görselleri (renk gradyanlarına geri dönüş).
    *   Modallar içinde zengin metin ve görsellere izin veren proje açıklamaları için Markdown desteği.
*   **Font Awesome İkonları:** Sosyal medya bağlantıları ve proje kartı ikonları için.
*   **SEO Optimize Edilmiş:** `jekyll-seo-tag` ile.
*   **RSS Beslemesi:** `jekyll-feed` ile.
*   **Site Haritası:** `jekyll-sitemap` ile.
*   **Özelleştirilebilir Veri Dosyaları:** Profil bilgilerini, sosyal bağlantıları, navigasyonu ve arayüz metinlerini `_data` dizinindeki YAML dosyaları aracılığıyla kolayca güncelleyin.
*   **GitHub Pages Hazır:** Otomatik dağıtım için bir GitHub Actions iş akışı içerir.

## 🚀 Başlarken

Bu talimatlar, projenin bir kopyasını geliştirme ve test amaçlı olarak yerel makinenizde çalıştırmanıza veya kendi versiyonunuzu dağıtmanıza yardımcı olacaktır.

### Ön Gereksinimler

*   **Ruby:** [Sürümü kontrol edin](https://www.ruby-lang.org/en/documentation/installation/) (Jekyll gereksinimi, örn: 3.0.x)
*   **Bundler:** (`gem install bundler`)
*   **Jekyll:** (`gem install jekyll`)
*   (İsteğe Bağlı) Tailwind CSS'i kapsamlı bir şekilde özelleştirmeyi ve yerel olarak build etmeyi planlıyorsanız Node.js ve npm/yarn. Şu anda bu tema, basitlik için Tailwind CSS CDN'ini kullanmaktadır.

### Kurulum ve Yerel Geliştirme

1.  **Depoyu Forklayın veya Klonlayın:**
    ```bash
    git clone https://github.com/SahinMuhammetAbdullah/portfolio.git
    cd portfolio
    ```

2.  **Bağımlılıkları Yükleyin:**
    ```bash
    bundle install
    ```

3.  **Siteyi Yerelde Çalıştırın:**
    ```bash
    bundle exec jekyll serve --livereload
    ```
    Siteniz şimdi `http://localhost:4000` adresinde çalışıyor olmalıdır. `--livereload` bayrağı, değişiklik yaptığınızda sayfayı otomatik olarak yenileyecektir. Varsayılan olarak İngilizce versiyonu sunacaktır.
    *   Türkçe versiyonu görüntülemek için: `http://localhost:4000/tr/`

### Dağıtım

Bu depo, `main` dalına push yaptığınızda siteyi otomatik olarak oluşturan ve GitHub Pages'a dağıtan bir GitHub Actions iş akışı (`.github/workflows/deploy.yml`) içerir.

1.  GitHub Pages için depo ayarlarınızın kaynak olarak "GitHub Actions" kullanacak şekilde yapılandırıldığından emin olun.
2.  `_config.yml` dosyasındaki `url` ve `baseurl` ayarlarını GitHub Pages URL'nizle eşleşecek şekilde güncelleyin (örn: `url: https://kullaniciadiniz.github.io`, `baseurl: /depo-adiniz`).

## 🛠️ Özelleştirme

Çoğu özelleştirme, `_data` dizinindeki YAML dosyalarını ve içerik için Markdown dosyalarını düzenleyerek yapılabilir.

*   **Site Yapılandırması (`_config.yml`):**
    *   `title`, `author`, `description`, `email`
    *   `url`, `baseurl` (DAĞITIM İÇİN KRİTİK)
    *   `github_username`
    *   Jekyll Polyglot ayarları: `languages`, `default_lang`, `default_lang_in_url`
    *   PWA için tema renkleri: `theme_color`, `background_color`, `ms_tile_color`
    *   Footer için: `technologies_used`, `license_name`, `license_url`, `repository_url`, `designer_name`, `designer_url`.

*   **Profil Bilgileri (`_data/profile.yml`):**
    *   `tagline`, `greeting_intro`, `about_title`, `about_bio`, `skills` ve `footer_copyright` şablonu gibi dile özgü profil detaylarını içerir.
    *   `avatar` yolunuzu burada güncelleyin.

*   **Navigasyon Bağlantıları (`_data/navigation.tr.yml`, `_data/navigation.en.yml`):**
    *   Her dil için ana navigasyon bağlantılarını (başlık ve URL) tanımlayın.

*   **Arayüz Metinleri (`_data/translations.yml`):**
    *   Tüm genel arayüz metinlerini (bölüm başlıkları, buton etiketleri vb.) kendi dil anahtarları altında hem `tr` hem de `en` için içerir.

*   **Sosyal Bağlantılar (`_data/social.yml`):**
    *   Sosyal medya bağlantılarınızı `name`, `url` ve `icon_class` (Font Awesome) dahil olmak üzere tanımlayın.

*   **Projeler (`_projects/`):**
    *   `_projects` içinde `tr` ve `en` adında alt klasörler oluşturun.
    *   Her proje için her iki dil klasöründe de bir `.md` dosyası oluşturun (örn: `_projects/tr/projem.md` ve `_projects/en/projem.md`).
    *   Front matter'daki `id` alanının bir projenin her iki dil versiyonu için de AYNI olduğundan emin olun.
    *   `title`, `short_description`, `tags`, `cover_image`, `icon_class`, `github_url`, `live_url` alanlarını özelleştirin.
    *   Front matter'dan (---) sonraki içerik, projenin modal içinde görünen detaylı açıklaması için Markdown'dır. Buraya Markdown sözdizimiyle görseller ekleyebilirsiniz: `![Alt metin]({{ '/assets/images/gorseliniz.jpg' | relative_url }})`.

*   **Stil Dosyaları (`assets/css/style.css`):**
    *   Özel CSS, modal içindeki Markdown'dan üretilen HTML için stiller ve kaydırma çubuğu stillerini içerir.
    *   Tailwind CSS öncelikle CDN aracılığıyla kullanılır, ancak buraya override'lar veya yeni stiller ekleyebilirsiniz.

*   **Faviconlar:**
    *   Favicon dosyalarınızı (örn: `favicon.ico`, `apple-touch-icon.png`, çeşitli `favicon-*.png`) `assets/images/favicons/` içine yerleştirin.
    *   `_includes/head.html` ve `manifest.json` (eğer kök dizinden taşıdıysanız) içindeki yolları güncelleyin.
    *   Kök dizindeki `manifest.json` dosyası PWA benzeri özellikleri yapılandırır. Yolların doğru olduğundan emin olun.

## 🤝 Katkıda Bulunma

Katkılarınızı bekliyoruz! Bu temayı geliştirmek için önerileriniz varsa, çekinmeyin:
1.  Projeyi Forklayın
2.  Özellik Dalınızı Oluşturun (`git checkout -b feature/HarikaOzellik`)
3.  Değişikliklerinizi Commit Edin (`git commit -m 'HarikaOzellik Eklendi'`)
4.  Dala Push Edin (`git push origin feature/HarikaOzellik`)
5.  Bir Pull Request Açın

## 📜 Lisans

Bu proje **{{ site.license_name | default: "MIT Lisansı" }}** altında lisanslanmıştır. Daha fazla detay için [LICENSE](LICENSE) dosyasına bakın.

## 🙏 Teşekkürler

*   [Jekyll](https://jekyllrb.com/)
*   [Jekyll Polyglot](https://github.com/untra/jekyll-polyglot)
*   [Tailwind CSS](https://tailwindcss.com/)
*   [Font Awesome](https://fontawesome.com/)
*   [Catppuccin Tema Paleti](https://github.com/catppuccin/catppuccin)
*   Adınız (tasarımcı olarak - eğer `{{ site.designer_name }}` kullanırsanız `_config.yml`'den otomatik olarak alınacaktır)

---
## English Documentation (İngilizce Açıklama)

For the English user guide and documentation for this project, please see the [README.md](README.md) file.
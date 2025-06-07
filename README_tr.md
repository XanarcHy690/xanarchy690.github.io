# Jekyll Portfolyo & Blog Teması (Catppuccin Stili)
[![License: CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)
<!-- GitHub Actions İş Akışı Durum Rozeti - KULLANICIADINIZ ve DEPOADINIZ ile değiştirin -->
<!-- ![GitHub Actions İş Akışı Durumu](https://img.shields.io/github/actions/workflow/status/KULLANICIADINIZ/DEPOADINIZ/jekyll.yml?branch=main&logo=github) -->

Jekyll için Catppuccin Mocha teması ve Tailwind CSS ile stillendirilmiş, duyarlı, çok dilli bir portfolyo ve blog temasıdır. Kolayca özelleştirilebilmesi ve GitHub Actions kullanılarak GitHub Pages üzerinde yayınlanabilmesi için oluşturulmuştur. Bu tema başlangıçta İngilizce (varsayılan) ve Türkçe için yapılandırılmıştır, ancak daha fazla dili destekleyecek şekilde genişletilebilir.

[Demoyu Görüntüle](https://sahinmuhammetabdullah.github.io/portfolio/) <!-- Kendi demo linkinizle değiştirin -->
| [English Documentation (İngilizce Açıklama)](README.md)

## ✨ Özellikler

*   **Çoklu Dil Desteği:** Jekyll Polyglot kullanarak içeriği birden çok dilde kolayca yönetin. İngilizce (varsayılan) ve Türkçe için kutudan çıktığı gibi yapılandırılmıştır, daha fazlası için genişletilebilir.
*   **Duyarlı Tasarım:** Masaüstü, tablet ve mobil cihazlarda harika görünür.
*   **Catppuccin Mocha Teması:** Güzel, dinlendirici koyu tema.
*   **Tailwind CSS (CDN):** CDN aracılığıyla kolay özelleştirme için yardımcı program öncelikli CSS çatısı.
*   **Proje Vitrini:** Projelerinizi modal içinde detaylarıyla sergilemek için özel bölüm.
    *   Proje kartları için kapak görselleri (renk gradyanlarına geri dönüş).
    *   Modallar içinde zengin metin ve görsellere izin veren proje açıklamaları için Markdown desteği.
*   **Font Awesome İkonları:** Sosyal medya bağlantıları ve proje kartı ikonları için.
*   **SEO Optimize Edilmiş:** `jekyll-seo-tag` ile.
*   **RSS Beslemesi:** `jekyll-feed` ile.
*   **Site Haritası:** `jekyll-sitemap` ile.
*   **Özelleştirilebilir Veri Dosyaları:** Profil bilgilerini, sosyal bağlantıları, navigasyonu ve arayüz metinlerini `_data` dizinindeki YAML dosyaları aracılığıyla her desteklenen dil için kolayca güncelleyin.
*   **GitHub Pages Hazır:** Otomatik oluşturma ve dağıtım için bir GitHub Actions iş akışı içerir.

## 🚀 Başlarken

Bu talimatlar, projenin bir kopyasını geliştirme ve test amaçlı olarak yerel makinenizde çalıştırmanıza veya kendi versiyonunuzu dağıtmanıza yardımcı olacaktır.

### Ön Gereksinimler

*   **Ruby:** [Sürümü kontrol edin](https://www.ruby-lang.org/en/documentation/installation/) (örn: 3.0.x, 3.1.x, `Gemfile` ve iş akışına göre)
*   **Bundler:** (`gem install bundler`)
*   **Jekyll:** (`gem install jekyll`)
*   (İsteğe Bağlı) Tailwind CSS'i yerel olarak kurmayı ve tüm yeteneklerini (örn: `@tailwindcss/typography` eklentisi) kullanmayı planlıyorsanız Node.js ve npm/yarn.

### Kurulum ve Yerel Geliştirme

1.  **Depoyu Forklayın veya Klonlayın:**
    ```bash
    git clone https://github.com/SahinMuhammetAbdullah/portfolio.git # Uygulanabilirse kendi fork'unuzla değiştirin
    cd portfolio
    ```

2.  **Bağımlılıkları Yükleyin:**
    Bu komut `Gemfile`'ı okur ve gerekli tüm Ruby gem'lerini yükler.
    ```bash
    bundle install
    ```

3.  **Siteyi Yerelde Çalıştırın:**
    Bu komut siteyi oluşturur ve yerel bir web sunucusu başlatır.
    ```bash
    bundle exec jekyll serve --livereload --baseurl ""
    ```
    *   Siteniz şimdi `http://localhost:4000/` adresinde çalışıyor olmalıdır.
    *   `--livereload` bayrağı, değişiklik yaptığınızda sayfayı otomatik olarak yeniler.
    *   `--baseurl ""` yerel geliştirme için `_config.yml`'deki `baseurl`'i geçersiz kılar, böylece linkler kök dizinden doğru çalışır.
    *   Varsayılan dil (İngilizce) `http://localhost:4000/` adresinde sunulacaktır.
    *   Diğer diller kendi yollarında olacaktır (örn: Türkçe: `http://localhost:4000/tr/`).

### ⚙️ GitHub Actions ile Oluşturma ve Dağıtım

Bu depo, önceden tanımlanmış bir **GitHub Actions iş akışı** kullanarak GitHub Pages'a kolay dağıtım için yapılandırılmıştır.

**Nasıl Çalışır:**

1.  **İş Akışı Dosyası:** Dağıtım süreci `.github/workflows/jekyll.yml` içinde tanımlanmıştır. Bu dosya, GitHub Actions'a Jekyll sitenizi nasıl oluşturacağını ve dağıtacağını söyler.
2.  **Tetikleyici:** İş akışı, `main` (veya `master`) dalınıza `push` yaptığınızda otomatik olarak tetiklenir.
3.  **Oluşturma Süreci:**
    *   GitHub Actions bir sanal ortam (Ubuntu) kurar.
    *   Deponuzun kodunu çeker.
    *   Ruby ortamını kurar ve `Gemfile`'ınızdaki tüm bağımlılıkları `bundle install` kullanarak yükler. Bu, `jekyll-polyglot` ve diğer özel eklentileri içerir.
    *   Ardından, statik sitenizi bir `_site` dizinine oluşturmak için `bundle exec jekyll build` komutunu çalıştırır. `_config.yml`'de yapılandırılan (veya `actions/configure-pages` tarafından belirlenen) `baseurl` burada kullanılır.
4.  **GitHub Pages'a Dağıtım:**
    *   `_site` dizininin içeriği bir "Pages artifact'i" olarak yüklenir.
    *   Bu artifact daha sonra GitHub Pages sitenize dağıtılır.

**Fork Edilen Depolar İçin Adımlar:**

Bu depoyu fork ettiyseniz ve kendi GitHub Pages'ınızda yayınlamak istiyorsanız:

1.  **`_config.yml`'i Güncelleyin:**
    *   `url` ayarını kendi GitHub Pages kök URL'nizle (örn: `https://kullaniciadiniz.github.io`) değiştirin.
    *   `baseurl` ayarını yapın:
        *   Eğer depo adınız `kullaniciadiniz.github.io` ise, `baseurl: ""` yapın.
        *   Eğer depo adınız `portfolyom` ise, `baseurl: "/portfolyom"` yapın.
    *   Diğer siteye özgü detayları (`title`, `author`, `email` vb.) güncelleyin.

2.  **GitHub Pages Kaynağını Yapılandırın:**
    *   Forkladığınız deponuzda **Ayarlar (Settings)** > **Sayfalar (Pages)** bölümüne gidin.
    *   "Oluşturma ve dağıtım (Build and deployment)" altında, **Kaynak (Source)** için **GitHub Actions**'ı seçin.
    *   Bu, GitHub Pages'a sitenizi kendisinin oluşturması yerine (ki bu `jekyll-polyglot` gibi özel eklentileri desteklemez) sizin `deploy.yml` iş akışınızın çıktısını kullanmasını söyler.

3.  **İlk Dağıtım Onayı (Gerekirse):**
    *   Bazen bir GitHub Actions iş akışı bir GitHub Pages ortamına ilk kez dağıtım yapmaya çalıştığında manuel bir onay gerekebilir.
    *   "Actions" sekmesindeki iş akışı çalışmanızda "Onay bekleniyor (Waiting for approval)" durumu veya "Dağıtımları gözden geçir (Review deployments)" butonu olup olmadığını kontrol edin. Varsa, devam etmek için onaylayın.

4.  **Değişiklikleri Push Edin:**
    *   Değişikliklerinizi (özellikle `_config.yml`'e yaptıklarınızı) `main` dalınıza commit edip push edin. Bu, GitHub Actions iş akışını tetikleyecek, sitenizi oluşturacak ve dağıtacaktır. Siteniz daha sonra Pages ayarlarınızda belirtilen URL'de canlı olmalıdır.

#### Sorun Giderme: Otomatik Dağıtım Çalışmıyorsa

GitHub Pages ayarlarınızı kaynak olarak "GitHub Actions" kullanacak şekilde yapılandırdıktan sonra, dağıtım iş akışınız (`.github/workflows/deploy.yml`) push işlemlerinde otomatik olarak tetiklenmiyorsa veya GitHub Pages hala kendi build işlemini yapmaya çalışıyor gibi görünüyorsa, Pages ortamı için iş akışını manuel olarak etkinleştirmeniz veya yeniden tetiklemeniz gerekebilir.

Siteniz özel GitHub Action'ınız aracılığıyla otomatik olarak dağıtılmıyorsa şu adımları izleyin:

1.  **GitHub Pages Ayarlarına Gidin:**
    *   Deponuzda **Ayarlar (Settings)** > **Sayfalar (Pages)** bölümüne gidin.
    *   "Oluşturma ve dağıtım (Build and deployment)" kaynağının **GitHub Actions** olarak ayarlandığından emin olun.

2.  **Pages İçin İş Akışı Çalıştırmalarına Erişin:**
    *   Eğer iş akışlarının etkinleştirilmesi gerektiğine veya sorunlar olduğuna dair bir gösterge varsa, **"İş akışı çalıştırmalarını görüntüle (View workflow runs)"** gibi bir mesaj veya bağlantı görebilirsiniz (Pages ayarlarıyla ilgili benzer bir ifade). Buna tıklayın.
    ![görsel](/assets/1.png)

3.  **İş Akışlarını Etkinleştirin:**
    *   GitHub Pages dağıtımı için iş akışlarını anladığınızı ve etkinleştirmek istediğinizi onaylamanızı isteyen bir sayfaya yönlendirilebilirsiniz.
    *   **"İş akışlarımı anlıyorum, devam et ve etkinleştir (I understand my workflows, go ahead and enable them)"** (veya benzer bir onay butonuna) tıklayın.
    ![görsel](/assets/2.png)

4.  **Dağıtım İş Akışını Manuel Olarak Çalıştırın:**
    *   Deponuzdaki **Eylemler (Actions)** sekmesine gidin.
    *   Sol kenar çubuğunda, dağıtım iş akışınızı bulun ve tıklayın (örn: **"Jekyll Site Build and GitHub Pages Deployment"** veya "Build and Deploy").
    ![görsel](/assets/3.png)
    *   Genellikle sağ tarafta bir **"İş akışını çalıştır (Run workflow)"** butonu görmelisiniz. Bu butona tıklayın.
    *   Hangi daldan çalıştırılacağını soran bir açılır menü görünebilir; ana dalınızı (örn: `main`) seçin ve yeşil renkli **"İş akışını çalıştır (Run workflow)"** butonuna tıklayın.
    ![görsel](/assets/4.png)

5.  **İş Akışı İsteğini Onaylayın:**
    *   İş akışını başarıyla tetikledikten sonra, **"İş akışı çalıştırması başarıyla istendi (Workflow run was successfully requested.)"** gibi bir onay mesajı görmelisiniz.
    ![görsel](/assets/5.png)
    *   Şimdi bu manuel olarak tetiklenen iş akışı çalıştırmasının ilerlemesini izleyebilirsiniz. Başarıyla tamamlandıktan sonra siteniz GitHub Pages'a dağıtılmalıdır.

Bu manuel tetikleme, genellikle GitHub Pages'ın özel iş akışınızı dağıtım süreciyle doğru bir şekilde ilişkilendirmesine yardımcı olur. Yapılandırılmış dalınıza sonraki push işlemleri, iş akışını otomatik olarak tetiklemelidir.


## 🛠️ Özelleştirme

*   **Site Yapılandırması (`_config.yml`):**
    *   `title`, `author`, `description`, `email`, `url`, `baseurl`, `github_username` güncelleyin.
    *   **Jekyll Polyglot:** `languages` (buraya yeni dil kodları ekleyin, örn: `["en", "tr", "fr"]`), `default_lang`, `default_lang_in_url`.
    *   Footer detayları: `technologies_used`, `license_name`, vb.

*   **Yeni Bir Dil Ekleme (örn: Fransızca "fr"):**
    1.  `_config.yml`'deki `languages` listesine `"fr"` ekleyin.
    2.  `_data/navigation.yml` oluşturun (`navigation.yml`'den `en:` kopyalayıp çevirin).
    3.  `_data/translations.yml` içinde, `fr:` bölümü ekleyip tüm arayüz metinlerini çevirin (`en:` bölümünden kopyalayıp çevirin).
    4.  `_data/profile.yml` içinde, `fr:` bölümü ekleyip profil detaylarını çevirin.
    5.  `_projects/en/` içindeki her proje için, `_projects/fr/` altında karşılık gelen bir dosya (örn: `_projects/fr/projem.md`) oluşturup içeriği çevirin. Front matter'daki `id` alanının aynı kaldığından emin olun.
    6.  Header'daki dil değiştirici otomatik olarak "fr"yi içerecektir.

*   **Profil, Navigasyon, Arayüz Metinleri, Sosyal Bağlantılar:** `_data` dizinindeki dosyaları düzenleyin (`profile.yml`, `navigation.xx.yml`, `translations.yml`, `social.yml`).

*   **Projeler (`_projects/`):**
    *   Her dil için alt klasörleri (örn: `en/`, `tr/`) koruyun.
    *   Proje `.md` dosyaları metadata için front matter (`id`, `title`, `cover_image`, `tags`, vb.) ve modal içindeki detaylı açıklama için Markdown kullanır.
    *   Aynı projenin farklı dil versiyonlarında `id`'nin tutarlı olduğundan emin olun.

*   **Stil Dosyaları (`assets/css/style.css`):** Özel CSS veya override'lar ekleyin.
*   **Faviconlar & Manifest:** `assets/images/favicons/` içindeki dosyaları ve kök dizindeki `manifest.json`'ı güncelleyin. `_includes/head.html` ve `manifest.json` içindeki yolların doğru olduğundan emin olun.

## 🤝 Katkıda Bulunma

Katkılarınızı bekliyoruz! Bu temayı geliştirmek için önerileriniz varsa, çekinmeyin:
1.  Projeyi Forklayın
2.  Özellik Dalınızı Oluşturun (`git checkout -b feature/HarikaOzellik`)
3.  Değişikliklerinizi Commit Edin (`git commit -m 'HarikaOzellik Eklendi'`)
4.  Dala Push Edin (`git push origin feature/HarikaOzellik`)
5.  Bir Pull Request Açın

## 📜 Lisans

Bu proje **CC BY 4.0 Lisansı** altında lisanslanmıştır. Daha fazla detay için [LICENSE](LICENSE) dosyasına bakın.

## 🙏 Teşekkürler

*   [Jekyll](https://jekyllrb.com/)
*   [Jekyll Polyglot](https://github.com/untra/jekyll-polyglot)
*   [Tailwind CSS](https://tailwindcss.com/)
*   [Font Awesome](https://fontawesome.com/)
*   [Catppuccin Tema Paleti](https://github.com/catppuccin/catppuccin)
*   Tasarım: **{{ site.designer_name }}**. Bu tema [Creative Commons Atıf 4.0 Uluslararası Lisansı](https://creativecommons.org/licenses/by/4.0/) ({{ site.license_url }}) altında lisanslanmıştır. Orijinal tasarımcı olarak **{{ site.designer_name }}**'e uygun şekilde atıfta bulunmanız şartıyla temayı kullanmakta, paylaşmakta ve uyarlamakta özgürsünüz. Bu genellikle footer'da veya benzer bir teşekkürler bölümünde "Tasarım..." kredisinin korunması anlamına gelir.

---
## English Documentation (İngilizce Açıklama)

For the English user guide and documentation for this project, please see the [README.md](README.md) file.
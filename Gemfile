# Gemfile
source "https://rubygems.org"

gem "jekyll", "~> 4.3.3" # Veya kullandığınız güncel Jekyll versiyonu
gem "jekyll-polyglot", "~> 1.8.1"
gem "jekyll-feed", "~> 0.17.0"
gem "jekyll-seo-tag", "~> 2.8.0"
gem "jekyll-sitemap", "~> 1.4.0"

group :test do
    gem "html-proofer"
end

# Windows'ta dosya izleme için (isteğe bağlı ama önerilir)
# :if yerine install_if kullanılıyor
gem 'wdm', '>= 0.1.0', install_if: Gem.win_platform?

# Ruby 3.4+ için gelecekte gerekebilecekler (şimdilik Jekyll bunları çekmeli)
# gem "csv"
# gem "base64"
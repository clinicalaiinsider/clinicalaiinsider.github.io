source "https://rubygems.org"

# Jekyll version
gem "jekyll", "~> 4.3"

# GitHub Pages compatibility (uncomment if deploying to GitHub Pages)
# gem "github-pages", group: :jekyll_plugins

# Plugins
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.17"
  gem "jekyll-seo-tag", "~> 2.8"
  gem "jekyll-sitemap", "~> 1.4"
end

# Windows and JRuby compatibility
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Performance booster for watching directories on Windows
gem "wdm", "~> 0.1", :platforms => [:mingw, :x64_mingw, :mswin]

# Lock http_parser.rb for JRuby builds
gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]

# Webrick for local development (Ruby 3.0+)
gem "webrick", "~> 1.8"

# Ruby 4.0+ compatibility (gems removed from stdlib)
gem "logger"
gem "csv"
gem "base64"
gem "bigdecimal"

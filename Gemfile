source "https://rubygems.org"

# Pinned to what GitHub Pages actually runs (see
# https://pages.github.com/versions/) rather than the full `github-pages`
# meta-gem, which pulls in every supported theme as a dependency and isn't
# needed here — this site uses no theme, just two plugins.
gem "jekyll", "3.10.0"
gem "kramdown-parser-gfm"

group :jekyll_plugins do
  gem "jekyll-seo-tag", "2.8.0"
  gem "jekyll-sitemap", "1.4.0"
end

# Ruby 3.4+ removed these from the standard library; Jekyll 3.x still needs
# them. Harmless no-ops on older Rubies where they're still built in.
gem "webrick"
gem "csv"
gem "base64"

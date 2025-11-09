source "https://rubygems.org"

# Use the GitHub Pages gem to keep dependency versions compatible with GitHub Pages.
# If you prefer to control Jekyll version yourself, replace this with `gem "jekyll", ">= 4.4"`
gem "github-pages", group: :jekyll_plugins

# Required on newer Rubies to provide WEBrick for `jekyll serve`
gem "webrick", "~> 1.8"

# Optional: add any gems you want outside the Jekyll plugins group here.

group :jekyll_plugins do
  gem "jekyll-paginate-v2"      # v2 pagination (replaces legacy jekyll-paginate)
  gem "jekyll-feed"             # RSS feed for posts
  gem "jekyll-seo-tag"          # SEO meta tags
  gem "jekyll-sitemap"          # sitemap.xml
  gem "jekyll-include-cache"    # cache includes
  gem "jekyll-remote-theme"     # use remote themes
  gem "jekyll-redirect-from"    # redirect_from support
end

# On Windows/JRuby include tzinfo-data
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo-data"
end

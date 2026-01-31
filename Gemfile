source "https://rubygems.org"

# Required for `jekyll serve` on Ruby 3.0+ (webrick was removed from the standard library)
gem "webrick"

# GitHub Pages uses the github-pages gem to pin Jekyll and plugins to compatible versions.
# Do not add explicit jekyll/minima/plugin versions here—they conflict with this gem.
gem "github-pages", group: :jekyll_plugins

# Windows and JRuby
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

gem "wdm", "~> 0.1", :platforms => [:mingw, :x64_mingw, :mswin]
gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]

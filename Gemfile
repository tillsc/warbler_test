source "https://rubygems.org"

# Bundle edge Rails instead: gem "rails", github: "rails/rails", branch: "main"
gem "rails", "~> 8.0.2"
# Use sqlite3 as the database for Active Record
platforms :jruby do
  gem "activerecord-jdbcsqlite3-adapter", '~>80.0', github: 'jruby/activerecord-jdbc-adapter'
end
platforms :ruby do
  gem "sqlite3", ">= 2.1"
end
# Use the Puma web server [https://github.com/puma/puma]
gem "puma", ">= 5.0"
# Build JSON APIs with ease [https://github.com/rails/jbuilder]
gem "jbuilder"

gem "warbler", github: "jruby/warbler", require: false

# Use Active Model has_secure_password [https://guides.rubyonrails.org/active_model_basics.html#securepassword]
# gem "bcrypt", "~> 3.1.7"

# Windows does not include zoneinfo files, so bundle the tzinfo-data gem
gem "tzinfo-data", platforms: %i[ windows jruby ]

# Use the database-backed adapters for Rails.cache and Active Job
#gem "solid_cache"
#gem "solid_queue"

# Deploy this application anywhere as a Docker container [https://kamal-deploy.org]
# gem "kamal", require: false

# Add HTTP asset caching/compression and X-Sendfile acceleration to Puma [https://github.com/basecamp/thruster/]
# gem "thruster", require: false

group :development do
  # Use console on exceptions pages [https://github.com/rails/web-console]
  gem "web-console"
end

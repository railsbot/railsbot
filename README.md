# Rails Starter

## Installation

Run `ruby -e "$(curl -s https://raw.githubusercontent.com/railsbot/railsbot/main/bin/new)"`

## Source Code

---

- `app/assets/javascripts/entrypoints/application.js` (TODO)

---

- `app/assets/stylesheets/application.scss` (TODO)

---

- `app/channels/application_cable/channel.rb` (TODO)

```ruby
# frozen_string_literal: true

module ApplicationCable
  class Channel < ActionCable::Channel::Base
  end
end
```

---

- `app/channels/application_cable/connection.rb` (TODO)

```ruby
# frozen_string_literal: true

module ApplicationCable
  class Connection < ActionCable::Connection::Base
  end
end
```

---

- `app/controllers/application_controller.rb`

```ruby
# frozen_string_literal: true

class ApplicationController < ActionController::Base
end
```

---

- `app/helpers/application_helper.rb`

```ruby
# frozen_string_literal: true

module ApplicationHelper
end
```

---

- `app/jobs/application_job.rb`

```ruby
# frozen_string_literal: true

class ApplicationJob < ActiveJob::Base
end
```

---

- `app/mailers/application_mailer.rb`

```ruby
# frozen_string_literal: true

class ApplicationMailer < ActionMailer::Base
  default from: ENV.fetch('MAILER_DEFAULT_FROM_ADDRESS', 'no-reply@example.com')
  layout 'mailer'
end
```

---

- `app/models/application_record.rb`

```ruby
# frozen_string_literal: true

class ApplicationRecord < ActiveRecord::Base
  self.abstract_class = true
end
```

---

- `app/views/layouts/application.html.erb`

```erb
<!DOCTYPE>
<html>
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <%= csrf_meta_tags %>
    <%= csp_meta_tag %>
    <title></title>
  </head>
  <body>
    <%= yield %>
  </body>
</html>
```

---

- `app/views/layouts/mailer.html.erb`

```erb
<!DOCTYPE>
<html>
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <style></style>
  </head>
  <body>
    <%= yield %>
  </body>
</html>
```

---

- `app/views/layouts/mailer.text.erb`

```erb
<%= yield %>
```

---

- `bin/rails`

```ruby
#!/usr/bin/env ruby
# frozen_string_literal: true

APP_PATH = File.expand_path('../config/application', __dir__)

require_relative '../config/boot'

require 'rails/commands'
```

---

- `bin/rake`

```ruby
#!/usr/bin/env ruby
# frozen_string_literal: true

require_relative '../config/boot'

require 'rake'

Rake.application.run
```

---

- `config/environments/development.rb`

```ruby
# frozen_string_literal: true

Rails.application.configure do
  config.eager_load = false
end
```

---

- `config/environments/production.rb`

```ruby
# frozen_string_literal: true

Rails.application.configure do
  config.eager_load = true
end
```

---

- `config/environments/test.rb`

```ruby
# frozen_string_literal: true

Rails.application.configure do
  config.eager_load = false
end
```

---

- `config/initializers/cookies.rb`

```ruby
# frozen_string_literal: true

Rails.application.config.action_dispatch.cookies_serializer = :json
```

---

- `config/initializers/inflections.rb`

```ruby
# frozen_string_literal: true

ActiveSupport::Inflector.inflections(:en) do |inflect|
  inflect.acronym 'API'
end
```

---

- `config/initializers/params.rb`

```ruby
# frozen_string_literal: true

ActiveSupport.on_load(:action_controller) do
  wrap_parameters format: [:json]
end

Rails.application.config.filter_parameters += [
  :_key,
  :certificate,
  :crypt,
  :otp,
  :passw,
  :salt,
  :secret,
  :ssn,
  :token
]
```

---

- `config/locales/en.yml`

```yaml
en:
```

---

- `config/application.rb`

```ruby
# frozen_string_literal: true

require_relative 'boot'

require 'rails'

require 'action_controller/railtie'
require 'active_model/railtie'
require 'action_view/railtie'
require 'active_record/railtie'

require 'action_cable/engine'
require 'active_job/railtie'
require 'action_mailer/railtie'
require 'active_storage/engine'

Bundler.require(*Rails.groups)

class Application < Rails::Application
  config.load_defaults 6.1
end
```

---

- `config/boot.rb`

```ruby
# frozen_string_literal: true

ENV['BUNDLE_GEMFILE'] ||= File.expand_path('../Gemfile', __dir__)

require 'bundler/setup'
require 'bootsnap/setup'
```

---

- `config/cable.yml`

```yaml
development:
  adapter: redis
  url: <%= ENV.fetch('REDIS_URL', 'redis://localhost:6379/1') %>

test:
  adapter: test

production:
  adapter: redis
  url: <%= ENV.fetch('REDIS_URL', 'redis://localhost:6379/1') %>
```

---

- `config/database.yml`

```yaml
default: &default
  adapter: sqlite3
  pool: <%= ENV.fetch('RAILS_MAX_THREADS', 5) %>
  timeout: 5000

development:
  <<: *default
  database: db/development.sqlite3

test:
  <<: *default
  database: db/test.sqlite3

production:
  <<: *default
  database: db/production.sqlite3
```

---

- `config/environment.rb`

```ruby
# frozen_string_literal: true

require_relative 'application'

Rails.application.initialize!
```

---

- `config/puma.rb`

```ruby
# frozen_string_literal: true

max_threads_count = ENV.fetch('RAILS_MAX_THREADS', 5)
min_threads_count = ENV.fetch('RAILS_MIN_THREADS', max_threads_count)

environment         ENV.fetch('RAILS_ENV', 'development')
pidfile             ENV.fetch('PIDFILE', 'tmp/pids/server.pid')
plugin              :tmp_restart
port                ENV.fetch('PORT', 3000)
threads             min_threads_count, max_threads_count
worker_timeout      3600 if ENV.fetch('RAILS_ENV', 'development') == 'development'
```

---

- `config/routes.rb`

```ruby
# frozen_string_literal: true

Rails.application.routes.draw do
end
```

---

- `config/storage.yml`

```yaml
local:
  service: Disk
  root: <%= Rails.root.join('storage') %>

test:
  service: Disk
  root: <%= Rails.root.join('tmp/storage') %>
```

---

- `db/seeds.rb`

```ruby
# frozen_string_literal: true
```

---

- `public/favicon.ico` (TODO)

---

- `spec/support/factory_bot.rb`

```ruby
# frozen_string_literal: true

RSpec.configure do |config|
  config.include FactoryBot::Syntax::Methods
end
```

---

- `spec/rails_helper.rb`

```ruby
# frozen_string_literal: true

require 'simplecov'

SimpleCov.start do
  coverage_dir 'tmp/coverage'
end

ENV['RAILS_ENV'] ||= 'test'

require File.expand_path('../config/environment', __dir__)

abort('The Rails environment is running in production mode!') if Rails.env.production?

require 'rspec/rails'

require 'spec_helper'

Dir[Rails.root.join('spec/support/**/*.rb')].sort.each { |file| require file }

begin
  ActiveRecord::Migration.maintain_test_schema!
rescue ActiveRecord::PendingMigrationError => e
  puts e.to_s.strip
  exit 1
end

RSpec.configure do |config|
  config.filter_rails_from_backtrace!
  config.fixture_path = "#{::Rails.root}/spec/fixtures"
  config.infer_spec_type_from_file_location!
  config.use_transactional_fixtures = true
end
```

---

- `spec/spec_helper.rb`

```ruby
# frozen_string_literal: true

RSpec.configure do |config|
  config.expect_with :rspec do |expectations|
    expectations.include_chain_clauses_in_custom_matcher_descriptions = true
  end

  config.mock_with :rspec do |mocks|
    mocks.verify_partial_doubles = true
  end

  config.shared_context_metadata_behavior = :apply_to_host_groups
end
```

---

- `.env`

```
MAILER_DEFAULT_FROM_ADDRESS=no-reply@example.com

PIDFILE=tmp/pids/server.pid

PORT=3000

RAILS_ENV=development
RAILS_MAX_THREADS=5
RAILS_MIN_THREADS=5

REDIS_URL=redis://localhost:6379/1
```

---

- `.gitignore`

```
/config/master.key
/db/*.sqlite*
/log/**
!/log/.keep
/node_modules/
/storage/**
!/storage/.keep
/tmp/**
!/tmp/cache/
!/tmp/cache/.keep
!/tmp/pids/
!/tmp/pids/.keep
!/tmp/storage/
!/tmp/storage/.keep
!/tmp/.keep
/.env
```

---

- `.rspec`

```
--require spec_helper
--format progress
```

---

- `.rubocop.yml` (TODO)

---

- `.ruby-version`

```
2.7.3
```

---

- `config.ru`

```ruby
# frozen_string_literal: true

require_relative 'config/environment'

run Rails.application

Rails.application.load_server
```

---

- `Gemfile`

```ruby
# frozen_string_literal: true

source 'https://rubygems.org'

gem 'bootsnap', '>= 1.4.4', require: false
gem 'pg', '~> 1.2'
gem 'puma', '~> 5.0'
gem 'rails', '~> 6.1.4'
gem 'redis', '~> 4.4'
gem 'sqlite3', '~> 1.4'

group :development do
  gem 'listen', '~> 3.3'
  gem 'web-console', '>= 4.1.0'
end

group :development, :test do
  gem 'factory_bot_rails', '~> 6.2'
  gem 'faker', '~> 2.18'
  gem 'pry', '~> 0.14.1'
  gem 'rspec-rails', '~> 5.0'
end

group :test do
  gem 'capybara', '>= 3.26'
  gem 'selenium-webdriver', '~> 3.142'
  gem 'simplecov', '~> 0.21.2', require: false
  gem 'webdrivers', '~> 4.6'
end
```

---

- `Rakefile`

```ruby
# frozen_string_literal: true

require_relative 'config/application'

Rails.application.load_tasks
```

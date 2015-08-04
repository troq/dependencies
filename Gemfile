gem 'mygemfiledep', '~> 4.0.0'

group :production do
  gem 'productiongemfiledep'
  group :test do
    gem 'test'
  end
  group :agroup, :development, optional: true do
    gem 'dev'

    group :randogroup do
      gem 'rando'
    end
  end
end

gem 'test2', :group => :test
gem 'test3', groups: [:randomgroup, :development]
gem 'rando2', :groups => [:randomgroup]

group :development do
  gem 'dev2'
end

platforms :rbx do
  gem 'rbxplatform'
end

on_heroku do
  gem 'heroku'
end

platforms :jruby do
  gem 'jrubyplatform'
  if ENV['AR_JDBC']
    gem 'if', github: 'jruby/activerecord-jdbc-adapter', branch: 'master'
    group :db do
      gem 'ifdb', github: 'jruby/activerecord-jdbc-adapter', branch: 'master'
      gem 'iftestdb', github: 'jruby/activerecord-jdbc-adapter', group: :test, branch: 'master'
    end
  else
    gem 'else', '>= 1.3.0'
    group :db do
      gem 'elsedb', '>= 1.3.0'
    end
  end
end

group :test do
  if true
    gem 'iftest'

    group :production do
      gem 'ifproduction'
    end
  end
end

def on_heroku
  if ENV['ON_HEROKU'] ||
     ENV['HEROKU_POSTGRESQL_ROSE_URL'] ||
     ENV['HEROKU_POSTGRESQL_GOLD_URL'] ||
     File.read(File.join(File.dirname(__FILE__), 'Procfile')) =~ /intended for Heroku/
    yield
  else
    # When not on Heroku, we still want our Gemfile.lock to include
    # Heroku specific gems, so we scope them to an unsupported
    # platform.
    platform :ruby_18, &proc
  end
end

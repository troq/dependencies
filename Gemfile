gem 'mygemfiledep', '~> 4.0.0'

group :production do
  gem 'productiongemfiledep'
  group :test do
    gem 'testgemfiledep'
  end
  group :agroup, :development, optional: true do
    gem 'devgemfiledep'
  end
end

gem 'testgemfiledep2', :group => :test
gem 'testgemfiledep3', groups: [:randomgroup, :development]

group :development do
  gem 'developmentgemfiledep'
end

gem 'mygemfiledep', '~> 4.0.0'

group :production do
  gem 'productiongemfiledep'
  group :test do
    gem 'testgemfiledep'
  end
  group :agroup, :development, optional: true do
    gem 'devgemfiledep'

    group :randogroup do
      gem 'randogemfiledep'
    end
  end
end

gem 'testgemfiledep2', :group => :test
gem 'testgemfiledep3', groups: [:randomgroup, :development]
gem 'randogemfiledep2', :groups => [:randomgroup]

group :development do
  gem 'developmentgemfiledep'
end

!SLIDE center

# Examples #

!SLIDE center

# Creating an Engine


!SLIDE left

# Foofah Engine

    foofah/app
    foofah/foofah.gemspec
    foofah/lib/foofah.rb
    foofah/lib/tasks

!SLIDE left small

## foofah.gemspec ##

    @@@ruby
    Gem::Specification.new do |s|
      s.platform    = Gem::Platform::RUBY
      s.name        = 'foofah'
      s.version     = '1.0'
      s.summary     = 'Special foofah gem for esting purposes'
      s.description = 'Description of foofah goes here'

      s.files        = Dir['LICENSE', 'README.md', 'app/**/*', 'config/**/*', 'lib/**/*']
      s.require_path = 'lib'
      s.requirements << 'none'

      # random dependency just for example
      s.add_dependency('will_paginate', '>= 3.0.pre')
    end

!SLIDE

## foofah.rb ##

    @@@ruby
    module Foofah
      class Engine < Rails::Engine
      end
    end

!SLIDE

## Gemfile ##

    @@@ruby
    gem 'foofah', '1.0', :path => 'foofah'

!SLIDE

# That's It #

!SLIDE commandline

# Lets Verify That We're Done #

    $ bundle list

    * abstract (1.0.0)
    * actionmailer (3.0.0)
    * actionpack (3.0.0)

    ...

    * foofah (1.0)

!SLIDE bullets incremental

# What About Migrations?

* Roll Your Own Rake Task

* For Now ...

!SLIDE

    @@@ruby
    #install.rake
    namespace :foofah do
      desc "Copies all migrations and assets"
      task :install do
        # rake foofah:install:migrations
        # rake foofah:install:assets
      end

      namespace :install do
        task :migrations do
          # copy migrations only
        end

        task :assets do
          # copy assets only
        end
      end
    end

!SLIDE

    $ rake foofah:install
    $ rake db:migrate



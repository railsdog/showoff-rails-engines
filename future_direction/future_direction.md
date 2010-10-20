!SLIDE center

# Future Direction

!SLIDE bullets incremental

# Rails 3.0 is Missing Some Features

* DIY Rake tasks for copying migrations
* Its a PITA to copy public assets

!SLIDE left

# Mountable Applications

    @@@ruby
    Rails.application.routes.draw do
      mount Foofah::Engine => "/foofah"
    end

    # example.org/foofah/articles

!SLIDE commandline

# Automagically Generated Rake Tasks

    $ rake foofah:install
    $ rake foofah:install:assets
    $ rake foofah:install:migrations

!SLIDE bullets incremental

# Serve Assets Directly from an Engine

* No need to copy assets to public directory
* Assets can be served out of the engines `public` directory
* This approach relies on rack-static
* You can also keep using the rake approach

!SLIDE left

    @@@ruby
    #lib/foofah.rb

    module Foofah
      class Engine < Rails::Engine
        config.asset_path = "/foofah/%s"
      end
    end

!SLIDE center

## Asset paths will be automatically modified inside the Engine:

    @@@ruby
    image_path("foo.jpg")

### same as ...

    @@@ruby
    "/foofah/images/foo.jpg"

!SLIDE center

# This is for Mountable Applications/Engines Only

!SLIDE bullets incremental

# You must mount the engine in order to:

* Have automagic rake tasks
* Load assets directly from your Engine via `ActionDispatch::Static`

!SLIDE bullets incremental

# Isolated Engine

* WTF?
* Interesting but ...
* Still Evolving

!SLIDE bullets incremental

# When Can I Have It?

* The future is now (on the "edge")
* Will be released as part of Rails 3.1
* December or January
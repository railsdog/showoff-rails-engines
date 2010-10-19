!SLIDE center

# Future Direction

!SLIDE bullets incremental

# Rails 3.0 is Missing Some Features

* DIY Rake tasks for copying migrations
* Its a PITA to copy public assets

!SLIDE bullets incremental

# Already Solved on "Edge"

* Will be available in Rails 3.1
* December or January

!SLIDE bullets incremental

# Automagically Generated Rake Tasks

    rake spree:install
    rake spree:install:assets
    rake spree:install:migrations

!SLIDE bullets incremental

# Serve Public Engine Assets

* No need to copy assets to public directory
* Assets can be served out of the engines `public` directory
* This approach relies on rack-static
* You can also keep using the rake approach

!SLIDE center

# Namespace vs. Isolated Engine

* TODO
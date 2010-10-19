!SLIDE bullets incremental

# Conflict Resolution

* Suppose there are two versions of something
* The main Rails application "wins"

!SLIDE center

# Customize a View or Layout

!SLIDE left

# Engine View

    @@@ruby
    # foofah/app/views/articles/index.html.erb

    Hello Foofah
    <%= t :test_message %>

!SLIDE left

# Custom View

    @@@ruby
    # app/views/articles/index.html.erb

    Hello Overrides
    <%= t :test_message %>

!SLIDE center

# Custom Locale

!SLIDE left

# Engine Locale

    @@@ruby
    # foofah/config/locales/en.yml

    en:
      test_message: "This is a message"

!SLIDE left

# Custom Locale

    @@@ruby
    # config/locales/en.yml

    en:
      test_message: "This is custom"

!SLIDE bullets incremental

# Peaceful Coexistence

* Rails application can have unrelated artifacts
* You can even override locales at the "key" level

!SLIDE left

# Engine Locale

    @@@ruby
    # foofah/config/locales/en.yml

    en:
      test_message: "This is a message"

!SLIDE left

# Custom Locale

    @@@ruby
    # config/locales/en.yml

    en:
      some_other_stuff: "Some other stuff"
      test_message: "This is custom"

!SLIDE bullets incremental

# You Can Override Other Stuff

* Models and Controllers
* Routes
* Images
* Javascript files
* Stylesheets

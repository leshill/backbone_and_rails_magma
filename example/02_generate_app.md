!SLIDE commandline
# Setup up a Rails gemset

    $ rvm gemset create backbone_and_rails

    $ rvm gemset use backbone_and_rails

    $ gem install rails

!SLIDE commandline
# Generate your app

    $ rails new backbone_and_rails

    $ cd backbone_and_rails

    $ git init .

    $ git commit -m 'Initial commit'

    $ cat > .rvmrc

    rvm use @backbone_and_rails

    $ git commit -am 'Setup .rvmrc'

!SLIDE commandline
# Add Backbone.js and Underscore.js

    $ curl -o vendor/assets/javascripts/backbone.js http://backbonejs.org/backbone.js

    $ curl -o vendor/assets/javascripts/underscore.js http://underscorejs.org/underscore.js

    $ git add vendor

    $ git commit -m 'Backbone.js and Underscore.js'

!SLIDE commandline
# Remove index.html

    $ git rm public/index.html

    $ git commit -m 'Remove default index.html'

!SLIDE
# Finish the install with some additional gems

* the new 1.9 `debugger` (yay!)

* `haml` for clearer markup

* `hogan_assets` to precompile our Mustache templates in the asset pipeline

* Bonus! `haml + mustache == hamstache`

* We added `informal` to not use AR, you should skip that

!SLIDE commandline
# Add gems

    $ cat > Gemfile

    source 'https://rubygems.org'
    gem 'rails', '3.2.5'
    gem 'haml'
    gem 'informal'
    gem 'jquery-rails'
    gem 'sqlite3'
    group :assets do
      gem 'coffee-rails', '~> 3.2.1'
      gem 'hogan_assets'
      gem 'sass-rails',   '~> 3.2.3'
      gem 'uglifier', '>= 1.0.3'
    end
    group :development, :test do
      gem 'debugger'
    end

    $ bundle

    $ git commit -am 'Add gems: debugger, haml, hogan_assets, informal'

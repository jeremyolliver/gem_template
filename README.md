Gem Template
============

This is a template for a skeleton ruby gem for use with [hoe](http://github.com/seattlerb/hoe)
The setup here are my own preferences, inspired and borrowed from the generators/templates from hoe, bundler and rails.

Caveats: This doesn't seem to work for gem names with dashes, underscores with lowercase is the ruby convention.

Usage
-----

install hoe

    gem install hoe

place this template in ~/.hoe_template

    git clone git://github.com/jeremyolliver/gem_template.git ~/.hoe_template

create new gem via hoe with:

    sow my_new_gem

Install development dependencies:

    gem install bundler
    bundle install
    
Writing Rails Engines (controllers or assets)
---------------------------------------------

Note: If you are writing a gem for use with rails, and intend to have either mountable controllers, or assets bundled via asset pipe. Then I highly suggest generating your gem/project with rails generators.

    gem update rails
    rails plugin new <name> --mountable

Read more at http://guides.rubyonrails.org/engines.html


Assumptions / Preferences
-------------------------

* Ruby 1.9.X Support only
* Usage of MiniTest::Spec and Simplecov
* Release process of:    
  1. Writing release notes in CHANGELOG.md
  2. Bump version by editing the constant in lib/foo_gem/version.rb
  3. Creating a git tag of vMAJOR.MINOR.PATCH (SemVer)
  4. build and push the gem to rubygems.org
  5. (`rake release`) will perform the previous two steps for you

Look for `TODO:`'s in the Source after generating your gems to see configuration and documentation that needs filling in

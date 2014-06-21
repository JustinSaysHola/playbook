# Boxen

We use [Github's Boxen](https://boxen.github.com/) to manage our development
environments. Using it makes it easy for us to get up and running with everyone
using the same environment. It also allows for easy upgrades of software
versions or adding new software as we add it to our stack.

## How to install

While not required, we would prefer if you start with a reformatted hard drive
with nothing installed. This will make sure that there isn't any software
already on your machine that conflicts with what boxen is installing.

1. Reformat your computer - [tutorial here](http://computers.tutsplus.com/tutorials/how-to-format-your-macs-hard-drive--mac-53986)
2. Turn on Full Disk Encryption - [tutorial
   here](http://osxdaily.com/2013/05/22/filevault-disk-encryption-mac/)
3. Install the latest [Xcode from the App
   Store](https://itunes.apple.com/us/app/xcode/id497799835?mt=12)
4. Install Xcode command line tools by running `xcode-select --install` in the
   Terminal
5. Go to [boxen web](https://poetic-boxen.herokuapp.com/), authorize with your
   github account and run the curl command in your Terminal.

It's possible that some errors may appear when boxen installs, if it is not
clear what you need to do to fix it you can contact @jakecraige or @MatthewHager
for assistance. The most common fixes are to restart the terminal and run the
`boxen` command again or to restart the computer and run the `boxen` command.

## What it installs

The list is constantly changing but we will try to keep this as up to date as
possible. As of today June 21, 2014 it installs the following items:

* [poetic standard dotfiles](https://github.com/poetic/dotfiles)
* gcc
* hub
* git
* nginx
* homebrew
* chrome
* firefox
* googledrive
* imageoptim
* postgresql
* sourcetree
* sublime
* transmit
* vagrant
* virtualbox
* wget
* sourcetree
* heroku
* memcached
* java
* solr
* elasticsearch
* eclipse::java
* android::sdk
* tmux
* ctags
* mongodb
* iterm2::stable
* iterm2::colors::solarized_dark
* iterm2::colors::jakes_cobalt
* mysql
* osx::global::disable_key_press_and_hold
* osx::global::expand_print_dialog
* osx::global::expand_save_dialog
* osx::dock::autohide
* osx::finder::show_all_on_desktop
* osx::finder::empty_trash_securely
* osx::finder::unhide_library
* osx::universal_access::ctrl_mod_zoom
* osx::universal_access::enable_scrollwheel_zoom
* osx::disable_app_quarantine
* osx::no_network_dsstores
* osx::keyboard::capslock_to_control
* rbenv
* Ruby versions: 2.1.2, 2.1.1, 2.1.0, 2.0.0, 1.9.3
* Ruby Gems
  * rails
  * ruboto
  * rails-api
  * compass
  * tmuxinator
  * rails_apps_composer
* Homebrew packages
  * ack
  * findutils
  * gnu-tar
  * drush
  * phantomjs
  * the_silver_searcher
  * git-flow
  * chromedriver
  * reattach-to-user-namespace
  * autojump
  * cmake
* Node versions: 0.10.26, 0.10.0
  * meteorite
  * grunt-cli
  * bower
  * cordova
  * ember-cli
  * yo


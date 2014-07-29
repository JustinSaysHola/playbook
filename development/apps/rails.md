# Rails

Rails is the ideal environment for developer happyness. **If you are careful and
you are smart about bootstraping your Rails project, you are almost
guaranteeing that your project will remain healthy for a long time.**

## What you need to know

First things first, let's instanciate your Rails project. (I'm not going into
details on using RVM or RBENV. Choosing one is a matter of preference although
some developers will always argue that one is better than the other.)

`gem install rails`

This will install rails if you don't have it. If you do, make sure to update to
the latest version.

`rails new APPNAME -T -d postgresql`

This will create your new rails project and use postgresql as the default
database. You should use postgresql since this is the database we use in
production. This way your development environment will also closely reflect the
production environment and you will avoid potential problems by using mysqlite
for development. The -T switch tells rails to skip TestUnit, since we use
Rspec/capybara exclusively.

## Gems

This is a list of gems that we often find ourselves using within our apps. Once
you set them up, save your Gemfile and do a bundle install.

**It is of extreme importance for you to take your time to review the repository
of every gem so you know how to set it up and how/why it works.

### Administration

* activeadmin or rails_admin

### User authentication

* devise + rolify, or sorcery

### For Apis

* active\_model\_serializers
* grape
* grape-active\_model\_serializers
* grape-swagger-rails
* rack-cors

### Development

* better_errors
* meta_request
* quiet_assets

### Development, Testing

* capybara
* capybara-screenshot
* database_cleaner
* factory\_girl\_rails
* faker
* poltergeist
* pry-rails
* rspec-rails
* shoulda_matchers
* spring-commands-rspec
* debugger
* simplecov or rubocop
* email_spec

### General

* figaro
* draper
* slim-rails
* pg
* simple_form
* unicorn

### Production

* airbrake * - for use with errbit*
* rails_12factor

## Overview

After setting your app, make sure to add an extra environment to your
app by adding a file in the `config/environments/` directory called `staging.rb`.
This is mainly used to have a second heroku app that you can use as staging to
show demos and try new code in a production-like env. Make sure your
application.yml file has separate keys for apis depending on what environment
you are on. For a more detailed explanation on this look into the **figaro** gem.
Also, you need to manually set the Rails.env variable manually on the staging
site, otherwise it will think it is in production.

### Javascripts

One good way to organize your javascript (these days even Rails apps are very JS
heavy) is to have a global Object with the name of your app. This object gets
called the `init()` method on the main application.js file. For example, we can
wrap the init file inside a jquery onready callback so our app knows when to
call all the javascript we've added to the app.

This main init function can be declared in another file, which in turn calls
different functions for different views/features. The code for these
views/features can be nested in an app directory inside the javascript
directory.

It's a bit confusing but it goes like this:

* Our main application.js file calls our APPNAME.init().
* The file where the init() method is defined then calls other functions we'll
  be using in our app.
* Each of these other functions is defined in it's own file nested in
  `javascripts/app/`. That way we can easily browse through different javascript
  features, each one declared in it's own file.

This gives us the ability to change the init function to add/remove any extra
functionality that is defined in it's own separate file - thus keeping our
codebase clean and organized.

## Guides

For a good example on how to setup a Rails api, go to:
[https://devmynd.com/blog/2014-7-rails-ember-js-with-the-ember-cli-redux-part-1-the-api-and-cms-with-ruby-on-rails]

For a good example of a well setup app, look into:
[https://bitbucket.org/poetic/ghba]
files with good configuration:
`spec/spec_helper.rb`
`config/environments/`

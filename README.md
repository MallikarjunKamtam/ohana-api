#Ohana API

A brand new project underway by Code for America's 2013 San Mateo County fellowship team. The goal is to build a read/write API for accessing data about available community social services.

This repo is in the early stages of development, stay tuned for when we are ready to accept contributions.

There is a front-end portion of this project under development at [Human Services Finder](https://github.com/codeforamerica/human_services_finder)

## Installation
Please note that the instructions below have only been tested on OS X. If you are running another operating system and run into any issues, feel free to update this README, or open an issue if you are unable to resolve installation issues.

###Prerequisites

#### Git, Ruby 2.0.0+, Rails 3.2.13+ (+ Homebrew on OS X)
**OS X**: [Set up a dev environment on OS X with Homebrew, Git, RVM, Ruby, and Rails](http://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/)

**Windows**: Try [RailsInstaller](http://railsinstaller.org), along with some of these [tutorials](https://www.google.com/search?q=install+rails+on+windows) if you get stuck.


#### MongoDB
**OS X**

On OS X, the easiest way to install MongoDB (or almost any development tool) is with Homebrew:

    brew update
    brew install mongodb

Follow the Homebrew instructions for configuring MongoDB

Launch mongodb in a separate Terminal tab or window:

    mongod

**Other**

See the Downloads page on mongodb.org for steps to install on other systems: [http://www.mongodb.org/downloads](http://www.mongodb.org/downloads)


#### Redis
**OS X**

On OS X, the easiest way to install Redis is with Homebrew:

    brew install redis

Follow the Homebrew instructions if you want Redis to start automatically every time you restart your computer. Otherwise launch Redis in a separate Terminal tab or window:

    redis-server

**Other**

See the Download page on Redis.io for steps to install on other systems: [http://redis.io/download](http://redis.io/download)

### Clone the app on your local machine:

    git clone git://github.com/codeforamerica/ohana-api.git
    cd ohana-api

### Install the dependencies:

    bundle

### Load the data
You can load two datasets — farmers' markets and libraries in San Mateo County — in your local db with this command:

    rake load_data

Create the geospatial indices for the [geocoder](https://github.com/alexreisner/geocoder) gem:

    rake db:mongoid:create_indexes

### Run the app
Start the app locally using Unicorn:

    unicorn

You should now be able to see a JSON response at [http://localhost:8080/api/organizations.json](http://localhost:8080/api/organizations.json)

## Development Details

* Ruby version 2.0.0
* Rails version 3.2.13
* MongoDB with the Mongoid ORM
* Template Engines: ERB and HAML
* Testing Frameworks: RSpec, Factory Girl
* Redis

## Contributing

(WE ARE NOT YET READY FOR CONTRIBUTIONS... BUT THIS WILL BE THE PROCESS...)

In the spirit of open source software, **everyone** is encouraged to help improve this project.

Here are some ways *you* can contribute:

* by using alpha, beta, and prerelease versions
* by reporting bugs
* by suggesting new features
* by suggesting labels for our issues
* by writing or editing documentation
* by writing specifications
* by writing code (**no patch is too small**: fix typos, add comments, clean up
  inconsistent whitespace)
* by refactoring code
* by closing [issues](https://github.com/codeforamerica/ohana-api/issues)
* by reviewing patches
* [financially](https://secure.codeforamerica.org/page/contribute)

## Submitting an Issue
We use the [GitHub issue tracker](https://github.com/codeforamerica/ohana-api/issues) to track bugs and features. Before submitting a bug report or feature request, check to make sure it hasn't already been submitted. When submitting a bug report, please include a [Gist](https://gist.github.com/) that includes a stack trace and any details that may be necessary to reproduce the bug, including your gem version, Ruby version, and operating system. Ideally, a bug report should include a pull request with failing specs.

## Submitting a Pull Request
1. [Fork the repository.][fork]
2. [Create a topic branch.][branch]
3. Add specs for your unimplemented feature or bug fix.
4. Run `rspec`. If your specs pass, return to step 3. In the spirit of Test-Driven Development, you want to write a failing test first, then implement the feature or bug fix to make the test pass.
5. Implement your feature or bug fix.
6. Run `rspec`. If your specs fail, return to step 5.
7. Add, commit, and push your changes.
8. [Submit a pull request.][pr]

[fork]: http://help.github.com/fork-a-repo/
[branch]: http://learn.github.com/p/branching.html
[pr]: http://help.github.com/send-pull-requests/

## Copyright
Copyright (c) 2013 Code for America. See [LICENSE](https://github.com/codeforamerica/ohana-api/blob/master/LICENSE.md) for details.
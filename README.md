# Logput

[![Build Status](https://travis-ci.org/chrisbarber86/logput.svg?branch=add_travis)](https://travis-ci.org/chrisbarber86/logput)

Rack middleware to sit in a rails app to put put the current environments log to a webpage. eg /logput

To be used in test and development environments to see logs without needing direct access to the box.

This NOT to be used in production like environments.

Supports Rails 3.x.x and 4.x.x

## Installation

Add this line to your application's Gemfile:

    gem 'logput'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install logput

## Usage

Inside you rails app. Add the following line to config/development.rb and/or any other environment you wish to use this in.

    config.middleware.use(Logput::Middleware)

The following configuration options are available.

* :path_to_log_file => '/path/to/custom/log'. Defaults to current environments log file if in rails.
* :lines_to_read => 1000. Defaults to 500.

Example.

    config.middleware.use(Logput::Middleware, :lines_to_read => 300, :path_to_log_file => './log/delayed_job')

Start you rails server as normal in the set environemnt. Navigate to /logput e.g. [http://localhost:3000/logput](http://localhost:3000/logput)

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

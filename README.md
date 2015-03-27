# Beanstalkd plugin

## Overview

This plugin will provide metrics from one or more [Beanstalkd](http://kr.github.io/beanstalkd/) servers to NewRelic.

## Prerequisites
- A NewRelic account

### Running Locally
- Ruby
- Bundler `gem install bundler`

### Running via Docker
- Docker

## Installation

The Beanstalkd plugin can be [installed manually](#first-time-setup-instructions) or automatically with [Chef](http://www.getchef.com). For Chef support see the New Relic plugin's [Chef Cookbook](http://community.opscode.com/cookbooks/newrelic_plugins).

Additional information on using Chef with New Relic is available in New Relic's [documentation](https://docs.newrelic.com/docs/plugins/plugin-installation-with-chef-and-puppet).

## First Time Setup Instructions
1. Download the [latest release](https://github.com/djoos/newrelic_beanstalkd_plugin/releases/latest) to the location you want to run the Beanstalkd agent from
2. Run `bundle install` in the folder you downloaded the agent to
2. Copy `config/newrelic_plugin.yml.dist` to `config/newrelic_plugin.yml`
3. Edit `config/newrelic_plugin.yml` and replace 'YOUR_LICENSE_KEY_HERE' with your New Relic license key
4. Configure the servers to monitor under the servers collection in the config file

### Running Locally
1. Run `bundle install`
2. Run `./bin/newrelic_beanstalkd`

### Running via Docker
1. Run `docker run --rm -v "$PWD":/usr/src/app -w /usr/src/app ruby:2.1 bundle install`
2. Run `docker build -t newrelic-beanstalkd-plugin .`
3. Run `docker run -d --restart=always newrelic-beanstalkd-plugin`

## Credits
We relied heavily on [ChannelGrabber Gearman NewRelic Plugin](https://github.com/channelgrabber/newrelic-gearman-plugin) for the development of this bundle. Thanks!

---
title:  "Hello Crystal?"
date:   2017-09-11 20:55:00
categories: [crystal]
tags: [crystal]
---
Crystal is a programming language created in 2011 which was designed to be productive and elegant as Ruby but faster as a compiled language.

Nowadays (2017/09) we are can see the rising of a new trend with some interesting and expressive frameworks that are being built on Crystal.

## Trending github projects

**[Kemal](https://github.com/kemalcr/kemal)**: A sinatra-like web framework. Fast and simple which allows you to configure everything according to your needs.

**[Amethyst](https://github.com/crystal-community/amethyst)**: A rails-like MVC framework which has some similar patterns if you are coming from Rails (controllers, routes, views, models [amethyst-model])

**[Amber](https://github.com/amberframework/amber)**: It's another rails-like framework, which has the same appeal of Amethyst but this one, include some scaffolding tools.

**[Awesome Crystal](https://github.com/veelenga/awesome-crystal)**: A huge FAQ, community-driven, repository. Just like "Awesome Ruby", "Awesome Javascript" and so.


## Hello World

A simple "Hello World" written in Crystal:

```ruby
puts "Hey, give me a beer, please!"
```

Another example using OO approach:

```ruby
class User
  def initialize(@name : String)
  end

  def say_hi
    puts "Hi #{@name}!"
  end
end

user = User.new("José")
user.say_hi
```

## Instalation

You can find a more detailed installation guide at the [official documentation website](https://crystal-lang.org/docs/installation/on_debian_and_ubuntu.html).

### On Ubuntu-based linux

Add the signing key and the repository configuration and update the packages available:

```
# apt-key adv --keyserver keys.gnupg.net --recv-keys 09617FD37CC06B54
# echo "deb https://dist.crystal-lang.org/apt crystal main" > /etc/apt/sources.list.d crystal.list
# apt-get update
```

Then install the Crystal lang compiler and dependencies:

```
sudo apt-get install  build-essential crystal
```

### On Apple using home brew

```
brew update
brew install crystal-lang
```

## Creating a simple chat using Kemal

```
# TODO
```
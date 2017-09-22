---
title:  "Hello Crystal"
date:   2017-09-11 20:55:00
categories: [crystal]
tags: [crystal]
---
Crystal is a programming language created in 2011 which was designed to be productive and elegant as Ruby but faster as a compiled language.

Nowadays (2017/09) we are can see the rising of a new trend with some interesting and expressive frameworks that are being built on Crystal.

## Trending github projects

When I was looking at Crystal frameworks at GitHub I found some interesting frameworks and repositories with an ascending number of stars and watchers.

If you are coming from another framework or technology, these ones may be a good choice for you.

**[Kemal](https://github.com/kemalcr/kemal)**

A sinatra-like web framework. Fast and simple which allows you to configure everything according to your needs.

**[Amethyst](https://github.com/crystal-community/amethyst)**

A rails-like MVC framework which has some similar patterns if you are coming from Rails (controllers, routes, views, models [amethyst-model])

**[Amber](https://github.com/amberframework/amber)**

It's another rails-like framework, which has the same appeal of Amethyst but this one, include some scaffolding tools.

**[Awesome Crystal](https://github.com/veelenga/awesome-crystal)**

A huge FAQ, community-driven, repository. Just like "Awesome Ruby", "Awesome Javascript" and so.


## Hello World

As I said before, Crystal looks like Ruby except for small differences. The example above shows a simple "hello world" in Crystal:

```ruby
puts "Hey, give me a beer, please!"
```

This is another example using the OOP approach:

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

The Crystal installation is very simple as any other modern languages you just have to add the source, update and install the package according to your operating system.

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

You can find a more detailed installation guide at the [official documentation website](https://crystal-lang.org/docs/installation/on_debian_and_ubuntu.html).


## Creating a simple chat using Kemal

This is a short example to show how simple is to create a real time application using Crystal could be.

First, create a project named **crystal-chat-example**:

```
crystal init app crystal-chat-example
cd crystal-chat-example
```

Now you should edit the file **shard.yml** to add the **Kemal** dependency.
The *shard.yml* works like the **package.json** from **npm** mixed with **Gemfile** from Ruby.

```yaml
name: crystal-chat-example
version: 0.1.0

dependencies:
  kemal:
     github: sdogruyol/kemal
     branch: master

authors:
  - José Ribeiro <zeca@digup.io>

targets:
  crystal-chat-example:
    main: src/crystal-chat-example.cr

crystal: 0.23.1

license: MIT
```

Then, run the **shards install** to download and install the dependencies.

```
shards install
```

### Controller

After that you will be able to use **Kemal**. Now change the file **src/crystal-chat-example.cr** with the following content:

```ruby
require "./crystal-chat-example/*"
require "kemal"

module Crystal::Chat::Example
  get "/" do |env|
    render "views/index.ecr"
  end
  Kemal.run
end
```

### View

Create the view file **views/index.ecr**:

```html
<!doctype html>
<html>
<body>
  <pre id='chat'></pre>
  <form>
    <input id='msg' placeholder='message...' />
    <input type="submit" value="Send">
  </form>
</body>
</html>
```

After that run the command **crystal run src/crystal-chat-example.cr** to start the application at [your localhost](http://localhost:4000/). After these steps you should see a blank page just with an input text and button that does nothing, yet.

### Adding websocket

---
layout: post
title: "Managing Gems and Ruby versions with RVM and Bundler"
comments: true
published: false
categories: ["Ruby", "RVM", "Tutorial"]
---

When learning Rails, I kept running into tutorials that recommended using RVM, but glossed over what it really did. All that I learned was that RVM lets you run different version of Ruby and Rails. Still, I never built the habits of using it and so never memorized any of the commands. With that in mind, I decided to dive into RVM deeper.

## Why use RVM
RVM stands for Ruby Version Manager. It's primary intent is to help you use different versions of ruby in different projects. It's solving the problem where you may have older apps that require older versions of ruby and need to switch to a newer version when building newer apps.

- Need different implementations of Ruby
- Conflicts between gems of different projects
- Makes it easy to install and manage Ruby and their gems

## Install RVM
Do `rvm -v` to see if you have RVM installed and what version

Recommended single-user installation:
    $ \curl -L https://get.rvm.io | bash -s -- --ignore-dotfiles
    $ echo "source $HOME/.rvm/scripts/rvm" >> ~/.bash_profile

See [rvm.io installation docs](https://rvm.io/rvm/install)

## Common RVM commands


## Gemsets
- Intro
- How to use
- rmvrc files

## Sources
[rvm.io: Official RVM site](http://rvm.io/)
[nettuts+: Why You Should Use RVM](http://net.tutsplus.com/tutorials/why-you-should-use-rvm/)
[Railscasts: Rails 3 Beta and RVM](http://railscasts.com/episodes/200-rails-3-beta-and-rvm?autoplay=true)



gem install bundler

bundle

bundler update

gem '', '~> 2.1'
gem '', '2.1'
gem ''
gem '', github: "rails/rails", branch:p

# RuboCop Factrory Bot

[![Join the chat at https://gitter.im/rubocop-rspec/Lobby](https://badges.gitter.im/rubocop-rspec/Lobby.svg)](https://gitter.im/rubocop-rspec/Lobby)
[![Gem Version](https://badge.fury.io/rb/rubocop-factory_bot.svg)](https://rubygems.org/gems/rubocop-factory_bot)
![CI](https://github.com/rubocop/rubocop-factory_bot/workflows/CI/badge.svg)

[Factory Bot](https://www.rubydoc.info/gems/factory_bot)-specific analysis for your projects, as an extension to
[RuboCop](https://github.com/rubocop/rubocop).

## Installation

Just install the `rubocop-factory_bot` gem

```bash
gem install rubocop-factory_bot
```

or if you use bundler put this in your `Gemfile`

```
gem 'rubocop-factory_bot', require: false
```

## Usage

You need to tell RuboCop to load the Factory Bot extension. There are three
ways to do this:

### RuboCop configuration file

Put this into your `.rubocop.yml`.

```yaml
require: rubocop-factory_bot
```

Alternatively, use the following array notation when specifying multiple extensions.

```yaml
require:
  - rubocop-other-extension
  - rubocop-factory_bot
```

Now you can run `rubocop` and it will automatically load the RuboCop Factory Bot
cops together with the standard cops.

### Command line

```bash
rubocop --require rubocop-factory_bot
```

### Rake task

```ruby
RuboCop::RakeTask.new do |task|
  task.requires << 'rubocop-factory_bot'
end
```

## Documentation

You can read more about RuboCop Factory Bot in its [official manual](https://docs.rubocop.org/rubocop-factory_bot).

## The Cops

All cops are located under
[`lib/rubocop/cop/factory_bot`](lib/rubocop/cop/factory_bot), and contain
examples/documentation.

In your `.rubocop.yml`, you may treat the Factory Bot cops just like any other
cop. For example:

```yaml
FactoryBot/AttributeDefinedStatically:
  Exclude:
    - spec/factories/my_factory.rb
```

## Contributing

Checkout the [contribution guidelines](.github/CONTRIBUTING.md).

## License

`rubocop-factory_bot` is MIT licensed. [See the accompanying file](MIT-LICENSE.md) for
the full text.

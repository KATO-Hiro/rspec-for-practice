# rspec-for-practice

Ruby and RSpec for practice with Docker.

## Requirement

- Docker 18.0x
- Ruby 2.x

## Usage

1. Install this repository and make initial settings.
2. Run tests.
3. Add your tests and run.

## Installation

Paste the following commands at a Terminal prompt.

```terminal:
$ git clone git@github.com:KATO-Hiro/rspec-for-practice.git
```

## Getting started

1. Create an image and run it using docker-compose command.

```terminal
$ docker-compose build
$ docker-compose up -d
```

2. Initialize RSpec.

```terminal
$ docker-compose run web rspec --init
```

+ To enable some settings, delete =begin and =end in spec/spec_helper.rb

```ruby
…
RSpec.configure do |config|
# The settings below are suggested to provide a good initial experience
# with RSpec, but feel free to customize to your heart's content.
- =begin
  # These two settings work together to allow you to limit a spec run
  # to individual examples or groups you care about by tagging them with
  # `:focus` metadata. When nothing is tagged with `:focus`, all examples
  # get run.
  config.filter_run :focus
  config.run_all_when_everything_filtered = true

  ...

    # Prevents you from mocking or stubbing a method that does not exist on
    # a real object. This is generally recommended.
    mocks.verify_partial_doubles = true
  end
- =end
end
```

3. Run the first test.

```
# This is a sample directory structure (main files only).
# See: References

rspec-for-practice
├── Dockerfile
├── Gemfile
├── Gemfile.lock
├── docker-compose.yml
├── lib
│   └── hello.rb
└── spec
    ├── hello_spec.rb
    └── spec_helper.rb
```

+ Add production/RSpec codes to lib/spec directory.

```terminal
$ docker-compose run web bundle exec rspec
```

+ It's okay if the status is a green bar like this:

```terminal
Randomized with seed 37023

Hello
  message return hello

Top 1 slowest examples (0.00061 seconds, 10.5% of total time):
  Hello message return hello
    0.00061 seconds ./spec/hello_spec.rb:4

1 example, 0 failures

Randomized with seed 37023
```

## References

> https://qiita.com/yusabana/items/db44b81bdddf6ed0e9f5

## Author

[@KATO-Hiro](https://twitter.com/k_hiro1818)

## License

[MIT](http://KATO-Hiro.mit-license.org)

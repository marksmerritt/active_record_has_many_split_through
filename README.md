# HasManySplitThrough association for ActiveRecord

Don't use joins 

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'active_record_has_many_split_through', github: 'myobie/active_record_has_many_split_through'
```

And then execute:

    $ bundle

## Usage

Add `split: true` to your normal `has_many :something, through: :something_else` to avoid using joins. Maybe your tables are in different databases 😎

Example from [`test/test_helper.rb`](test/test_helper.rb):

```ruby
class ShippingCompany < ActiveRecord::Base
  has_many :offices
  has_many :employees, through: :offices

  # in other databases
  has_many :docks
  has_many :ships, through: :docks, split: true
end
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/myobie/active_record_has_many_split_through. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the ActiveRecordHasManySplitThrough project’s codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/myobie/active_record_has_many_split_through/blob/master/CODE_OF_CONDUCT.md).

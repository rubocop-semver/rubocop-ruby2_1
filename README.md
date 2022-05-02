<p align="center">
    <a href="https://rubocop.org#gh-light-mode-only"  target="_blank" rel="noopener">
      <img width="120px" src="https://github.com/rubocop-semver/rubocop-ruby2_1/raw/main/docs/images/logo/rubocop-light.svg?raw=true" alt="PNG Rubocop Logo, Copyright (c) 2014 Bozhidar Batsov, MIT License, SVG Rubocop Logo, Gil Barbara, CC0">
    </a>
    <a href="https://rubocop.org#gh-dark-mode-only"  target="_blank" rel="noopener">
      <img width="120px" src="https://github.com/rubocop-semver/rubocop-ruby2_1/raw/main/docs/images/logo/rubocop-dark.svg?raw=true" alt="SVG Rubocop Logo, Copyright (c) 2014 Bozhidar Batsov, MIT License, SVG Rubocop Logo, Roberto Huertas, MIT">
    </a>
    <a href="https://www.ruby-lang.org/" target="_blank" rel="noopener">
      <img width="120px" src="https://github.com/rubocop-semver/rubocop-ruby2_1/raw/main/docs/images/logo/ruby-logo.svg?raw=true" alt="Yukihiro Matsumoto, Ruby Visual Identity Team, CC BY-SA 2.5">
    </a>
    <a href="https://semver.org/#gh-light-mode-only" target="_blank" rel="noopener">
      <img width="120px" src="https://github.com/rubocop-semver/rubocop-ruby2_1/raw/main/docs/images/logo/semver-light.svg?raw=true" alt="SemVer.org Logo by @maxhaz">
    </a>
    <a href="https://semver.org/#gh-dark-mode-only" target="_blank" rel="noopener">
      <img width="120px" src="https://github.com/rubocop-semver/rubocop-ruby2_1/raw/main/docs/images/logo/semver-dark.svg?raw=true" alt="SemVer.org Logo by @maxhaz">
    </a>
</p>

# Rubocop::Ruby21

See the intro [blog post](https://dev.to/pboling/rubocop-ruby-matrix-gems-nj)!

This gem requires no other gems. It depends on `rubocop`, but does not `require 'rubocop'`.

Awareness of `rubocop`'s lack of [SemVer][semver] adherence isn't evenly dispersed in the Ruby community.

The Rubocop team [has real reasons](https://github.com/semver/semver/issues/317)
for [not following SemVer](https://github.com/rubocop/rubocop/issues/4243), but if you've
found this project their reasons likely weigh less, in your context (e.g. running `rubocop` from command line), than
what brought you here.

<p align="left">
    <a href="https://metaredux.com/posts/2022/04/21/rubocop-turns-10.html" target="_blank" rel="noopener">
      <img width="360px" src="https://github.com/rubocop-semver/rubocop-ruby2_1/raw/main/docs/images/rubocop-not-semver.png?raw=true" alt="Explanation of non-SemVer compliance, @bbatsov">
    </a>
</p>

The purpose of this gem is to constrain the `rubocop` dependency of a project in
a [SemVer compliant](https://semver.org/) (Semantic Versioning) way that aligns with the the desired minimum
compatible/supported Ruby version.

Adding this gem will facilitate the best practice of adding a `~> ` version constrained `rubocop` dependency, while
minimizing the risk of a rubocop minor / patch upgrade breaking the build. See the
official [compatibility matrix](https://github.com/rubocop/rubocop/blob/master/docs/modules/ROOT/pages/compatibility.adoc#support-matrix) (Rubocop documentation)

## Stable

All releases of this gem are stable releases. The first version is `1.0.0`.

## Installation

Without bundler execute:

    $ gem install 

Add this line to your application's Gemfile:

```ruby
gem 'rubocop-ruby2_1', '~> 1.0', require: false
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install rubocop-ruby2_1

## Usage

The following is optional.  We'll discuss why you might want to do this after you see what it does.

Add to the top of your project's `.rubocop.yml` configuration file:

```yaml
inherit_gem:
  rubocop-ruby2_1: rubocop.yml
```

This has the same effect as you declaring the following in your `.rubocop.yml`:

```yaml
AllCops:
  # remove if already present in your `.rubocop.yml` to gain the full benefit of this gem!
  TargetRubyVersion: 2.1
  # The sibling gems for newer versions of Ruby support the NewCops directive as soon as Rubocop adds it.
  # NewCops: enable
```

Let's talk about these settings.

## TargetRubyVersion

Allowing this gem to manage the target ruby version means you can switch to a different gem within the family when you upgrade to the next version of Ruby, and have nothing else to change.  A single line in the `Gemfile`, and you are done.

## NewCops: enable

If you want to use this you'll have to upgrade to Ruby >= 2.4 and use the appropriate sibling gem, e.g. [`rubocop-ruby2_4`][2-4].

[2-4]: https://github.com/rubocop-semver/rubocop-ruby2_4

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and the created tag, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

See [CONTRIBUTING.md][contributing]

## Contributors

[![Contributors](https://contrib.rocks/image?repo=rubocop-semver/rubocop-ruby2_1)]("https://github.com/rubocop-semver/rubocop-ruby2_1/graphs/contributors")

Made with [contributors-img](https://contrib.rocks).

## License

The gem is available as open source under the terms of
the [MIT License][license] [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)][license-ref].
See [LICENSE][license] for the official [Copyright Notice][copyright-notice-explainer].

<details>
  <summary>Project Logos (rubocop-ruby2_1)</summary>

See [docs/images/logo/README.txt][project-logos]
</details>

<details>
  <summary>Organization Logo (rubocop-semver)</summary>

Author: [Yusuf Evli][org-logo-author]
Source: [Unsplash][org-logo-source]
License: [Unsplash License][org-logo-license]
</details>

[project-logos]: https://github.com/rubocop-semver/rubocop-ruby2_1/blob/main/docs/images/logo/README.txt
[org-logo-author]: https://unsplash.com/@yusufevli
[org-logo-source]: https://unsplash.com/photos/yaSLNLtKRIU
[org-logo-license]: https://unsplash.com/license

### Copyright

* Copyright (c) 2022 [Peter H. Boling][peterboling] of [Rails Bling][railsbling]

[copyright-notice-explainer]: https://opensource.stackexchange.com/questions/5778/why-do-licenses-such-as-the-mit-license-specify-a-single-year

## Code of Conduct

Everyone interacting in the Rubocop::Ruby21 project's codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/rubocop-semver/rubocop-ruby2_1/blob/main/CODE_OF_CONDUCT.md).

## Versioning

This library aims to adhere to [Semantic Versioning 2.0.0][semver]. Violations of this scheme should be reported as
bugs. Specifically, if a minor or patch version is released that breaks backward compatibility, a new version should be
immediately released that restores compatibility. Breaking changes to the public API will only be introduced with new
major versions.

As a result of this policy, you can (and should) specify a dependency on this gem using
the [Pessimistic Version Constraint][pvc] with two digits of precision.

For example:

```ruby
spec.add_dependency "rubocop-ruby2_1", "~> 1.0"
```

[copyright-notice-explainer]: https://opensource.stackexchange.com/questions/5778/why-do-licenses-such-as-the-mit-license-specify-a-single-year

[gh_discussions]: https://github.com/rubocop-semver/rubocop-ruby2_1/discussions

[conduct]: https://github.com/rubocop-semver/rubocop-ruby2_1/blob/main/CODE_OF_CONDUCT.md

[contributing]: https://github.com/rubocop-semver/rubocop-ruby2_1/blob/main/CONTRIBUTING.md

[security]: https://github.com/rubocop-semver/rubocop-ruby2_1/blob/main/SECURITY.md

[license]: https://github.com/rubocop-semver/rubocop-ruby2_1/blob/main/LICENSE.txt

[license-ref]: https://opensource.org/licenses/MIT

[semver]: http://semver.org/

[pvc]: http://guides.rubygems.org/patterns/#pessimistic-version-constraint

[railsbling]: http://www.railsbling.com

[peterboling]: http://www.peterboling.com

[aboutme]: https://about.me/peter.boling

[angelme]: https://angel.co/peter-boling

[coderme]:http://coderwall.com/pboling

[followme-img]: https://img.shields.io/twitter/follow/galtzo.svg?style=social&label=Follow

[tweetme]: http://twitter.com/galtzo

[politicme]: https://nationalprogressiveparty.org

[documentation]: https://rubydoc.info/github/rubocop-semver/rubocop-ruby2_1/main

[source]: https://github.com/rubocop-semver/rubocop-ruby2_1/

[actions]: https://github.com/rubocop-semver/rubocop-ruby2_1/actions

[issues]: https://github.com/rubocop-semver/rubocop-ruby2_1/issues

[climate_maintainability]: https://codeclimate.com/github/rubocop-semver/rubocop-ruby2_1/maintainability

[code_triage]: https://www.codetriage.com/rubocop-semver/rubocop-ruby2_1

[blogpage]: http://www.railsbling.com/tags/rubocop-ruby2_1/

[rubygems]: https://rubygems.org/gems/rubocop-ruby2_1

[chat]: https://gitter.im/rubocop-semver/rubocop-ruby2_1?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge

[maintenancee_policy]: https://guides.rubyonrails.org/maintenance_policy.html#security-issues

[liberapay_donate]: https://liberapay.com/pboling/donate

[gh_sponsors]: https://github.com/sponsors/pboling

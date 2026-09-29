<h1 align="center">
  <a href="https://github.com/tomtom87/Portage"><img src="https://raw.githubusercontent.com/tomtom87/Portage/main/docs/assets/portage-logo.svg" alt="Portage" width="520"></a>
</h1>

<p align="center"><strong>The Homebrew tap for the <code>portage</code> CLI.</strong></p>

<p align="center">
  <a href="https://github.com/tomtom87/homebrew-portage/blob/main/Formula/portage.rb"><img src="https://img.shields.io/badge/dynamic/regex?url=https%3A%2F%2Fraw.githubusercontent.com%2Ftomtom87%2Fhomebrew-portage%2Fmain%2FFormula%2Fportage.rb&search=portage-cli-(%5Cd%2B%5C.%5Cd%2B%5C.%5Cd%2B)&replace=%241&label=homebrew&color=orange" alt="homebrew"></a>
  <a href="https://rubygems.org/gems/portage-cli"><img src="https://img.shields.io/gem/v/portage-cli" alt="gem version"></a>
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="license">
  <a href="https://portage.readthedocs.io/en/latest/"><img src="https://img.shields.io/badge/docs-readthedocs-blue" alt="docs"></a>
  <a href="https://github.com/tomtom87/Portage"><img src="https://img.shields.io/badge/source-tomtom87%2FPortage-black?logo=github" alt="source"></a>
</p>

<p align="center">
  <a href="https://github.com/tomtom87/Portage"><img src="https://raw.githubusercontent.com/tomtom87/Portage/main/docs/assets/portage-demo.gif" alt="portage buy searching The Light Yard over UCP and opening the checkout for a gold leaf bathroom wall light" width="900"></a>
</p>

Portage lets an AI agent find and buy things from real online stores for you, and you approve every payment. This tap installs the `portage` command-line tool with every first-party store adapter bundled, so there is nothing else to install. Source, issues and docs live in the main project, [tomtom87/Portage](https://github.com/tomtom87/Portage).

## Install

```bash
brew install tomtom87/portage/portage
```

Or tap first, then install by name:

```bash
brew tap tomtom87/portage
brew install portage
```

Or in a `Brewfile`:

```ruby
tap "tomtom87/portage"
brew "portage"
```

Then run setup once, in a terminal. It asks for your shipping address, optional search keys and spending caps, one skippable step at a time:

```bash
portage setup
```

## Update or remove

```bash
brew update && brew upgrade portage

brew uninstall portage
brew untap tomtom87/portage
```

## What's in the formula

| | |
| --- | --- |
| **Formula** | [`portage`](Formula/portage.rb) |
| **Installs** | [`portage-cli`](https://rubygems.org/gems/portage-cli) plus every bundled adapter, webmcp and decision gem, each pinned to an exact version and sha256 |
| **Requires** | Homebrew's `ruby` (installed for you) |

Prefer RubyGems? On Ruby 3.2 or newer, `gem install portage-cli`. See the [Portage README](https://github.com/tomtom87/Portage#quickstart) for which extra gems to add.

## Use it with Claude Code

The [`buy` plugin](https://github.com/tomtom87/Portage#install-the-buy-plugin) teaches Claude Code to shop through this CLI. With `portage` installed, inside Claude Code:

```text
/plugin marketplace add tomtom87/Portage
/plugin install buy@portage
```

Then ask Claude, for example `/buy a burton snowboard under $600`. It shows real offers and a dry-run total, and waits for your yes before any purchase.

## Maintainers

`Formula/portage.rb` is generated. Don't hand-edit it. Every release of `portage-cli` or a bundled gem regenerates, tests and pushes it from the main repo:

```bash
rake homebrew:update
```

That runs `script/homebrew-formula`, then `brew install --build-from-source`, `brew test`, `brew style` and `brew audit --strict --online` before committing. The tap has no CI of its own.

## Links

- [Portage source and issues](https://github.com/tomtom87/Portage)
- [Documentation](https://portage.readthedocs.io/en/latest/)
- [Changelog](https://github.com/tomtom87/Portage/blob/main/CHANGELOG.md)
- [Homebrew documentation](https://docs.brew.sh)

## License

MIT. See [LICENSE](https://github.com/tomtom87/Portage/blob/main/LICENSE).

# Changelog

All notable changes to Congo will be documented in this file. Things that need attention when upgrading from a prior version are marked ⚠️.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.6.2] - 2022-01-07

### Changed

- Upgrade to Chart.js v3.7.0
- Upgrade to Mermaid v8.13.8

### Fixed

- `lead` shortcode not rendering Markdown formatted text ([#73](https://github.com/jpanther/congo/issues/73))
- JSON-LD keywords data not structured correctly ([#74](https://github.com/jpanther/congo/issues/74))

## [1.6.1] - 2021-12-31

### Added

- Icon for Blogger ([#71](https://github.com/jpanther/congo/pull/71))

### Fixed

- Error when building using older Hugo versions ([#65](https://github.com/jpanther/congo/pull/65))
- Error when serving sites using blogdown ([#66](https://github.com/jpanther/congo/pull/66))

## [1.6.0] - 2021-12-21

### Added

- Article word counts ([#57](https://github.com/jpanther/congo/pull/57))
- Last updated dates on articles
- Icons for Amazon, Apple, Flickr, Google, Kickstarter, Microsoft, Patreon, Telegram, Tumblr and WhatsApp

### Changed

- Adjusted contrast of some items to improve accessibility
- Upgrade to Chart.js v3.6.2
- Upgrade to Mermaid v8.13.6

### Fixed

- Missing ARIA descriptions and alt tags on some images and links

## [1.5.3] - 2021-11-18

### Changed

- Updated Chinese translation ([#32](https://github.com/jpanther/congo/pull/32))

### Fixed

- Article pagination uses date of current article ([#32](https://github.com/jpanther/congo/pull/32))

## [1.5.2] - 2021-11-10

### Added

- German translation ([#27](https://github.com/jpanther/congo/pull/27))
- Brazilian Portuguese translation ([#28](https://github.com/jpanther/congo/pull/28))
- Spanish translation ([#30](https://github.com/jpanther/congo/pull/30))

### Fixed

- Article pagination link spacing ([#26](https://github.com/jpanther/congo/pull/26))
- Minor icon style issues

## [1.5.1] - 2021-11-04

### Fixed

- Hugo failing to build site when deploying as a module

## [1.5.0] - 2021-11-04

### Added

- Chart.js support using `chart` shortcode
- KaTeX support using `katex` shortcode
- Dark mode toggle with new theme parameters for managing light/dark appearance
- French translation ([#18](https://github.com/jpanther/congo/pull/18))
- Author bio in article footer
- Grouping by year can now be specificed in front matter on list pages

### Changed

- Site name, author and menus will now render Markdown and Emoji
- Bundled Mermaid for better vendor dependency management
- Mermaid diagrams are now themed to match the configured colour scheme
- Upgrade to Tailwind v2.2.19

### Fixed

- Site logo image dimensions are unconstrained ([#19](https://github.com/jpanther/congo/issues/19))
- Article summary styled incorrectly in dark mode
- Links containing `code` blocks styled incorrectly

## [1.4.0] - 2021-10-20

### Added

- Footer menu
- Article summary support
- Slate colour scheme ([#9](https://github.com/jpanther/congo/pull/9))
- Icons for ORCID and ResearchGate ([#9](https://github.com/jpanther/congo/pull/9))
- Pinterest sharing links
- Sharing links can now be specified in front matter

### Changed

- Main menu is now optional
- Upgrade to Mermaid v8.13.3
- Upgrade to Tailwind v2.2.17

### Fixed

- Site logo not linked to home page ([#13](https://github.com/jpanther/congo/issues/13))

## [1.3.0] - 2021-09-29

### Added

- Site logo support
- Chinese translation ([#2](https://github.com/jpanther/congo/pull/2))

### Changed

- Upgrade to Tailwind v2.2.16

## [1.2.1] - 2021-08-26

### Added

- New `robots` parameter to add metadata to guide robots on how to handle specific content

### Changed

- URLs are relative by default which allows the theme to be more flexible in different deployment scenarios

### Fixed

- Missing dark style for group subheadings on article listings
- Fathom Analytics script included twice when using custom domain
- Recent heading on homepage profile layout misaligned

## [1.2.0] - 2021-08-22

### Added

- Multiple colour schemes
- Edit links on article pages
- Icons for Foursquare and Pinterest
- Asset fingerprinting and SRI
- CSS minification for custom stylesheets

### Changed

- Static assets are now managed through Hugo Pipelines

### Fixed

- Minor style issue with `button` shortcode
- Hugo Modules would fail when using default theme config file
- Some content not centred correctly on the profile homepage layout
- Some links missing the correct styles when in Firefox
- `externalUrl` front matter not working on some list pages

## [1.1.1] - 2021-08-19

### Fixed

- Hotfix for exampleSite and GitHub configuration

## [1.1.0] - 2021-08-18

### Added

- Breadcrumbs
- i18n support
- Recent articles partial
- CSS transitions
- Hugo module support
- JSON-LD structured metadata

### Changed

- ⚠️ Renamed parameter: `homepage.showList` -> `homepage.showRecent`
- ⚠️ Renamed parameter: `homepage.listSections` -> `mainSections`
- ⚠️ Consolidated author configuration parameters into `config.toml`
- General style tweaks to enhance design consistency

### Fixed

- URLs being incorrect in some cases when the site is deployed in a subfolder

## [1.0.0] - 2021-08-16

### Added

- Built with Tailwind CSS JIT for minified stylesheets without any excess code
- Fully responsive layout
- Dark mode (auto-switching based upon browser)
- Highly customisable configuration
- Multiple homepage layouts
- Flexible with any content types, taxonomies and menus
- Ability to link to posts on third-party websites
- Diagrams and visualisations using Mermaid JS
- SVG icons from FontAwesome 5
- Heading anchors, Buttons, Badges and more
- HTML and Emoji support in articles
- SEO friendly with links for sharing to social media
- RSS feeds
- Fathom Analytics and Google Analytics support
- Favicons support
- Comments support
- Advanced customisation using simple Tailwind colour definitions and styles
- Fully documented

[unreleased]: https://github.com/jpanther/congo/compare/v1.6.2...HEAD
[1.6.2]: https://github.com/jpanther/congo/compare/v1.6.1...v1.6.2
[1.6.1]: https://github.com/jpanther/congo/compare/v1.6.0...v1.6.1
[1.6.0]: https://github.com/jpanther/congo/compare/v1.5.3...v1.6.0
[1.5.3]: https://github.com/jpanther/congo/compare/v1.5.2...v1.5.3
[1.5.2]: https://github.com/jpanther/Congo/compare/v1.5.1...v1.5.2
[1.5.1]: https://github.com/jpanther/Congo/compare/v1.5.0...v1.5.1
[1.5.0]: https://github.com/jpanther/Congo/compare/v1.4.0...v1.5.0
[1.4.0]: https://github.com/jpanther/Congo/compare/v1.3.0...v1.4.0
[1.3.0]: https://github.com/jpanther/Congo/compare/v1.2.1...v1.3.0
[1.2.1]: https://github.com/jpanther/Congo/compare/v1.2.0...v1.2.1
[1.2.0]: https://github.com/jpanther/Congo/compare/v1.1.1...v1.2.0
[1.1.1]: https://github.com/jpanther/congo/compare/v1.1.0...v1.1.1
[1.1.0]: https://github.com/jpanther/congo/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/jpanther/congo/releases/tag/v1.0.0

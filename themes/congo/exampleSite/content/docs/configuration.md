---
title: "Configuration"
date: 2020-08-14
draft: false
description: "All the configuration variables available in Congo."
slug: "configuration"
tags: ["config", "docs"]
---

Congo is a highly customisable theme and uses some of the latest Hugo features to simplify how it is configured.

The theme ships with a default configuration that gets you up and running with a basic blog or static website.

> Configuration files bundled with the theme are provided in TOML format as this is the default Hugo syntax. Feel free to convert your config to YAML or JSON if you wish.

The default theme configuration is documented in each file so you can freely adjust the settings to meet your needs.

{{< alert >}}
As outlined in the [installation instructions]({{< ref "/docs/installation#set-up-theme-configuration-files" >}}), you should adjust your theme configuration by modifying the files in the `config/_default/` folder of your Hugo project and delete the `config.toml` file in your project root.
{{< /alert >}}

## Site configuration

Standard Hugo configuration variables are respected throughout the theme, however there are some specific things that should be configured for the best experience.

The site configuration is managed through the `config/_default/config.toml` file. The table below outlines all the settings that the Congo takes advantage of.

Note that the variable names provided in this table use dot notation to simplify the TOML data structure (ie. `outputs.home` refers to `[outputs] home`).

<!-- prettier-ignore-start -->
|Name|Default|Description|
|---|---|---|
|`theme`|`"congo"`|When using Hugo Modules this config value should be removed. For all other installation types, this must be set to `congo` for the theme to function.|
|`baseURL`|_Not set_|The URL to the root of the website.|
|`defaultContentLanguage`|`"en"`|This value determines the default language of theme components and content. Refer to the [language and i18n](#language-and-i18n) section below for supported language codes.|
|`enableRobotsTXT`|`true`|When enabled a `robots.txt` file will be created in the site root that allows search engines to crawl the entire site. Set to `false` if you wish to provide your own file.|
|`paginate`|`10`|The number of articles listed on each page of the article listing.|
|`summaryLength`|`0`|The number of words that are used to generate the article summary when one is not provided in the [front matter]({{< ref "front-matter" >}}). A value of `0` will use the first sentence. This value has no effect when summaries are hidden.|
|`outputs.home`|`["HTML", "RSS", "JSON"]`|The output formats that are generated for the site. Congo requires HTML, RSS and JSON for all theme components to work correctly.|
|`permalinks`|_Not set_|Refer to the [Hugo docs](https://gohugo.io/content-management/urls/#permalinks) for permalink configuration.|
|`taxonomies`|_Not set_|Refer to the [Organising content]({{< ref "getting-started#organising-content" >}}) section for taxonomy configuration.|
<!-- prettier-ignore-end -->

## Language and i18n

Congo is optimised for full multilingual websites and theme assets are translated into several languages out of the box. The language configuration allows you to generate multiple versions of your content to provide a customised experience to your visitors in their native language.

The theme currently supports the following languages by default:

| Language                         | Code    |
| -------------------------------- | ------- |
| :gb: English                     | `en`    |
| :bangladesh: Bengali             | `bn`    |
| :cn: Chinese                     | `zh`    |
| :fr: French                      | `fr`    |
| :de: German                      | `de`    |
| :brazil: Portuguese (Brazil)     | `pt-br` |
| :portugal: Portuguese (Portugal) | `pt-pt` |
| :es: Spanish (Spain)             | `es`    |
| :tr: Turkish                     | `tr`    |

The default translations can be overridden by creating a custom file in `i18n/[code].yaml` that contains the translation strings. You can also use this method to add new languages. If you'd like to share a new translation with the community, please [open a pull request](https://github.com/jpanther/congo/pulls).

### Configuration

In order to be as flexible as possible, a language configuration file needs to be created for each language on the website. By default Congo includes an English language configuration at `config/_default/languages.en.toml`.

The default file can be used as a template to create additional languages, or renamed if you wish to author your website in a language other than English. Simply name the file using the format `languages.[language-code].toml`.

{{< alert >}}
**Note:** Ensure the `defaultContentLanguage` parameter in the [site configuration](#site-configuration) matches the language code in your language config filename.  
{{< /alert >}}

<!-- prettier-ignore-start -->
|Name|Default|Description|
|---|---|---|
|`languageCode`|`"en"`|The Hugo language code for this file. It can be a top-level language (ie. `en`) or a sub-variant (ie. `en-au`) and should match the language code in the filename. Hugo expects this value to always be in lowercase. For proper HTML compliance, set the `isoCode` parameter which is case-sensitive.|
|`languageName`|`"English"`|The name of the language.|
|`displayName`|`"EN"`|The name used when the language appears on the website.|
|`isoCode`|`"en"`|The ISO language code for HTML metadata purposes. It can be a top-level language (ie. `en`) or a sub-variant (ie. `en-AU`).|
|`weight`|`1`|The weight determines the order of languages when building multilingual sites.|
|`rtl`|`false`|Whether or not this is a RTL language. Set to `true` to reflow content from right-to-left. Congo fully supports using RTL and LTR languages at the same time and will dynamically adjust to both.|
|`dateFormat`|`"2 January 2006"`|How dates are formatted in this language. Refer to the [Hugo docs](https://gohugo.io/functions/format/#gos-layout-string) for acceptable formats.|
|`title`|`"Congo"`|The title of the website. This will be displayed in the site header and footer.|
|`description`|_Not set_|The website description. This will be used in the site metadata.|
|`copyright`|_Not set_|A Markdown string containing the copyright message to be displayed in the site footer. If none is provided, Congo will automatically generate a copyright string using the site `title`.|
|`author.name`|_Not set_|The author's name. This will be displayed in article footers, and on the homepage when the profile layout is used.|
|`author.image`|_Not set_|Path to the image file of the author. The image should be a 1:1 aspect ratio and placed in the site's `assets/` folder.|
|`author.headline`|_Not set_|A Markdown string containing the author's headline. It will be displayed on the profile homepage under the author's name.|
|`author.bio`|_Not set_|A Markdown string containing the author's bio. It will be displayed in article footers.|
|`author.links`|_Not set_|The links to display alongside the author's details. The config file contains example links which can simply be uncommented to enable. The order that the links are displayed is determined by the order they appear in the array. Custom links can be added by providing corresponding SVG icon assets in `assets/icons/`.|
<!-- prettier-ignore-end -->

### Menus

Congo also supports language-specific menu configurations. Menu config files follow the same naming format as the languages file. Simply provide the language code in the file name to tell Hugo which language the file relates to.

Menu config files are named with the format `menus.[language-code].toml`. Always ensure that the language code used in the menus configuration matches the languages configuration.

The [Getting Started]({{< ref "getting-started#menus" >}}) section explains more about the structure of this file. You can also refer to the [Hugo menu docs](https://gohugo.io/content-management/menus/) for more configuration examples.

## Theme parameters

Congo provides a large number of configuration parameters that control how the theme functions. The table below outlines every available parameter in the `config/_default/params.toml` file.

Many of the article defaults here can be overridden on a per article basis by specifying it in the front matter. Refer to the [Front Matter]({{< ref "front-matter" >}}) section for further details.

<!-- prettier-ignore-start -->
|Name|Default|Description|
|---|---|---|
|`colorScheme`|`"congo"`|The theme colour scheme to use. Valid values are `congo` (default), `avocado`, `ocean`, `fire` and `slate`. Refer to the [Colour Schemes]({{< ref "getting-started#colour-schemes" >}}) section for more details.|
|`defaultAppearance`|`"light"`|The default theme appearance, either `light` or `dark`.|
|`autoSwitchAppearance`|`true`|Whether the theme appearance automatically switches based upon the visitor's operating system preference. Set to `false` to force the site to always use the `defaultAppearance`.|
|`showAppearanceSwitcher`|`false`|Whether or not to show the appearance switcher in the site footer. The browser's local storage is used to persist the visitor's preference.|
|`enableSearch`|`false`|Whether site search is enabled. Set to `true` to enable search functionality. Note that the search feature depends on the `outputs.home` setting in the [site configuration](#site-configuration) being set correctly.|
|`enableCodeCopy`|`false`|Whether copy-to-clipboard buttons are enabled for `<code>` blocks.|
|`logo`|_Not set_|The relative path to the site logo file within the `assets/` folder. The logo file should be provided at 2x resolution and supports any image dimensions.|
|`mainSections`|_Not set_|The sections that should be displayed in the recent articles list. If not provided the section with the greatest number of articles is used.|
|`robots`|_Not set_|String that indicates how robots should handle your site. If set, it will be output in the page head. Refer to [Google's docs](https://developers.google.com/search/docs/advanced/robots/robots_meta_tag#directives) for valid values.|
|`showScrollToTop`|`true`|When set to `true` the scroll to top arrow is displayed.|
|`homepage.layout`|`"page"`|The layout of the homepage. Valid values are `page`, `profile` or `custom`. When set to `custom`, you must provide your own layout by creating a `/layouts/partials/home/custom.html` file. Refer to the [Homepage Layout]({{< ref "homepage-layout" >}}) section for more details.|
|`homepage.showRecent`|`false`|Whether or not to display the recent articles list on the homepage.|
|`article.showDate`|`true`|Whether or not article dates are displayed.|
|`article.showDateUpdated`|`false`|Whether or not the dates articles were updated are displayed.|
|`article.showAuthor`|`true`|Whether or not the author box is displayed in the article footer.|
|`article.showBreadcrumbs`|`false`|Whether or not breadcrumbs are displayed in the article header.|
|`article.showDraftLabel`|`true`|Whether or not the draft indicator is shown next to articles when site is built with `--buildDrafts`.|
|`article.showEdit`|`false`|Whether or not the link to edit the article content should be displayed.|
|`article.editURL`|_Not set_|When `article.showEdit` is active, the URL for the edit link.|
|`article.editAppendPath`|`true`|When `article.showEdit` is active, whether or not the path to the current article should be appended to the URL set at `article.editURL`.|
|`article.showHeadingAnchors`|`true`|Whether or not heading anchor links are displayed alongside headings within articles.|
|`article.showPagination`|`true`|Whether or not the next/previous article links are displayed in the article footer.|
|`article.invertPagination`|`false`|Whether or not to flip the direction of the next/previous article links.|
|`article.showReadingTime`|`true`|Whether or not article reading times are displayed.|
|`article.showTableOfContents`|`false`|Whether or not the table of contents is displayed on articles.|
|`article.showTaxonomies`|`false`|Whether or not the taxonomies related to this article are displayed.|
|`article.showWordCount`|`false`|Whether or not article word counts are displayed.|
|`article.sharingLinks`|_Not set_|Which sharing links to display at the end of each article. When not provided, or set to `false` no links will be displayed.|
|`list.showBreadcrumbs`|`false`|Whether or not breadcrumbs are displayed in the header on list pages.|
|`list.showTableOfContents`|`false`|Whether or not the table of contents is displayed on list pages.|
|`list.showSummary`|`false`|Whether or not article summaries are displayed on list pages. If a summary is not provided in the [front matter]({{< ref "front-matter" >}}), one will be auto generated using the `summaryLength` parameter in the [site configuration](#site-configuration).|
|`list.groupByYear`|`true`|Whether or not articles are grouped by year on list pages.|
|`sitemap.excludedKinds`|`["taxonomy", "term"]`|Kinds of content that should be excluded from the generated `/sitemap.xml` file. Refer to the [Hugo docs](https://gohugo.io/templates/section-templates/#page-kinds) for acceptable values.|
|`taxonomy.showTermCount`|`true`|Whether or not the number of articles within a taxonomy term is displayed on the taxonomy listing.|
|`fathomAnalytics.site`|_Not set_|The site code generated by Fathom Analytics for the website. Refer to the [Analytics docs]({{< ref "partials#analytics" >}}) for more details.|
|`fathomAnalytics.domain`|_Not set_|If using a custom domain with Fathom Analytics, provide it here to serve `script.js` from the custom domain.|
|`verification.google`|_Not set_|The site verification string provided by Google to be included in the site metadata.|
|`verification.bing`|_Not set_|The site verification string provided by Bing to be included in the site metadata.|
|`verification.pinterest`|_Not set_|The site verification string provided by Pinterest to be included in the site metadata.|
|`verification.yandex`|_Not set_|The site verification string provided by Yandex to be included in the site metadata.|
<!-- prettier-ignore-end -->

---
title: "Front Matter"
date: 2020-08-12
draft: false
description: "All the front matter variables available in Congo."
slug: "front-matter"
tags: ["front matter", "config", "docs"]
---

In addition to the [default Hugo front matter parameters](https://gohugo.io/content-management/front-matter/#front-matter-variables), Congo adds a number of additional options to customise the presentation of individual articles. All the available theme front matter parameters are listed below.

Front matter parameter default values are inherited from the theme's [base configuration]({{< ref "configuration" >}}), so you only need to specify these parameters in your front matter when you want to override the default.

<!-- prettier-ignore-start -->
|Name|Default|Description|
|---|---|---|
|`title`|_Not set_|The name of the article.|
|`description`|_Not set_|The text description for the article. It is used in the HTML metadata.|
|`externalUrl`|_Not set_|If this article is published on a third-party website, the URL to this article. Providing a URL will prevent a content page being generated and any references to this article will link directly to the third-party website.|
|`editURL`|`article.editURL`|When `showEdit` is active, the URL for the edit link.|
|`editAppendPath`|`article.editAppendPath`|When `showEdit` is active, whether or not the path to the current article should be appended to the URL set at `editURL`.|
|`groupByYear`|`list.groupByYear`|Whether or not articles are grouped by year on list pages.|
|`menu`|_Not set_|When a value is provided, a link to this article will appear in the named menus. Valid values are `main` or `footer`.|
|`robots`|_Not set_|String that indicates how robots should handle this article. If set, it will be output in the page head. Refer to [Google's docs](https://developers.google.com/search/docs/advanced/robots/robots_meta_tag#directives) for valid values.|
|`sharingLinks`|`article.sharingLinks`|Which sharing links to display at the end of this article. When not provided, or set to `false` no links will be displayed.|
|`showAuthor`|`article.showAuthor`|Whether or not the author box is displayed in the article footer.|
|`showDate`|`article.showDate`|Whether or not the article date is displayed. The date is set using the `date` parameter.|
|`showDateUpdated`|`article.showDateUpdated`|Whether or not the date the article was updated is displayed. The date is set using the `lastmod` parameter.|
|`showEdit`|`article.showEdit`|Whether or not the link to edit the article content should be displayed.|
|`showHeadingAnchors`|`article.showHeadingAnchors`|Whether or not heading anchor links are displayed alongside headings within this article.|
|`showPagination`|`article.showPagination`|Whether or not the next/previous article links are displayed in the article footer.|
|`invertPagination`|`article.invertPagination`|Whether or not to flip the direction of the next/previous article links.|
|`showReadingTime`|`article.showReadingTime`|Whether or not the article reading time is displayed.|
|`showTaxonomies`|`article.showTaxonomies`|Whether or not the taxonomies that relate to this article are displayed.|
|`showTableOfContents`|`article.showTableOfContents`|Whether or not the table of contents is displayed on this article.|
|`showWordCount`|`article.showWordCount`|Whether or not the article word count is displayed.|
|`showSummary`|`list.showSummary`|Whether or not the article summary should be displayed on list pages.|
|`summary`|Auto generated using `summaryLength` (see [site configuration]({{< ref "configuration#site-configuration" >}}))|When `showSummary` is enabled, this is the Markdown string to be used as the summary for this article.|
|`xml`|`true` unless excluded by `sitemap.excludedKinds`|Whether or not this article is included in the generated `/sitemap.xml` file.|
<!-- prettier-ignore-end -->

---
title: "Partials"
date: 2020-08-10
draft: false
description: "All the partials available in Congo."
slug: "partials"
tags: ["partials", "analytics", "privacy", "comments", "favicons", "icon", "docs"]
---

## Analytics

Congo provides built-in support for Fathom Analytics and Google Analytics. Fathom is a paid alternative to Google Analytics that respects user privacy. If you're interested you can use this affiliate link to [receive $10 credit](https://usefathom.com/ref/RLAJSV) and try the service.

### Fathom Analytics

To enable Fathom Analytics support, simply provide your Fathom site code in the `config/_default/params.toml` file. If you also use the custom domain feature of Fathom and would like to serve their script from your domain, you can also additionally provide the `domain` configuration value. If you don't provide a `domain` value, the script will load directly from Fathom DNS.

```toml
# config/_default/params.toml

[fathomAnalytics]
  site = "ABC12345"
  domain = "llama.yoursite.com"
```

### Google Analytics

Google Analytics support is provided through the internal Hugo partial. Simply provide the `googleAnalytics` key in the `config/_default/config.toml` file and the script will be added automatically.

```toml
# config/_default/config.toml

googleAnalytics = "UA-PROPERTY_ID"
```

### Custom analytics providers

If you wish to use a different analytics provider on your website you can also override the analytics partial and provide your own script. Simply create the file `layouts/partials/analytics.html` in your project and it will automatically include it in the `<head>` of the website.

## Comments

To add comments to your articles, Congo includes support for a comments partial that is included at the base of each article page. Simply provide a `layouts/partials/comments.html` which contains the code required to display your chosen comments.

You can use either the built-in Hugo Disqus template, or provide your own custom code. Refer to the [Hugo docs](https://gohugo.io/content-management/comments/) for further information.

## Favicons

Congo provides a default set of blank favicons to get started but you can provide your own assets to override them. The easiest way to obtain new favicon assets is to generate them using a third-party provider like [favicon.io](https://favicon.io).

Icon assets should be placed directly in the `static/` folder of your website and named as per the listing below. If you use [favicon.io](https://favicon.io), these will be the filenames that are automatically generated for you, but you can provide your own assets if you wish.

```shell
static/
├─ android-chrome-192x192.png
├─ android-chrome-512x512.png
├─ apple-touch-icon.png
├─ favicon-16x16.png
├─ favicon-32x32.png
├─ favicon.ico
└─ site.webmanifest
```

Alternatively, you can also completely override the default favicon behaviour and provide your own favicon HTML tags and assets. Simply provide a `layouts/partials/favicons.html` file in your project and this will be injected into the site `<head>` in place of the default assets.

## Icon

Similar to the [icon shortcode]({{< ref "shortcodes#icon" >}}), you can include icons in your own templates and partials by using Congo's `icon.html` partial. The partial takes one parameter which is the name of the icon to be included.

**Example:**

```go
  {{ partial "icon.html" "github" }}
```

Congo includes a number of built-in icons for social, links and other purposes. You can also provide your own icon assets by including the SVG in `assets/icons/`.

## Extensions

Congo also provides for a number of extension partials that allow for expanding upon base functionality.

### Article link

If you wish to insert additional code after article links, create a `layouts/partials/extend-article-link.html` file. This is especially powerful when combined with the [`badge`]({{< ref "shortcodes#badge" >}}) shortcode which can be used to highlight metadata for certain articles.

### Head and Footer

The theme allows for inserting additional code directly into the `<head>` and `<footer>` sections of the template. These can be useful for providing scripts or other logic that isn't part of the theme.

Simply create either `layouts/partials/extend-head.html` or `layouts/partials/extend-footer.html` and these will automatically be included in your website build. Both partials are injected as the last items in `<head>` and `<footer>` so they can be used to override theme defaults.

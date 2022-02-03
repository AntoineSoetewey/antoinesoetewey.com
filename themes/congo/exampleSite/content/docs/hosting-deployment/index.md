---
title: "Hosting & Deployment"
date: 2020-08-07
draft: false
description: "Learn how to deploy a Congo site."
slug: "hosting-deployment"
tags: ["hosting", "deployment", "docs", "github", "netlify", "render"]
---

There are many ways to deploy your Hugo website built with Congo. The theme is designed to be flexible in almost any deployment scenario.

Congo is built using relative URLs throughout the theme. This enables sites to easily be deployed to sub-folders and hosts like GitHub Pages. There's usually no special configuration required for this to work as long as the `baseURL` parameter has been configured in the `config.toml` file.

The official Hugo [Hosting and Deployment](https://gohugo.io/hosting-and-deployment/) docs are the best place to learn how to deploy your site. The sections below contain some specific theme configuration details that can help you deploy smoothly with certain providers.

**Choose your provider:**

- [GitHub Pages](#github-pages)
- [Netlify](#netlify)
- [Render](#render)
- [Shared hosting, VPS or private web server](#shared-hosting-vps-or-private-web-server)

---

## GitHub Pages

GitHub allows hosting on [GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages) using Actions. To enable this functionality, enable Pages on your repo and create a new Actions workflow to build and deploy your site.

The file needs to be in YAML format, placed within the `.github/workflows/` directory of your GitHub repository and named with a `.yml` extension.

```yaml
# .github/workflows/gh-pages.yml

name: GitHub Pages

on:
  push:
    branches:
      - main # change to the branch name for your project

jobs:
  build-deploy:
    runs-on: ubuntu-20.04
    concurrency:
      group: ${{ github.workflow }}-${{ github.ref }}
    steps:
      - name: Checkout
        uses: actions/checkout@v2
        with:
          submodules: true
          fetch-depth: 0

      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: "latest"

      - name: Build
        run: hugo --minify

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        if: ${{ github.ref == 'refs/heads/main' }}
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_branch: gh-pages
          publish_dir: ./public
```

Push the config file to GitHub and the action should automatically run. It may fail the first time and you'll need to visit the **Settings > Pages** section of your GitHub repo to check the source is correct. It should be set to use the `gh-pages` branch.

{{< screenshot src="github-pages-source.jpg" alt="Screen capture of GitHub Pages source" >}}

Once the settings are configured, re-run the action and the site should build and deploy correctly. You can consult the actions log to check everything deployed successfully.

## Netlify

To deploy to [Netlify](https://www.netlify.com), create a new continuous deployment site and link it to your source code. The build settings can be left blank in the Netlify UI. You will only need to configure the domain you'll be using.

{{< screenshot src="netlify-build-settings.jpg" alt="Screen capture of Netlify build settings" >}}

Then in the root of your site repository, create a `netlify.toml` file:

```toml
# netlify.toml

[build]
  command = "hugo mod get -u && hugo --gc --minify -b $URL"
  publish = "public"

[build.environment]
  NODE_ENV = "production"
  GO_VERSION = "1.16"
  TZ = "UTC"  # Set to preferred timezone

[context.production.environment]
  HUGO_VERSION = "0.87.0"
  HUGO_ENV = "production"
```

This configuration assumes you are deploying Congo as a Hugo module. If you have installed the theme using another method, change the build command to simply `hugo --gc --minify -b $URL`.

When you push the config file to your repo, Netlify should automatically deploy your site. You can check the deploy logs in the Netlify UI to check for any errors.

## Render

Deploying to [Render](https://render.com) is very straightforward and all configuration is via the Render UI.

Create a new **Static Site** and link it to your project's code repository. Then simply configure the build command to be `hugo --gc --minify` and publish directory to be `public`.

{{< screenshot src="render-settings.jpg" alt="Screen capture of Render settings" >}}

The site will automatically build and deploy whenever you push a change to your repo.

## Shared hosting, VPS or private web server

Using traditional web hosting, or deploying to your own web server, is as simple as building your Hugo site and transferring the files to your host.

Make sure that the `baseURL` parameter in `config.toml` is set to the full URL to the root of your website (including any sub domains or sub-folders).

Then build your site using `hugo` and copy the contents of the output directory to the root of your web server and you will be ready to go. By default, the output directory is named `public`.

_If you need a hosting provider, check out [Vultr](https://www.vultr.com/?ref=8957394-8H) or [DigitalOcean](https://m.do.co/c/36841235e565). Signing up using these affiliate links will give you up to $100 in free credit so you can try the service._

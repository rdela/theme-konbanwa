# Konbanwa (Micro.blog version)

![Konbanwa](https://github.com/rdela/theme-konbanwa/blob/master/images/screenshot.png?raw=true)

Konbanwa started as a fork of the [Micro.blog version](https://github.com/microdotblog/theme-hello) of the [Hello Friend](https://github.com/panr/hugo-theme-hello-friend) theme by [@panr](https://github.com/panr).

This is the dark by default, [Micro.blog](https://micro.blog/) version.

### DEMO - <https://theme-konbanwa.netlify.com> ([source](https://github.com/rdela/theme-konbanwa-demo))

---

- [Features](#features)
- [Built-in shortcodes](#built-in-shortcodes)
- [Code highlighting](#code-highlighting)
- [How to start](#how-to-start)
- [How to configure](#how-to-configure)
- [How to add a cover image to your posts](#how-to-add-a-cover-image-to-your-posts)
- [Add-ons](#add-ons)
- [How to run your site](#how-to-run-your-site)
- [How to edit the theme](#how-to-edit-the-theme)
- [How to contribute](#how-to-contribute)
- [Konbanwa theme user list](#konbanwa-theme-user-list)
- [License](#license)

## Features

- **dark/light mode**, depending on your preferences (dark is default, but you can change it)
- great reading experience thanks to [**Inter font**](https://rsms.me/inter/), made by [Rasmus Andersson](https://rsms.me/about/)
- nice code highlighting thanks to [**PrismJS**](https://prismjs.com)
- fully responsive

#### Built-in shortcodes

- **`image`** (prop required: **`src`**; props optional: **`alt`**, **`position`** (**left** is default | center | right), **`style`**)
  - eg: `{{< image src="/img/hello.jpg" alt="Konbanwa" position="center" style="border-radius: 8px;" >}}`
- **`figure`** (same as `image`, plus few optional props: **`caption`**, **`captionPosition`** (left | **center** is default | right), **`captionStyle`**
  - eg: `{{< figure src="/img/hello.jpg" alt="Konbanwa" position="center" style="border-radius: 8px;" caption="Konbanwa!" captionPosition="right" captionStyle="color: red;" >}}`

#### Code highlighting

By default the theme is using PrismJS to color your code syntax. All you need to do is to wrap you code like this:

<pre>
```html
  // your code here
```
</pre>

**Supported languages**: bash/shell, css, clike, javascript, apacheconf, actionscript, applescript, c, csharp, cpp, coffeescript, ruby, csp, css-extras, diff, django, docker, elixir, elm, markup-templating, erlang, fsharp, flow, git, go, graphql, less, handlebars, haskell, http, java, json, kotlin, latex, markdown, makefile, objectivec, ocaml, perl, php, php-extras, r, sql, processing, scss, python, jsx, typescript, toml, reason, textile, rust, sass, stylus, scheme, pug, swift, yaml, haml, twig, tsx, vim, visual-basic, wasm.

## How to start

You can download the theme manually by folowing these steps

  1. Go to <https://github.com/rdela/theme-konbanwa>
  2. Select the `Clone or download` button then Download ZIP
  3. Unzip the downloaded file, rename it to konbanwa, and move it to `themes/konbanwa` in the root directory of your project, creating the themes directory if it does not already exist.

You can also clone it directly to your Hugo folder:

```sh
git clone https://github.com/rdela/theme-konbanwa.git themes/konbanwa
```

If you do not want to make any radical changes, cloning is the best option, because you can get new updates when they are available. To do so, include it as a git submodule:

```sh
git submodule add https://github.com/rdela/theme-konbanwa.git themes/konbanwa
```

## How to configure

The theme does not require any advanced configuration. Just copy:

```
baseurl = "/"
languageCode = "en-us"
theme = "konbanwa"
paginate = 12

[params]
  # dir name of your blog content (default is `content/posts`)
  contentTypeName = "posts"
  # "light" or "dark"
  defaultTheme = "dark"
  # if you set this to 0, only submenu trigger will be visible
  showMenuItems = 2
  # Show reading time in minutes for posts
  showReadingTime = false

[languages]
  [languages.en]
    title = "Konbanwa"
    subtitle = "A mellow theme for Micro.blog"
    keywords = ""
    copyright = ""
    menuMore = "Show more"
    writtenBy = "Written by"
    readMore = "Read more"
    readOtherPosts = "Read other posts"
    newerPosts = "Newer posts"
    olderPosts = "Older posts"
    minuteReadingTime = "min read"
    dateFormatSingle = "2006-01-02"
    dateFormatList = "2006-01-02"

    [languages.en.params.logo]
      logoText = "konbanwa"
      logoHomeLink = "/"
    # or
    #
    # path = "/img/your-example-logo.svg"
    # alt = "Your example logo alt text"

    [languages.en.menu]
      [[languages.en.menu.main]]
        identifier = "about"
        name = "About"
        url = "/about"
      [[languages.en.menu.main]]
        identifier = "showcase"
        name = "Showcase"
        url = "/showcase"
```

to `config.toml` file in your Hugo root directory and change `params` and `languages` fields to suit your project.

**NOTE:** Please keep in mind that currently main menu does not support nesting.

## How to add a cover image to your posts

Adding a cover image to your post is simple and there are two options when you edit your `index.md` file in `content/posts/blog-entry-xy/index.md`:

* Use `cover = "/path/to/absolute/img.jpg"` to link an absolute image
  * Resulting in `https://www.yourpage.com/path/to/absolute/img.jpg`
* Use `cover = "img.jpg"` and `useRelativeCover = true` to link the image relative to the blog post folder
  * Resulting in `https://www.yourpage.com/posts/blog-entry-xy/img.jpg`

## Add-ons

- **Archive** — Theme has built-in `archive` page for main content (see `contentTypeName` variable in config). If you need archive on your blog just copy https://github.com/rdela/theme-konbanwa/blob/master/exampleSite/content/archive.md to your `content` dir. If you need multilangual archives, duplicate `content/archive.md` and add `.Lang` variable, eg: `content/archive.pl.md` (remember to change `url` in duplicated file).
- **Comments** — for adding comments to your blog posts please take a look at `layouts/partials/comments.html` https://github.com/panr/hugo-theme-terminal/blob/master/layouts/partials/comments.html.
- **Extended `<head>`** — if you need to add something inside `<head>` element, please take a look at `layouts/partial/extended_head.html` https://github.com/rdela/theme-konbanwa/blob/master/layouts/partials/extended_head.html
- **Extended `<footer>`** — if you need to add something before end of `<body>` element, please take a look at `layouts/partial/extended_footer.html` https://github.com/rdela/theme-konbanwa/blob/master/layouts/partials/extended_footer.html

## How to run your site

From your Hugo root directory run:

```
$ hugo server -t konbanwa
```

and go to `localhost:1313` in your browser. From now on all the changes you make will go live, so you do not need to refresh your browser every single time.

## How to edit the theme

If you have to override some of the styles, you can do this easily by adding `static/style.css` in your root directory and point things you want to change.

Otherwise, if you really want to edit the theme, you need to install Node dependencies. To do so, go to the theme directory (from your Hugo root directory):

```sh
cd themes/konbanwa
```

and then run:

```sh
npm i
npm run dev
```

or, with yarn:

```sh
yarn
yarn dev
```

Do not forget to build when you are happy with your changes, before you push:

```sh
npm run build
# or
yarn build
```

## How to contribute

If you spot any bugs, please use [Issue Tracker](https://github.com/rdela/theme-konbanwa/issues) or if you want to add a new feature directly please create a new [Pull Request](https://github.com/rdela/theme-konbanwa/pulls).

## `Konbanwa` theme user list

I would be happy to know more about you and what you are doing. If you want to share it, please make a contribution and [add your site to the list](https://github.com/rdela/theme-konbanwa/blob/master/USERS.md)! 📒

## License

Copyright © 2019 [Ricky de Laveaga](https://rdela.com)

The theme is released under the [MIT License](https://github.com/rdela/theme-konbanwa/blob/master/LICENSE.md).

---
title: "Improving my website with simple GoHugo tricks"
date: 2020-11-06T20:54:06+01:00
draft: false
description: "As you may have seen, I started to really work on my website lately..."
tags: ["meta", "software"]
---

As you may have seen, I started to really work on my website lately, I first switched to a homemade theme ([the article can be found here]({{< ref "/blog/2020/may2020-hugo-website.md" >}})) and then started to work on smaller tweaks of the theme while adding cool features such as Twitter's cards or integrating the [OpenGraph](https://ogp.me/) protocol.

As you may know it, my website uses the [GoHugo](https://gohugo.io/) website generator ([code under MIT license by the way](https://forge.tedomum.net/jae/main-website)) which is super easy to use and has a really good integration with Gitlab Pages.

Getting OpenGraph to work is one of the first really easy steps to have a nicer presence when your website is linked to another place. It basically shows as a little card with a bit of information such as the name of the website, the author, the description of the page and an image. Twitter's card are basically the same thing but for Twitter.

To add OpenGraph to your pages, just add this in the `<head>` of your template:

```
    {{ template "_internal/opengraph.html" . }}
```

The same goes on for Twitter's cards:

```
    {{ template "_internal/twitter_cards.html" . }}
```

At the end, the OpenGraph should produce an output like this:

{{< highlight html "linenos=table" >}}

<meta property="og:site_name" content="Jae" />
<meta property="og:locale" content="nn_NO" />
<meta property="og:type" content="article" />
<meta property="og:url" content="http://jae.moe/blog/nov2020-improvements/" />
<meta property="og:title" content="Improving my website with simple GoHugo tricks" />
<meta property="og:image" content="http://jae.moe/images/logo.svg" />
<meta property="og:description" content="As you may have seen, I started to really work on my website lately..." />
{{< / highlight >}}

And the Twitter's cards:

{{< highlight html "linenos=table" >}}

<meta name="twitter:card" content="summary"/>
<meta name="twitter:title" content="Improving my website with simple GoHugo tricks"/>
<meta name="twitter:description" content="As you may have seen, I started to really work on my website lately..."/>
{{< / highlight >}}

Some other improvements are regarding custom shortcodes, [like the one I made for spoilers](https://forge.tedomum.net/jae/main-website/-/blob/master/layouts/shortcodes/spoiler.html) which shows like this:

Which generates this HTML output:

As you can see, this is actually really easy to improve small bits of your website if you really want to.

However, if you are not the maintainer of the theme you are currently using, open an issue telling the maintainer(s) those shortcodes actually exists or if you can, contribute!

However, [more shortcodes are available on GoHugo's website](https://gohugo.io/content-management/shortcodes/) including ones for Youtube, Instagram or Twitter.

That’s all for today,
I'll see you next time!
If you like my content, [don't forget to subscribe throught RSS](/blog/index.xml)!

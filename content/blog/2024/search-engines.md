---
title: "Search engines sucks - paid ones won't fix it"
description: "Over the past few years, enshittification also reached our search engines, including paid ones."
date: 2024-02-13
draft: true
---

Hey there everybody!

Over the past few years, the process of enshittification[^1] started to englobe all aspect of software.  
Chat apps started getting nonsensical subscriptions and (paid) additions[^2], the use of APIs got restricted on large websites[^3], and of course, search engines were affected as well.

In this, all search engines are affected (unless it has some aspects vetted manually) so switching will have little to no effect.

## Ads, ads everywhere

When submitting a query on Google, you'll first be presented with either:

- A banner of sponsored products (mostly for shopping, for instance `best laptop`)
- A bunch of links looking like legitimate search results but that are in fact sponsored (for instance `antivirus`)

On some queries, you will even have another panel on the right of the search result showing a bunch of sponsored products (for instance `antivirus`).

Bing itself isn't much better, doing the exact same thing with the added benefit that the first actual search results are redirecting to scam websites (for instance the wonderful `antivirusguide[.]com`, `softwarelab[.]org` or even `top10antivirussoft[.]com`).

Most of those websites are usually made to either bring you and make you stay as long as possible on a page full of ads or make you purchase of sponsored product. That's when the website isn't a straight up "download my virus" or "call center" kind of scam.

Ads themselves only are the tip of the iceberg and all of those scam results actually bring out two other reasons search engines are getting worse and worse.

### SEO

SEO, or "Search Engine Optimization" is trying to get more natural traffic from search engine by adding tags, information and a ton of other stuff to your website so it appears higher on the search results.

The wonderful world of SEO is also how we end up having in the search results, a bunch of websites all linking to each other, repeating the same things over and over again and stuffing keywords everywhere.

SEO overall is just an arms race to be the first in keyword searches that only made the web a worse place.

### AI

_Oh boy, here we go again._

With the advent of LLMs, we now have software capable of hallucinating large amounts of text.  
Can you guess who would want large amounts of text to be generated? That's right, SEO spammers!

What a world we live in, we can now automate the whole process?  
Need a tutorial on how to change your clock settings on an iPhone? ChatGPT is here to help!

You can now generate huge masses of uninformative content easily and automate the whole process with a simple script and API requests.

There are some search engines, for instance Bing, that will also just incentivize you to use their AI chatbot instead of looking up stuff yourself (and spoilers, AIs can't be trusted[^4]).

### Other misc issues

There are also a bunch of other issues including, but not limited to:

- Linking to social media such as Facebook, Twitter or Instagram - Almost all content on those websites being gated by login screens and providing no information whatsoever, it would make no sense to even include those in search results
- Not having official documentations first - When looking up information about a product, library or else, the official support or documentation website should be linked first since useful information is obviously there

## Paid search engines will fix it, right?

As you may know, I was a beta tester for Kagi, a paid search engine.  
Consider this post as my final review of it if you will.

Let's set aside for a moment how weird the idea of a paid search engine sounds.

Kagi boasts about:

- No ads (due to the paid nature)
- Better results (due to combining multiple indexes with their own)
- Results filtering

I've used it for about a year and half total with another try end of last year and the conclusion is: it's not that good.

While ads aren't present as promised and that the result filtering is good, results themselves suck as much as on any other search engine.  
Don't take my word for it, you can in fact test Kagi with 100 searches for free per month.

Overall, I don't see any good enough reasons to pay for it as even the filtering can be achieved on any other search engine (it was just made into a neat little interface there).

There are other paid search engines, but not notable enough yet to warrant their own tests for now (future blog posts will be posted once they do).

## What can we do?

Being honest, not much, as search engines are essential for basically everyday life.  
As we can't really swap to another one to magically make the problem disappear, I have some tips to make existing one _more livable_.

One first method is using operators to refine your search as much as possible (Google for sure will support those as well as some others):

- `"something"` will only show results having `something` in it
- `filetype:` will only show results for that particular filetype
- `site:` will only show results within a specific domain
- `intitle:` searches for a word in the title
- `allintitle:` same as the previous one but with multiple words
- `inurl:` searches for a word in the url
- `allinurl:` same as the previous one but with multiple words
- `intext:` searches for a word in the text of the page
- `allintext:` you get the gist, same as the previous one but with multiple words
- `-word` will exclude the term from results, in this instance the term being `word`
- `before:` and `after:` will only search for result before or after the specified date

I can also recommend specifying websites when writing queries; for instance, instead of `how to do X`, instead search for `how to do X reddit` which will usually show more informative content.

Some websites that are great for queries:

- Wikipedia
- Reddit
- YouTube
- StackOverflow
- StackExchange
- GitHub
- ArchWiki
- Gentoo Wiki

I can also recommend that for some queries, you use the internal search of some websites.  
For instance, on an issue concerning code, I always have more luck using the internal search of StackOverflow.  
If you want to see quickly what is something or look up some historical event, use Wikipedia's search.  
But don't stop at websites I gave you, found a good and reliable source for what you need? Add it on the pile.

My other big piece of advice is to **get a damn ad blocker**.  
I can warmly recommend [uBlock Origin](https://github.com/gorhill/uBlock) as it's fast, always up-to-date and can block many more annoyances than just ads and tracking.  
And remember, uBlock origin works best on Firefox[^5]!

While writing this post, someone posted a link in a chat to the [OpenWebSearch](https://openwebsearch.eu/) project, funded by the European Union.  
While the intention is good, it remains to be seen if the whole thing won't just be cannibalized and killed in the background by private companies.

For my part, I'll stay on my good old [SearXNG](https://docs.searxng.org/) as it aggregates results from multiple search engines and has a nice filtering syntax[^6].

[^1]: https://en.wikipedia.org/wiki/Enshittification
[^2]: https://support.discord.com/hc/en-us/articles/17828465914263-Profile-Effects
[^3]: https://en.wikipedia.org/wiki/2023_Reddit_API_controversy
[^4]: https://labs.ripe.net/author/kathleen_moriarty/the-llm-misinformation-problem-i-was-not-expecting/
[^5]: https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox
[^6]: https://docs.searxng.org/user/search-syntax.html

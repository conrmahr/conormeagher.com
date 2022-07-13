---
templateEngineOverride: md
metaTitle: RSS Feed in a 11ty site
metaDescription: How to add an RSS Feed in a 11ty site
title: RSS Feed in a 11ty site 
description: How to add an RSS Feed in a 11ty site
featuredImg: rss-11ty
subHeading: How to add an RSS Feed in a 11ty site.
tags: ['RSS', '11ty', 'Web Development']
date: 2022-07-12T19:00Z
updated:
published: true
---

<div class="col-start-3 col-end-9">

https://twitter.com/davatron5000/status/1308404187299012616?s=20&t=e4vdBOpt8sEjbCJp21Qz7A

[Dave Rupert](https://daverupert.com) is right. Really Simple Syndication or [RSS](https://en.wikipedia.org/wiki/RSS) is a great way for people to digest their favorite blog articles with a RSS reader of their choice not be bombarded with ads, click-bait, and spam. So why not do your readers a favor and add it to your 11ty blog?

### Install package
Start in your 11ty project folder and install this package.
```bash
npm install @11ty/eleventy-plugin-rss --save-dev
```

### Include in your 11ty configuration
In the `.eleventy.js` file, require the plugin and include it in the `module.exports` function with any other plugins you may have.
```js
const pluginRss = require("@11ty/eleventy-plugin-rss");

module.exports = function(eleventyConfig) {
    eleventyConfig.addPlugin(pluginRss);
};
```

### Add to feed metadata
In the `_data/metadata.json` file, add the unique metadata for the feed.
```json
{
  "feed": {
    "subtitle": "I am writing about my experiences as a circus clown.",
    "filename": "feed.xml",
    "path": "/feed.xml",
    "id": "https://example.com/"
  }
},
```
### Create a RSS feed
From your top-level of your 11ty project folder, create this template file.
```bash
touch src/feed.xml
```

Atom has several advantages over RSS: less restrictive licensing, IANA-registered MIME type, XML namespace, URI support, RELAX NG support. [^1] Knowing this, we will copy and paste the Atom format to produce our feed template. Other formats are available such as RSS and JSON. [^2]

```xml
---
# Metadata comes from _data/metadata.json
permalink: "{{ metadata.feed.path }}"
eleventyExcludeFromCollections: true
---
<?xml version="1.0" encoding="utf-8"?>
<feed xmlns="http://www.w3.org/2005/Atom">
	<title>{{ metadata.title }}</title>
	<subtitle>{{ metadata.feed.subtitle }}</subtitle>
	{% set absoluteUrl %}{{ metadata.feed.path | url | absoluteUrl(metadata.url) }}{% endset %}
	<link href="{{ absoluteUrl }}" rel="self"/>
	<link href="{{ metadata.url }}"/>
	<updated>{{ collections.posts | rssLastUpdatedDate }}</updated>
	<id>{{ metadata.feed.id }}</id>
	<author>
		<name>{{ metadata.author.name }}</name>
		<email>{{ metadata.author.email }}</email>
	</author>
	{%- for post in collections.posts | reverse %}
	{% set absolutePostUrl %}{{ post.url | url | absoluteUrl(metadata.url) }}{% endset %}
	<entry>
		<title>{{ post.data.title }}</title>
		<link href="{{ absolutePostUrl }}"/>
		<updated>{{ post.date | rssDate }}</updated>
		<id>{{ absolutePostUrl }}</id>
		<content type="html">{{ post.templateContent | htmlToAbsoluteUrls(absolutePostUrl) }}</content>
	</entry>
	{%- endfor %}
</feed>
```
That's it. You now have a RSS feed on your 11ty website when you serve or build the project.

Check out mine and subscribe!
https://conormeagher.com/feed/

[^1]: ["RSS compared with Atom"](https://en.wikipedia.org/wiki/RSS#RSS_compared_with_Atom). Retrieved June 14, 2022
[^2]: ["Sample Feed Templates"](https://www.11ty.dev/docs/plugins/rss/#sample-feed-templates). Retrieved July 12, 2022
</div>

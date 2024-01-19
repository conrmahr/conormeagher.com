---
templateEngineOverride: njk,md
metaTitle: Announcing Discord-RSS
metaDescription: A new RSS Reader bot for Discord
title: Announcing Discord-RSS
description: A new RSS Reader bot for Discord
featuredImg: discord-rss-logo
subHeading: A new RSS Reader bot for Discord
tags: ["Discord", "RSS", "Node.js", "Svelte-Kit", "Auth.js"]
date: 2024-01-10T17:00:00Z
updated:
published: true
---

<div class="col-start-3 col-end-9">

Announcing a fork of [Discord-RSS](https://github.com/3ventic/discord-rss) using the latest versions of [Node.js](https://nodejs.org), [Svelte-Kit](https://kit.svelte.dev) and [Auth.js](https://authjs.dev/). This unique tool will provide an innovative way to manage and share RSS feed content across Discord channels, with a focus on simplicity and speed.

### Unique Features
The new Discord-RSS bot boasts several unique features that will enhance user experience and functionality.

### Simple Web Management UI
Using modern [TailwindCSS](https://tailwindcss.com) to incorporates a simple web management UI. This is a significant feature as it allows non-technical users to easily manage the admin user-interface. No coding skills required. It eliminates the intimidation that often comes with managing technical platforms, making it accessible to a wider range of users.

{% figure 'discord-rss-web', 'Discord RSS Feed Manager Screenshot', 'Discord RSS Feed Manager Screenshot' %}

### User Mentions in Posts
This new Discord-RSS bot also brings the addition of cleaner user mentions in posts. This feature enhances the functionality by showing the ownership of posts. It also provides instant notifications to the author when their post is shared.

{% figure 'discord-rss-webhook', 'Webhook Post Screenshot', 'Webhook Post Screenshot' %}

### Enhanced Logging
The runner outputs more robust logs that gives better observability on the bot. This better helps to troubleshoot misconfigured, timed-out, invalid, RSS feeds with fun emojis. 🎉

{% figure 'discord-rss-runner', 'Runner Logging via CLI', 'Runner Logging via CLI' %}

### Post to Any Channel Webhook
The Node.js runner gives users the flexibility to post to any channel webhook. This is a notable improvement from most RSS integrations to Discord which limit you to just the channel or server. The webhook is only tied to a channel and is not restricted by any other factors.

### Power of Node.js, Svelte, and Redis
The bot leverages the power of three key technologies: Node.js, Svelte, and Redis.

Svelte-Kit provides a host of great features out of the box. It offers *fast setup, fast development, fast builds, fast page loads, and fast navigation*[^1]. At the same time, [learn.svelte.dev](https://learn.svelte.dev/) is a great way to learn with user docs integrated with a coding playground. This makes it very easy to build and learn quickly. The coding sytax has got an old-school "HTML written on Notepad.exe" feel to it with HTML, JavaScript, and Svelte all in one file. Meanwhile, Node.js is just a trusty way to have of a script runner digesting RSS Feeds via its built-in fetch API. The combination of these two technologies results in a high-performing and efficient tool.

Where do you store all the RSS feed meta? Since only an object of feeds is needed, a Redis instance is more than enough because it's a good caching layer and it has lack of complexity. Svelte-Kit can handle the rest with writable [svelte/stores](https://svelte.dev/docs/svelte-store#readable) and [redis/ioredis](https://github.com/redis/ioredis) for *a robust, performance-focused, and full-featured Redis client for Node.js*[^2].

### Promoting RSS Feed Use
The Discord RSS is not just a tool; it is a medium to promote the use of adding [RSS feeds](https://aboutfeeds.com/) for personal and professional blogs. By integrating this tool, Discord users can easily promote their latest blog posts. Adding an RSS feed to their blog ensures that their content can be easily added to Discord RSS, thereby increasing visibility and engagement.

### Open-Sourced
The best feature of all is that this is available for anyone! Self-host this repo on a VM or locally and get it integrated with your own Discord server. Bug issues and features are welcomed too. Check it out: 

https://github.com/conrmahr/discord-rss

[^1]: ["SvelteKit • Web development, streamlined"](https://kit.svelte.dev). Retrieved January 18, 2024.
[^2]: ["redis/ioredis: 🚀 A robust, performance-focused, and full-featured Redis client for Node.js."](https://github.com/redis/ioredis). Retrieved January 18, 2024.
</div>
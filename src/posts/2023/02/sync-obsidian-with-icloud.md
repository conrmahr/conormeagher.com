---
templateEngineOverride: njk,md
metaTitle: Sync Obsidian with iCloud 
metaDescription: Use your existing iCloud space to sync your Obsidian vault across multiple devices.
title: Sync Obsidian with iCloud 
description: Use your existing iCloud space to sync your Obsidian vault across multiple devices.
featuredImg: obsidian-logo
subHeading: Use your existing iCloud space to sync your Obsidian vault across multiple devices.
tags: ['Obsidian', 'iCloud', 'Backup', 'Productivity']
date: 2023-02-28T17:00:00Z
updated:
published: true
---

<div class="col-start-3 col-end-9">

https://twitter.com/bencodezen/status/1458484105331585028

Being a Obsidian Power-User, I always wanted to update my notes from any of my devices from the beginning but didn't have a great use case to host my notes with the paid version of [Obsidian Sync](https://obsidian.md/sync). iCloud Drive would be the best option and it's free! These steps are not the only way to sync with iCloud but I found this order to be easiest.

### Requirements
- [Obsidian for macOS](https://obsidian.md/download)
- [Obsidian for iOS or iPadOS](https://apps.apple.com/us/app/obsidian-connected-notes/id1557175442) 
- [Apple ID account](https://appleid.apple.com/)

### Setup

1. Setup and enable iCloud Drive on all devices you want to sync.[^1]

1. Open the Obsidian iOS or iPadOS app and select "Create new vault".

1. Type a vault name and check "Store in iCloud" then tap "Create".

{% figure 'ios-store-in-icloud', 'iOS Obsidian - Store in iCloud', 'iOS Obsidian - Store in iCloud' %}

1. Move to your macOS device and open the Obsidian app.

1. Open the newly create vault with File > Open Vault... 

1. Browse to iCloud Drive > Obsidian > `vault name` and click "Open".

1. Create a new note for testing with File > New Note

{% figure 'macos-hello-world', 'macOS Obisidan - Hello World', 'macOS Obisidan - Hello World' %}

1. Return to your Obsidian app on iOS and see if your file synced.

{% figure 'ios-hello-world', 'iOS Obsidian - Hello World', 'iOS Obsidian - Hello World' %}

**Success!**

**Existing Obsidian Users: Copy all your previous vault files and directory structure to this iCloud folder*

*Note: You can also download [iCloud Drive for Windows](https://support.apple.com/en-us/HT204283) and keep your Obsidian vault insync on a Windows device.

I've got one vault synced across, macOS, iOS, iPadOS, and Windows 11 devices.

[^1]: ["Set up iCloud Drive"](https://support.apple.com/en-us/HT204025). Retrieved November 3, 2022.

</div>
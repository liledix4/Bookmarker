# Bookmarker

App for saving bookmarks offline, using Markdown files as "notepads". It's supposed to come in a variety of flavors: Electron app (for Windows, macOS and Linux), browser extension (for Chromium and Firefox) and Android app.

## How is it supposed to work?

Electron/Android apps work differently from a browser extension, but there are things in common.

## Common

You can have various notepads. Every notepad is a Markdown file with one big list of notes. Every note can have hashtags, URLs and custom text. Additionally you can attach images and files to the notes. Everything is saved locally, there's no Internet connection required, unless you use specific online features like getting titles for YouTube videos.

Bookmarker parses all Markdown files, turns them into notepads, saves notepads to the local storage, and creates indexes for quicker search (especially it's helpful for extension to read saved URLs).

### Electron/Android

You can choose a folder for storing Markdown files. Bookmarker will open all files as notepads.

- App can make an attempt to open the webpage from link without using another web browser for it – but this is tricky, since, most likely, IFRAME will be utilized and some websites are forbidding using it.

### Browser extension

Extensions are very limited by nature. It's not possible to read folders, and files can only be opened manually one by one. Extension can store multiple notepads, and it's possible to export notepads as Markdown. It's possible to update extension's notepads by rewriting them with Markdown file contents. The thing is: **it's all manual.**

I could try to create the local server for Electron app, so extension could read its database.

- Extension can have a brilliant feature. It can check currently opened website in the list of saved URLs – it can even check a match of domain.
- It'll be possible to create bookmarks in notepads using context menu or extension window.
- Browser bookmarks can be added to the notepads, if you're thinking about data migration. ^^
- I could add a feature of reading the website itself and finding saved URLs from links.
- Text highlighting – I think it could be possible too. You select text, choose any color you prefer, add the notes (optionally with your own comments) to the notepads using context menu or hotkeys – and when you reopen the page, saved text will be highlighted. When you hover (or tap) the highlighted text with your written comment, it'll be displayed.

## Inspirations

- Domain Bookmark: https://chromewebstore.google.com/detail/domain-bookmark/bdenbnecgoejgedenceiggneklpbmlio
- Obsidian Web: https://github.com/coddingtonbear/obsidian-web

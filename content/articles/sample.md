---
title: Introduction
description: Learn how to use @nuxtjs/content.Learn how to use @nuxtjs/content.Learn how to use @nuxtjs/content.
tags: ['sample', 'test']
image: '/3000.png'
---

# Lorem ipsum

## dolor—sit—amet

### consectetur &amp; adipisicing

### 目次テスト

#### elit

```js{1,3-5}[server.js]
const http = require('http')
const bodyParser = require('body-parser')

http.createServer((req, res) => {
  bodyParser.parse(req, (error, body) => {
    res.end(body)
  })
}).listen()
```

##### elit

Here's a simple footnote,[^1] and here's a longer one.[^bignote]

## Links

<nuxt-link to="/articles">Nuxt Link to Blog</nuxt-link>

<a href="/articles">Html Link to Blog</a>

[Markdown Link to Blog](/articles)

<a href="https://nuxtjs.org">External link html</a>

[External Link markdown](https://nuxtjs.org)

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ my code }`

    Add as many paragraphs as you like.
# Portfolio

A portfolio for my good friend and copywriter Joph.

This will be a static website backed by Dropbox for easy editing with an automated build *in the cloud*. The `/src` directly will come from Dropbox. A Dropbox webhook will hit a little web server that'll kick off a build and then copy `/build` to S3 for serving. So to recap:

* easy editing
* the cheapest to host
* the fastest response times

#### building

```bash
node build.js
```

or for dev (watching + serving)

```bash
node build.js dev
```

or as a module

```javascript
var build = require('./build');

build();
```

#### running the build trigger server

```bash
node app.js
curl -XPOST localhost:8080/build       # If you don't care if the build failed
curl -XPOST localhost:8080/build_sync  # If you care if the build failed
```

#### adding a page

```markdown
---
title: About
date: 2015-01-01
---

I started out as a simple man.
```

Options for metadata are:

* `title`
* `date`
* `template`: defaults to `page`, but can also be: `layout`.

#### Markdown overview

[Markdown syntax](http://daringfireball.net/projects/markdown/syntax)

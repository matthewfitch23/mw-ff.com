# mw-ff.com

My personal blog built with Jekyll and hosted on mw-ff.com.

## Setup

1. Install Ruby and Bundler
2. Install dependencies:
   ```bash
   bundle install
   ```

## Local Development

To build and serve the site locally:

```bash
bundle exec jekyll serve
```

The site will be available at `http://localhost:4000`

## Building for Production

To build the static site:

```bash
bundle exec jekyll build
```

The generated site will be in the `_site` directory.

## Adding New Posts

Create a new file in the `_posts` directory with the format:
```
YYYY-MM-DD-title.markdown
```

Add front matter at the top:
```yaml
---
layout: post
title: "Your Post Title"
date: YYYY-MM-DD HH:MM:SS +0000
categories: your-category
---
```

Then write your content in Markdown below the front matter.

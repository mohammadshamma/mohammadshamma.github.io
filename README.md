# mohammadshamma.github.io

Personal blog built with [Hugo](https://gohugo.io/) using the [hugo-blog-awesome](https://github.com/hugo-sid/hugo-blog-awesome) theme.

## Prerequisites

- [Hugo](https://gohugo.io/installation/) (extended version recommended)
- Git

## Setup

Clone the repo and initialize the theme submodule:

```bash
git clone https://github.com/mohammadshamma/mohammadshamma.github.io.git
cd mohammadshamma.github.io
git submodule update --init --recursive
```

## Run locally

```bash
hugo server -D
```

The site will be available at http://localhost:1313. The `-D` flag includes draft posts.

## Add a blog post

```bash
hugo new posts/my-post-title.md
```

This creates `content/posts/my-post-title.md` with default front matter. Edit the file to write your post, then set `draft = false` when ready to publish.

Front matter fields:

| Field | Description |
|-------|-------------|
| `title` | Post title |
| `date` | Publication date |
| `draft` | Set to `false` to publish |
| `tags` | List of tags, e.g. `["go", "hugo"]` |

## Publish

Build the static site:

```bash
hugo
```

Output goes to the `public/` directory (excluded from version control). Deploy by pushing to the `master` branch — GitHub Pages will serve the site automatically if configured.

## Project structure

```
.
├── archetypes/       # Templates for new content
├── assets/           # Images and other assets (e.g. avatar.jpg)
├── content/
│   └── posts/        # Blog posts (Markdown files)
├── themes/
│   └── hugo-blog-awesome/  # Theme (git submodule)
└── hugo.toml         # Site configuration
```

## Configuration

Edit `hugo.toml` to update:

- `baseURL` — your GitHub Pages URL (e.g. `https://mohammadshamma.github.io/`)
- `params.author` — your name, bio, and avatar
- `params.socialIcons` — links to your social profiles

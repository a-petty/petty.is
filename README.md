# petty.is

A handcrafted blog built with plain HTML & CSS. No frameworks, no build step, no nonsense.

## Structure

```
├── index.html    # Homepage with featured post + post grid
├── post.html     # Individual post template (duplicate & edit for each post)
├── about.html    # About page
├── style.css     # All styles — edit colors/fonts via CSS variables at top
└── README.md     # You're here
```

## How to Write a New Post

1. Copy `post.html` and rename it (e.g., `my-new-post.html`)
2. Update the `<title>`, meta description, article tag, title, subtitle, date, and body content
3. Add the post to the grid on `index.html`
4. Deploy

## Customization

All design tokens are CSS custom properties in `style.css`:

```css
:root {
  --ink: #1a1714;         /* Primary text */
  --paper: #f4f0e8;       /* Background */
  --accent: #c4401a;      /* Links, highlights, drop cap */
  --muted: #8a8279;       /* Secondary text */
  --rule: #c9c2b6;        /* Borders & dividers */
  --font-display: ...     /* Headlines */
  --font-body: ...        /* Body text */
  --font-mono: ...        /* Code, labels, meta */
}
```

## Hosting Options

Since this is just static files, you can host it almost anywhere:

**GitHub Pages** (free)
- Push to a repo, enable Pages in settings, point your domain's DNS

**Netlify** (free tier)
- Drag and drop the folder, or connect a Git repo
- Custom domain + HTTPS in one click

**Cloudflare Pages** (free tier)
- Connect your repo, zero-config for static sites
- Great CDN performance, and you may already have your DNS there

**Vercel** (free tier)
- `npx vercel` from this directory
- Automatic deployments from Git

For all of these, you'll point your `petty.is` domain via DNS (usually an A record or CNAME) to the host's provided address.

## Adding Images

Replace the placeholder `<div class="placeholder-img">` blocks with actual `<img>` tags:

```html
<div class="hero-image">
  <img src="images/my-photo.jpg" alt="Description of the image">
</div>
```

## RSS

You'll want to create an `rss.xml` file for subscribers. Here's a minimal structure to start with — update it each time you publish:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<rss version="2.0">
  <channel>
    <title>petty.is</title>
    <link>https://petty.is</link>
    <description>Writing by Petty</description>
    <item>
      <title>Post Title</title>
      <link>https://petty.is/post.html</link>
      <pubDate>Wed, 06 Mar 2026 00:00:00 GMT</pubDate>
      <description>Post excerpt here.</description>
    </item>
  </channel>
</rss>
```

---

Built with stubbornness and `<table>`-free HTML.

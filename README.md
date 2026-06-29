# Lead Continuity LLC — Website

A2P 10DLC-compliant website for Lead Continuity LLC, built with [Astro](https://astro.build).

## Commands

| Command           | Action                               |
|:----------------- |:------------------------------------ |
| `npm install`     | Install dependencies                 |
| `npm run dev`     | Start dev server at `localhost:4321` |
| `npm run build`   | Build production site to `./dist/`   |
| `npm run preview` | Preview the build locally            |

## Publishing a Blog Post

Blog posts are Markdown files in `src/content/blog/`. Astro automatically discovers them and generates pages at `/blog/<slug>`.

### Step-by-step

1. Create a new `.md` file in `src/content/blog/`:
   
   ```
   src/content/blog/my-new-post.md
   ```

2. Add the frontmatter at the top of the file:
   
   ```markdown
   ---
   title: "Your Post Title"
   description: "A short description for SEO and the blog listing page."
   pubDate: 2026-07-15
   heroImage: "/assets/favicon.svg"
   ---
   
   Your post content goes here in Markdown.
   ```

3. Write your content below the frontmatter using standard Markdown (headings, lists, links, images, code blocks, etc.).

4. Save the file. The dev server hot-reloads automatically. If using the build, run `npm run build` to regenerate.

### Frontmatter fields

| Field         | Required | Description                                         |
|:------------- |:-------- |:--------------------------------------------------- |
| `title`       | Yes      | Post headline                                       |
| `description` | Yes      | Short summary for SEO and the blog index.            |
| `pubDate`     | Yes      | Publication date (YYYY-MM-DD)                       |
| `updatedDate` | No       | Last updated date (shown if different from pubDate) |
| `heroImage`   | No       | URL to a hero image for the post                    |

### Slug rules

The URL slug is derived from the filename (without `.md`):

- `src/content/blog/why-businesses-lose-leads.md` → `/blog/why-businesses-lose-leads`
- Use lowercase, hyphens instead of spaces. No special characters.

## Project Structure

```
src/
  layouts/       Base HTML layout (head, nav, footer)
  components/    Nav, Footer
  styles/        global.css (full design system)
  pages/         All page routes
  content/       Blog markdown posts
    blog/
public/
  assets/        Logo, headshot, favicon
dist/            Production build output
```

## A2P Compliance

This site is A2P 10DLC compliant with:

- Dual consent checkboxes (unchecked by default)
- Non-sharing clause in Privacy Policy
- SMS Program page at `/sms`
- Privacy Policy & Terms linked from every page footer
- noindex/nofollow (compliance site, not for SEO)

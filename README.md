# garrettdbates.com

Personal site and blog for Garrett D. Bates built with [Jekyll](https://jekyllrb.com/) and the Minima theme. The repo hosts the content served at https://garrettdbates.com and contains a few custom layouts, embeds, and redirects layered on top of the stock Jekyll stack.

## Getting Started
- Ensure Ruby 3.1+ and Bundler are installed (`gem install bundler` if needed).
- Install dependencies: `bundle install`
- Run the site locally: `bundle exec jekyll serve --livereload`
  - Visit http://127.0.0.1:4000 to preview changes. The site reloads when you save files, but edits to `_config.yml` require restarting the server.
- Build for production: `JEKYLL_ENV=production bundle exec jekyll build`
  - The generated site is written to `_site/`.

## Project Structure
- `_posts/` holds published articles. Each file uses standard Jekyll front matter plus optional fields that the custom post layout reads (`read_time`, `view_count`, `comment_count`, `last_modified_at`).
- `2024/` contains redirect stubs to preserve historical URLs. Each Markdown file there sets `layout: redirect` and a `redirect` target.
- `_layouts/` overrides Minima templates. Notably `post.html` adds share buttons, view/comment counters, and GA snippets, while `redirect.html` handles legacy URL redirects and analytics.
- `_includes/` stores reusable partials (Mailchimp embed, RSS subscribe button, share buttons, etc.).
- `assets/` contains Sass overrides (`main.scss`) and static article assets grouped by slug.
- `_config.yml` defines site metadata, plugins, and permalink structure. `CNAME` pins the custom domain for GitHub Pages.

## Writing Content
- Use the bundled `jekyll-compose` plugin to scaffold new entries. Example:
  - `bundle exec jekyll compose "My New Post" --collection posts`
  - `bundle exec jekyll compose "Feature Draft" --collection drafts`
- Add optional front matter values if you want estimated read time, view counts, or comment counts rendered with the post metadata.
- Assets referenced in posts should live under `assets/<slug>/` so they are copied during the build.

## Deployment
- The project is configured for GitHub Pages with a custom domain. Pushes to the default branch trigger the build that serves `https://garrettdbates.com`.
- Update the `CNAME` file if the domain ever changes.
- Remember to run `bundle update` periodically to keep Jekyll, Minima, and plugin dependencies current.

## Troubleshooting
- If dependencies change, re-run `bundle install`.
- Delete `.jekyll-cache/` and `_site/` if you encounter stale assets or layout issues before rebuilding.
- Check `bundle exec jekyll doctor` for configuration warnings.

# squiffle.uk

Static site built with [Hugo](https://gohugo.io) and the [Blowfish](https://blowfish.page) theme.

## Editing pages

Every page is a Markdown file in `content/`:

| File                          | Page                |
|-------------------------------|---------------------|
| `content/_index.md`           | Home                |
| `content/civicrm.md`          | CiviCRM             |
| `content/civicrm-costs.md`    | CiviCRM costs       |
| `content/case-study-step.md`  | Case study – Step   |
| `content/civicrm-support.md`  | Support & upgrades  |
| `content/data-sovereignty.md` | Data sovereignty    |
| `content/it-review.md`        | IT Review           |
| `content/contact-us.md`       | Contact us          |
| `content/about-us.md`         | About us            |

- The top of each file (between `---` lines) holds the page title.
- To add a page, copy an existing file, change the title, then add it to the menu in `hugo.toml`.
- Images live in `static/images/`. Put one beside the text with:
  `{{< img src="/images/civicrm-logo.png" alt="CiviCRM logo" width="200" align="right" >}}`
- `{{< civibadges >}}` shows the CiviCRM Partner and Contributor badges. To update them, replace
  the two `civibadge-*.png` files in `static/images/` with new ones from
  https://civicrm.org/providers/Squiffle-Consulting (or edit `layouts/shortcodes/civibadges.html`).
- Homepage cards use `{{< feature ... >}}` blocks; copy an existing one to add another.

## Preview locally

    hugo server

then open http://localhost:1313. Pages refresh as you save.

## Publish

Commit and push to the `main` branch on GitHub:

    git add -A
    git commit -m "Describe the change"
    git push

GitHub Actions (`.github/workflows/hugo.yml`) rebuilds the site and publishes it to
GitHub Pages within a minute or two. Progress is on the repository's **Actions** tab.

You can also edit a page directly on github.com (open the file, click the pencil icon,
then "Commit changes") – it publishes the same way.

## Other files (rarely needed)

- `hugo.toml` – site title, menu, colours, theme options
- `assets/css/custom.css` – a few small style tweaks
- `layouts/shortcodes/img.html` – the `img` shortcode
- `themes/blowfish` – the theme (git submodule). Update with
  `git submodule update --remote`, but check the site still builds afterwards.

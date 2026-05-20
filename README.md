# Academic Homepage Template

A clean, bilingual, Markdown-driven academic homepage template for GitHub Pages.

This template is designed for students, researchers, labs, and academic developers who want a lightweight personal homepage that is easy to edit and easy to publish. The page is pure static HTML/CSS/JavaScript, so there is no build step and no framework lock-in.

Markdown is rendered in the browser with Marked.js from CDN. A lightweight built-in fallback supports common Markdown syntax if the CDN is unavailable.

## Features

- Markdown-first content editing
- Bilingual section titles
- Fixed profile sidebar
- Responsive desktop/mobile layout
- Built-in section types for timeline, research cards, publications, projects, honors, and contact
- No build step required
- GitHub Pages friendly
- MIT licensed

## Repository Structure

```text
.
├── content
│   ├── about.md
│   ├── config.json
│   ├── contact.md
│   ├── honors.md
│   ├── news.md
│   ├── projects.md
│   ├── publications.md
│   └── research.md
├── static
│   ├── assets
│   │   ├── favicon.ico
│   │   └── img
│   │       └── avatar.svg
│   ├── css
│   │   └── main.css
│   └── js
│       └── main.js
├── index.html
├── LICENSE
└── README.md
```

## Quick Start: Fork This Template

### 1. Fork the repository

Click **Fork** on GitHub to create your own copy of this repository.

### 2. Rename the repository

For a personal GitHub Pages site, rename your fork to:

```text
<your-github-username>.github.io
```

For example, if your GitHub username is `alice`, the repository should be:

```text
alice.github.io
```

This gives you the homepage URL:

```text
https://alice.github.io/
```

If you keep another repository name, GitHub Pages will publish it as a project site instead:

```text
https://<your-github-username>.github.io/<repository-name>/
```

### 3. Edit your profile configuration

Open:

```text
content/config.json
```

Update these fields:

```json
{
  "site": {
    "title": "Your Name | Academic Homepage",
    "description": "Your academic homepage",
    "author": "Your Name"
  },
  "profile": {
    "avatar": "static/assets/img/avatar.svg",
    "name": "Your Name",
    "nameLocal": "你的姓名",
    "role": "Your Academic Role",
    "affiliation": [
      "Department or School",
      "University or Organization"
    ]
  }
}
```

You can also reorder, rename, add, or remove sections in the `sections` array.

### 4. Edit Markdown content

Edit the Markdown files in `content/`:

```text
content/about.md          homepage introduction
content/news.md           timeline entries
content/research.md       research cards
content/publications.md   publication list
content/projects.md       project cards
content/honors.md         honors and achievements
content/contact.md        contact information
```

For card-like sections such as research, publications, and projects, each `### Heading` starts a new card.

Example:

```md
### Multimodal Learning

Describe your research direction here.

### Embodied AI

Describe another research direction here.
```

For timeline sections, use:

```md
- **2026.05** | **[Publication]** One paper was accepted by Conference 2026.
- **2025.09** | **[Education]** Joined University as a Ph.D. student.
```

### 5. Replace the avatar

Replace:

```text
static/assets/img/avatar.svg
```

with your own avatar image. You may use `.png`, `.jpg`, `.jpeg`, `.webp`, or `.svg`.

If you change the filename, also update `profile.avatar` in `content/config.json`.

### 6. Enable GitHub Pages

In your forked repository:

1. Go to **Settings**
2. Click **Pages**
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`
4. Select branch `main`
5. Select folder `/ (root)`
6. Click **Save**

GitHub Pages usually deploys within a few minutes.

## Local Preview

Because the site loads Markdown with `fetch()`, preview it through a local server instead of opening `index.html` directly.

Run:

```bash
python -m http.server 8000 --bind 127.0.0.1
```

Then open:

```text
http://127.0.0.1:8000/
```

## Section Types

The `type` field in `content/config.json` controls how each Markdown file is rendered.

```text
hero          large intro section
timeline      dated news timeline
research      grid of research cards
publications  publication list
projects      vertical project cards
honors        honors list
contact       contact card
plain         plain Markdown card
```

## Remove or Add a Section

To remove a section, delete its entry from `content/config.json`.

To add a section:

1. Create a new Markdown file in `content/`
2. Add a matching entry to the `sections` array in `content/config.json`

Example:

```json
{
  "id": "teaching",
  "title": "Teaching",
  "subtitle": "教学",
  "file": "content/teaching.md",
  "type": "plain"
}
```

## Custom Design

Edit:

```text
static/css/main.css
```

You can change colors, spacing, typography, sidebar width, card style, and responsive behavior.

## License

This project is released under the MIT License.

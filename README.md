# Lukey Lab Website

A modern, responsive website for the Lukey Lab at Cold Spring Harbor Laboratory, built with Jekyll and hosted on GitHub Pages.

## Quick Start

### Local Development

1. **Install Ruby and Jekyll** (if not already installed):
   ```bash
   # macOS
   brew install ruby
   gem install jekyll bundler

   # Ubuntu/Debian
   sudo apt install ruby-full build-essential
   gem install jekyll bundler
   ```

2. **Install dependencies**:
   ```bash
   bundle install
   ```

3. **Run locally**:
   ```bash
   bundle exec jekyll serve
   ```

4. **View the site** at `http://localhost:4000`

### Deploying to GitHub Pages

Simply push your changes to the `main` branch. GitHub Pages will automatically build and deploy the site.

---

## Maintaining the Website

This website is designed to be easy to maintain without programming knowledge. Most content is stored in simple YAML and Markdown files.

### Updating Content

#### Team Members (`_data/team.yml`)

To add a new team member:

1. Open `_data/team.yml`
2. Add a new entry following this format:

```yaml
- name: "Jane Smith"
  role: "Postdoctoral Fellow"
  category: "postdoc"  # Options: pi, postdoc, graduate, undergraduate, staff, alumni
  photo: "/assets/images/team/jane-smith.jpg"
  bio: "Brief biography here"
  email: "jsmith@cshl.edu"
  twitter: "janesmith"  # Optional, without @
  google_scholar: "https://scholar.google.com/..."  # Optional
```

3. Add the photo to `assets/images/team/`
4. Commit and push changes

#### Publications (`_data/publications.yml`)

To add a new publication:

1. Open `_data/publications.yml`
2. Add a new entry at the top:

```yaml
- title: "Full Paper Title Here"
  authors: "Author A, Author B, **Lukey MJ**"  # Use ** to highlight lab members
  journal: "Journal Name"
  year: 2024
  volume: "12"
  pages: "123-456"
  doi: "10.1234/example.doi"
  pmid: "12345678"
  highlight: true  # Set to true for featured publications
```

#### News Items (`_data/news.yml`)

To add news:

1. Open `_data/news.yml`
2. Add a new entry:

```yaml
- date: 2024-06-15
  title: "News Headline"
  excerpt: "Brief description of the news"
  link: "https://example.com/article"  # Optional
  external: true  # Set to true if link goes to external site
```

### Adding/Editing Pages

Each main page is a Markdown file in the root directory:

| File | Page |
|------|------|
| `index.html` | Home page |
| `research.md` | Research page |
| `team.md` | Team page |
| `publications.md` | Publications page |
| `join.md` | Join Us page |
| `contact.md` | Contact page |

To edit content, simply modify the Markdown text below the `---` front matter section.

### Images

- **Team photos**: Add to `assets/images/team/` (recommended size: 400x400 pixels, square format)
- **Research images**: Add to `assets/images/research/`
- **General images**: Add to `assets/images/`

Supported formats: JPG, PNG, WebP

---

## Site Configuration

Main settings are in `_config.yml`:

### Principal Investigator Information
```yaml
pi:
  name: "Michael Lukey"
  title: "Associate Professor"
  email: "lukey@cshl.edu"
  phone: "516-367-5016"
  photo: "/assets/images/lukey_profile.jpg"
```

### Institution Information
```yaml
institution:
  name: "Cold Spring Harbor Laboratory"
  department: "Cancer Center"
  address: "1 Bungtown Road, Cold Spring Harbor, NY 11724"
```

### Social Media Links
```yaml
social:
  twitter: ""
  github: "lukey-lab"
  google_scholar: ""
  orcid: ""
```

### Navigation Menu
```yaml
nav:
  - title: "Home"
    url: "/"
  - title: "Research"
    url: "/research/"
  # Add more menu items as needed
```

---

## File Structure

```
lukey-lab.github.io/
├── _config.yml          # Site configuration
├── _data/
│   ├── team.yml         # Team members
│   ├── publications.yml # Publications list
│   └── news.yml         # News items
├── _layouts/
│   ├── default.html     # Base layout
│   ├── page.html        # Standard page
│   ├── home.html        # Home page
│   └── ...              # Other layouts
├── assets/
│   ├── css/
│   │   └── main.css     # Stylesheet
│   └── images/
│       └── team/        # Team photos
├── index.html           # Home page
├── research.md          # Research page
├── team.md              # Team page
├── publications.md      # Publications page
├── join.md              # Join Us page
├── contact.md           # Contact page
└── README.md            # This file
```

---

## Customization

### Colors

Edit CSS variables in `assets/css/main.css`:

```css
:root {
  --color-primary: #1a365d;      /* Main brand color */
  --color-accent: #3182ce;       /* Accent/link color */
  /* ... more colors */
}
```

### Fonts

Fonts are loaded from Google Fonts. To change, edit the `<link>` tag in `_layouts/default.html` and update the CSS variables.

---

## Troubleshooting

### Site not updating after push
- Wait 1-2 minutes for GitHub Pages to rebuild
- Check the Actions tab in your GitHub repository for build errors
- Clear your browser cache

### Images not showing
- Ensure paths start with `/assets/images/`
- Check file names match exactly (case-sensitive)
- Verify files are committed to the repository

### Local development issues
- Run `bundle update` to update dependencies
- Delete `_site` folder and rebuild

---

## Support

For technical issues with the website template, please open an issue in the GitHub repository.

For questions about lab operations, contact: [lukey@cshl.edu](mailto:lukey@cshl.edu)

---

## License

This website template is open source. Content copyright Lukey Lab, Cold Spring Harbor Laboratory.

# Marco Fraccaro's Personal Website

This repository contains the source code for Marco Fraccaro's personal website, hosted at [marcofraccaro.github.io](https://marcofraccaro.github.io/).

## Technologies Used

The website is built using:

- **Jekyll**: A static site generator that transforms Markdown and other formats into a complete website.
- **Sass**: A CSS preprocessor used for styling, with files located in the `_sass/` directory.
- **GitHub Pages**: For hosting the website directly from this GitHub repository.

Additional Jekyll plugins include:
- `jekyll-feed`: Generates an Atom feed for the site.
- `jekyll-paginate`: Adds pagination support for posts.

## Local Development

To run the website locally for development:

1. Ensure you have Ruby installed (version 2.5.0 or higher recommended).
2. Install Jekyll and Bundler:
   ```
   gem install jekyll bundler
   ```
3. Clone this repository and navigate to the directory.
4. Install dependencies (if a Gemfile is present):
   ```
   bundle install
   ```
5. Serve the site locally:
   ```
   bundle exec jekyll serve
   ```
   Or if no Gemfile:
   ```
   jekyll serve
   ```
6. Open your browser to `http://localhost:4000` to view the site.

## Hosting

The website is automatically hosted on GitHub Pages. Any changes pushed to the `main` branch (or `master` if configured) will trigger a rebuild and deployment of the site.
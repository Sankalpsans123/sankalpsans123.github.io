# sankalp.github.io
Personal website

This site is configured to use **Ruby 4.0.0** with Jekyll and GitHub Pages.

## Ruby Version

This project uses Ruby 4.0.0 as specified in `.ruby-version`. The site is built and deployed using GitHub Actions, which allows us to use Ruby 4.0.0 even though GitHub Pages' built-in Jekyll build system doesn't support it yet.

## Local Development

#### Install Jekyll

Jekyll is a [Ruby Gem](https://jekyllrb.com/docs/ruby-101/#gems) that can be installed on most systems.

1. Install Ruby 4.0.0 using a version manager like [rbenv](https://github.com/rbenv/rbenv) or [rvm](https://rvm.io/):
   ```bash
   # Using rbenv
   rbenv install 4.0.0
   rbenv local 4.0.0
   
   # Or using rvm
   rvm install 4.0.0
   rvm use 4.0.0
   ```

2. Install Jekyll and [bundler](https://jekyllrb.com/docs/ruby-101/#bundler) [gems](https://jekyllrb.com/docs/ruby-101/#gems)
   ```
   gem install jekyll bundler
   ```

3. Change into your new directory
   ```
   cd sankalpsans123.github.io
   ```

4. Install missing gems
   ```
   bundle install
   ```

5. Build the site and make it available on a local server
   ```
   bundle exec jekyll serve
   ```

You should see something like:

```
Configuration file: /octocat/personal-website/_config.yml
            Source: /octocat/personal-website
       Destination: /octocat/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
   GitHub Metadata: No GitHub API authentication could be found. Some fields may be missing or have incorrect data.
                    done in 14.729 seconds.
 Auto-regeneration: enabled for '/octocat/personal-website'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
```

Don't worry about the "No GitHub API authentication could be found" message. [API authentication is only necessary](https://github.com/jekyll/github-metadata/blob/master/docs/authentication.md) if you intend to display more detailed metadata, like a branch name.

6. Now browse to [http://localhost:4000](http://localhost:4000)

## GitHub Pages Deployment

This site uses GitHub Actions to build and deploy with Ruby 4.0.0. The workflow is configured in `.github/workflows/deploy.yml`.

### Setup Instructions

1. Enable GitHub Pages in your repository settings:
   - Go to Settings → Pages
   - Under "Source", select "GitHub Actions"

2. The site will automatically build and deploy when you push to the `main` or `master` branch.

3. The workflow uses Ruby 4.0.0 to build your Jekyll site and deploy it to GitHub Pages.

### Manual Deployment

You can also manually trigger the deployment workflow:
- Go to the "Actions" tab in your GitHub repository
- Select "Build and Deploy Jekyll Site"
- Click "Run workflow"

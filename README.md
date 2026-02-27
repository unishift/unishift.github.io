# Eugene Lyapustin's Personal Page

This is a personal page about me. It is based on the [academicpages](https://github.com/academicpages/academicpages.github.io) template.

## Building and Running Locally

To build and run this Jekyll site locally, you'll need Ruby and Bundler installed.

### Prerequisites

1. **Ruby**: Version 3.0 or higher is recommended.
   - **macOS Users**: Do not use the default system Ruby (it is outdated and may cause permission errors). Install Ruby via [Homebrew](https://brew.sh/):
     ```bash
     brew install ruby
     ```
     Make sure the Homebrew Ruby is in your `$PATH` (follow the instructions brew prints after installation).

2. **Bundler**: Install the Bundler gem:
   ```bash
   gem install bundler
   ```

### Setup

Install the required Ruby dependencies for the project:

```bash
bundle install
```

### Running the Local Server

Start the Jekyll development server:

```bash
bundle exec jekyll serve
```

The site will be available at `http://127.0.0.1:4000/`. The server will automatically regenerate files when you make changes.

### Troubleshooting on macOS

If you get an error like `Could not find 'bundler'`, it means your terminal is still using the old macOS system Ruby (usually v2.6).

1. Ensure your shell profile (e.g., `~/.zshrc`) includes the Homebrew Ruby path.
2. Alternatively, you can run Bundler directly from the Homebrew path if you know which version you installed. For example, if you have Ruby 3.3 installed:
   ```bash
   /opt/homebrew/lib/ruby/gems/3.3.0/bin/bundle exec jekyll serve
   ```

# Local preview of the site with the same gems as GitHub Pages.
# Used both by devcontainer.json and compose.yaml.
FROM ruby:3.3-bookworm

# Lets jekyll-github-metadata find the repo without asking git, and see it as
# an organisation site (*.github.io) like on GitHub, not as a project page.
ENV PAGES_REPO_NWO=skemake/SkeMake.github.io \
    PAGES_PAGES_HOSTNAME=github.io
# The mounted repo is owned by another uid than the container user.
RUN git config --system --add safe.directory /srv/jekyll

WORKDIR /srv/jekyll

COPY Gemfile Gemfile.lock ./
RUN bundle install

COPY .devcontainer/serve-site /usr/local/bin/serve-site

# Non-root user for the dev container, so edited files keep your ownership.
RUN useradd --create-home --uid 1000 --shell /bin/bash jekyll

EXPOSE 4000 35729
CMD ["serve-site"]

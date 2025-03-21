# Contributing to documentation

## Documenting the next release

When you're contributing documentation changes for code in `main` branch, then documentation in `releases-source/` is where you should make changes. Changes made here will automatically be included in the next release.

## Improving documentation for existing releases

If you're contributing documentation for an existing release, then your documentation changes should go into the documentation for that release in `_releases/` folder, and possibly several of the following releases also.

### Where are all the _releases_?

All the files that used to be under `_releases` in the `main` can be found in the `releases` branch. The `main` branch now only keeps the latest version. That means, to fix the docs of published releases you need to checkout the _relases branch_ and supply a PR against that.

## Running the documentation site locally

For casual improvements to the documentation, this shouldn't really be necessary, as all the content documents are plain markdown files.

However, if you're going to contribute changes that alter the overall structure or design of the site, then this section is for you.

```shell
# navigate to docs/
cd docs

# ensure you have bundler

# install all dependencies

# build, serve and live-reload the site
npm run serve-docs
```

After that you can access the site at http://localhost:4000/

Unfortunately, you will not see the full `release-source`, as the site is excluded from
Jekyll, but we made a little hack to expose the currently worked-on version.
You can check out the currently worked on release docs under [`/releases/dev/release`](http://localhost:4000/releases/dev/release).

## Linting of Markdown

To help keep the documentation syntactically consistent and free of syntax violations, a pre-commit hook using [markdownlint](https://github.com/DavidAnson/markdownlint) verifies Markdown documents.

The CI server uses [markdownlint](https://github.com/DavidAnson/markdownlint) with the same configuration to verify the pull request.

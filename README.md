# Amethyst

[![Build Status](https://travis-ci.org/psastras/amethyst.svg?branch=master)](https://travis-ci.org/psastras/amethyst)

A minimal, responsive blog post skeleton site based on
[Cobalt](https://github.com/cobalt-org/cobalt.rs). All static pages, no
Javascript, and minimal CSS from the small
[Pure.css](https://github.com/yahoo/pure/) library (<30 KB total, <10 KB
gzipped).

## Demo

https://psastras.github.io/amethyst/

## Usage

### Dependencies

You must first install [Cobalt](https://github.com/cobalt-org/cobalt.rs). Make
sure that `cobalt` is on your `PATH`. Assuming you have Rust and `cargo`
installed, just run:

```
cargo install cobalt-bin
```

To create your own site, clone this repo, then:

```
npm install
npm run watch
```

This should serve the site on `localhost:8080`. You can add posts in the
`src/posts` directory. Root pages can be added by creating markdown files in the
`src` directory (see `src/about.md` for an example). To add a link to a page
in the navigation bar, add an item to the `site_links` entry in
`src/_data/meta.yml`.

All changes should automatically reload in your broweser on change (note that
for this to work you must have Javascript enabled - however the final built
files do not require Javascript).

To create the static files, run:

```
npm run build
```

The output files should be written to the `dist` folder.

## Usage with Github Pages

This is intended for use with Github pages (although static files can be
deployed on your host of choice). See the `.travis.yml` configuration file. You
will need to edit the last line of the `build_script` entry:

```
 - >-
    echo "base_path: \"/amethyst\"" > ./src/_data/meta.yml
```

Replace `amethyst` with your Github repo pathname (ie.
`foo.github.io/<pathname>`) - if this is a Github Org page, the basepath should
be empty.

In order to publish the built files, you must provide the environment variable
`GITHUB_TOKEN` in the Travis build,
[see here](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/)
for more information on creating a personal token.

# License

Licensed under the MIT License, see the LICENSE file for more information.

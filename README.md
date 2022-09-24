# Optimizing Your Learning

- See info about Kibo's BSc. Computer Science: https://kibo.school/degree/

## What's here?

```
$ tree .
.
├── README.md
├── book.toml
├── theme/
└── src
    ├── SUMMARY.md
    └── [various chapters].md

```

### README.md

You're lookin at it.

### book.toml

Config file for the course. Authors, title, other mdbook settings.

https://rust-lang.github.io/mdBook/format/configuration/index.html

### theme/

Any overrides of the default mdbook theme. Right now, just some custom CSS on
top of the standard mdbook CSS.

https://rust-lang.github.io/mdBook/format/theme/index.html

### src

Holds all the course files.

The static site output will be built to `output`, but that's git ignored.

### src/SUMMARY.md

This gets turned into the sidebar on the site. 

It's the text that should show, plus links to other md files in `src/`.

https://rust-lang.github.io/mdBook/format/summary.html

Files that are linked here will be built to the static site; ones that are not
will not be.

### src/*

These are the pages that actually make up the course. It's nice to put things in folders to organize the different pages. Each week can get a 'cover page' and a page per lesson, in a folder with that name, like

```
managing-your-learning-context.md
managing-your-learning-context/
    food-and-movement.md
    learning-with-others.md
    managing-stress-breathing-and-mindfulness.md
    motivation.md
    physical-environment.md
    sleep.md
```

etc.

### output

To generate the static site, run:

```
mdbook build
```

Output lives here, in `output`.
You can usually ignore these files; git will.

## Getting Started

Install mdbook: https://rust-lang.github.io/mdBook/guide/installation.html

if you use rust:

```
cargo install mdbook
```

Or use your package manager: `brew install mdbook`, or download a release from Github.

### Run the book locally

```
mdbook serve --open
```

## Deployment

We use `vercel` to handle deploys. It takes some setup to connect a repo to
vercel, assign a production domain, and set up auto-deploys.

* If you pushed to `main`, it will deploy to the live site. Watch out!
* Github actions will run `mdbook build` on pushed changes

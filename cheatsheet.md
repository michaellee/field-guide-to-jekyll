# Commands

## Generating a new Jekyll project

### Generate a new Jekyll project

`jekyll new project_name`

### Generate a new Jekyll project in an existing folder

`jekyll new . --force`

### Generate a new Jekyll project without a gem-based theme

`jekyll new project_name --blank`

## Build Jekyll project

`jekyll build`

This will build your project into a folder called `_site` in your Jekyll project's directory.

### Build a Jekyll project in a folder different than `_site`

`jekyll build --destination output_folder_name`

### Build with environment set

`JEKYLL_ENV=production jekyll build`

Accepts either `production` or `development`

## Serve Jekyll project

`jekyll serve`

This serves up a server hosted at http://localhost:4000/. It also auto-regenerates so that when changes are made in the Jekyll project, it rebuilds itself.

### Serve without auto-regeneration

`jekyll serve --no-watch`

### Serve with environment set

`JEKYLL_ENV=development jekyll serve`

Accepts either `development` or `production`

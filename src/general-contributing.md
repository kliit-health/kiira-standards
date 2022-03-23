# Contributing

## Installation

The official [Docker image](https://hub.docker.com/r/squidfunk/mkdocs-material/) is a great way to get up and running in a few minutes, as it comes with all dependencies pre-installed. Pull the image for the latest version with:

```
docker pull squidfunk/mkdocs-material
```

## Usage

MkDocs includes a live preview server, so you can preview your changes as you write your documentation. The server will automatically rebuild the site upon saving. Start it with:

```
docker run --rm -it -p 8000:8000 -v ${PWD}:/docs squidfunk/mkdocs-material
```
<!--
- `mkdocs new [dir-name]` - Create a new project.
- `mkdocs serve` - Start the live-reloading docs server.
- `mkdocs build` - Build the documentation site.
- `mkdocs -h` - Print help message and exit.
-->

## Directory Structure

```
> kiira-standards
    > src
        - index.md  # documentation homepage
        - [...].*   # other markdown pages, images, and other files
    - mkdocs.yml    # the configuration file
```
# Kometa collection files
Repo to hold collection based configuration for Kometa. The actual Kometa config file is kept in a private git repo that references this repo.

Feel free to fork this repo and modify the settings to your own desires.

<a href="https://kometa.wiki" target="_blank">kometa.wiki</a>

# Directory Structure
```
kometa_files/
├── movies/
│   ├── collections/
│   │   ├── lists.yml
│   │   ├── manual.yml
│   │   └── smart.yml
│   ├── metadata/
│   │   ├── mediux_movie.yml
│   │   └── movie_edits.yml
│   ├── overlays/
│   │   └── movies.yml
│   └── templates/
│       └── movie_collections
└── tv_shows/
    ├── collections/
    │   ├── lists.yml
    │   ├── manual.yml
    │   └── smart.yml
    ├── metadata/
    │   └── mediux_shows.yml
    ├── overlays/
    │   └── tv_shows.yml
    └── templates/
        └── tv_collections
```

# Usage

Kometa config file requires the following settings to be configured for remote github usage:

## Global settings

While you can use this repo directly, I'm not sure how much usage you can get out of a random person's config for their personal server

```
settings:
    custom_repo: https://github.com/bucketsadmin/kometa_files/tree/main
```

## Per library settings

```
libraries:
  Movies:
    collection_files:
    - repo: movies/collections/lists
    - repo: movies/collections/manual
    - repo: movies/collections/smart
    overlay_files:
      - repo: movies/overlays/movies
    metadata_files:
    - repo: movies/metadata/mediux_movie
    - repo: movies/metadata/movie_edits

  TV Shows:
    collection_files:
    - repo: tv_shows/collections/lists
    - repo: tv_shows/collections/manual
    - repo: tv_shows/collections/smart
    overlay_files:
      - repo: tv_shows/overlays/tv_shows
    metadata_files:
      - repo: tv_shows/metadata/mediux_shows
```

## config file authorization

It is recommended to use environment variables in configuration, placing the token in plain text is not a good security practice
When running a docker container, env variables can be passed to the config via docker runtime environment variables

<a href="https://kometa.wiki/en/latest/kometa/environmental/#docker-environment_30" target="_blank">Kometa: Run Commands & Environment Variables</a>

```
########## Optional Connections ##########
github:
  token: <<git_token>>
```

More information on configuring Github can be found here:
<a href="https://kometa.wiki/en/latest/config/github/" target="_blank">Kometa Wiki: github</a>

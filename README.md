# Docker Infrastructure

### Getting started
```sh
bundle install    # Install gems
rake clean_start  # See Rakefile for info
```

### About
- `rake clean_start` task ensures that all services are properly setup, running any first time configurations on the docker containers.
- `rake start` You should always **ALWAYS USE**  unless you modify the `DOCKERFILE` or any of the underlying infrastructure

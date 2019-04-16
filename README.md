# Useful base images for our projects

[![CircleCI](https://circleci.com/gh/mtgroupit/baseimage.svg?style=svg)](https://circleci.com/gh/mtgroupit/baseimage)

## Keeping images up-to-date (for security reasons)

To speed up builds and keep images up-to-date on each build (which can be triggered
manually from CircleCI UI) corresponding `update` script will be executed to detect
pending updates (if any) and provide `--build-arg` to ensure these updates will be
installed.

To ensure they're always up-to-date it may worth to trigger build of CircleCI from
cron every 24 hours using CircleCI API.

### Implementation details

- `ARG UPGRADE` in `Dockerfile.*` must be located above all other `ARG UPGRADE_*`, if any.

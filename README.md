# glab-groups-chromium

Thin GitHub Actions wrapper for the Chromium Gitiles root mirror.

## Scope

- Loads `gh-actions-cfg/glab-groups-chromium`
- Calls the reusable workflow in `glab-groups-shared@mcr/main`
- Uses the BWS target PAT secret `GL_PAT_GROUP_CHROMIUM_SVC`
- Mirrors the current public `chromium.googlesource.com` repositories into
  `chromium/*` beneath `glab-forks`
- Preserves nested source repository paths such as `chromium/...` under the
  target namespace
- Runs deterministic mirror batch shards with five jobs max in parallel
- Schedules at minute 5 of hours 9 and 21 UTC
- Publishes discovery, plan, report, CSV, JSON, and Parquet artifacts for each run

## Validation

```sh
python3 -m unittest discover -s tests
```

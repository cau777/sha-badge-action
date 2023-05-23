# SHA Badge Action

This repo contains a simple GitHub Actions workflow that computes the short hash for a given branch and generates a badge with it.
This is useful to quickly check what branch is currently deployed. To make it more realistic, the repo has 3 branches
(master, canary and production) with some sample data to make the hashes different.
Credit on **schneegans/dynamic-badges-action** for most of the logic.

# Option 1: Storing the hashes

![master SHA](https://img.shields.io/endpoint?url=https://gist.githubusercontent.com/cau777/63a20a64c3d5ea1ef487b04c75629f29/raw/master-sha.json)
![canary SHA](https://img.shields.io/endpoint?url=https://gist.githubusercontent.com/cau777/63a20a64c3d5ea1ef487b04c75629f29/raw/canary-sha.json)
![production SHA](https://img.shields.io/endpoint?url=https://gist.githubusercontent.com/cau777/63a20a64c3d5ea1ef487b04c75629f29/raw/production-sha.json)

#### Hosting the hashes

Once computed, the hashes are hosted in [this public gist](https://gist.github.com/cau777/63a20a64c3d5ea1ef487b04c75629f29).
This is necessary because if we tried hosting in the same repo, the badge would not work for private repos (and we
probably don't want to distribute access tokens everywhere).

#### Usage

To include this in your repo:
1) Generate a personal access token with access to gists under profile/developer settings
2) Create an action secret in your repo called `GIST_SECRET` with that token
3) Copy the workflow

# reusable-workflows
This repository holds a list of shared workflows that are being used in other MapLibre repositories

## create-bump-version-pr.yml

This action is used to update package.json files with the relevant version (it receives a list of folders to run `npm version` in.
It is also used to add missing PRs to the changelog by looking at the git history, finding PR links, compare them to the existing changelog and add the missing ones.
It opens a PR with the relevant code changes to allow review, edit and merge.
Once merged, it relays on the following action to do the release.

## npm-publish.yml

This action is responsoble for both npm publishing and also publishing the docs to github pages for every release.
It start by checking if the version of the root package.json to see if it had changed.
If so, it starts by:
1. Installing and building the package.
2. Publishing it to npm.
3. Creating a git tag.
4. Creating a GitHub release.
5. Building the docs.
6. Publishing the docs to GitHub pages.

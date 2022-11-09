# .github

Repository for community health files for the @Energyhub organization

## Developing

In order to develop these workflows and actions before pushing to `main`, create a branch with
your changes and push to GitHub. Then in a repository that uses these workflows and actions (like
the [java-microservice-template](https://github.com/energyhub/java-microservice-template)), change
the reference to the action or workflow from a published GitHub release, to the name of your feature
branch and push that branch to GitHub as well.

## Deploying

When you would like a new version of any workflow or action to be available, create a tag and
release from `main` and update the reference in your repository.

For example,
```shell
# one-time install
brew install gh

# run this whenever you want to release
export $DOT_GITHUB_VERSION=v0.1.0 # change me to the next version
git checkout main
git pull
git tag -a "${$DOT_GITHUB_VERSION}" -m "Add fun new action"
git push origin 2.3.0
gh release create "${$DOT_GITHUB_VERSION}" -t "${$DOT_GITHUB_VERSION}" --generate-notes -R energyhub/.github
```

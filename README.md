# get-pr-commits

A GitHub Action that get commits in current pull-request

## Usage
Add .github/workflows/sanity-check.yml with the following:

```
name: Sanity check
on: [pull_request]

jobs:
  commits_check_job:
    runs-on: ubuntu-latest
    name: Commits Check
    steps:
    - name: Get PR Commits
      id: 'get-pr-commits'
      uses: tim-actions/get-pr-commits@master
      with:
        token: ${{ secrets.GITHUB_TOKEN }}

```
\n## Stale PRs

Stale pull requests (PRs) are those that have not had any activity for a certain period of time. It's important to manage stale PRs to keep the project's pull requests manageable and to ensure that contributions are either moving forward or being closed if they are no longer relevant.

Stale PRs are managed by using the [Stale](https://github.com/actions/stale):
- PRs with no activity for 30 days are marked as stale
- stale PRs for 10 days are closed

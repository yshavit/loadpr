Stages the diff of a pull request locally
=========================================

GitHub's ability to view pull requests online is great, but there are times I want the same diff locally (so that I can view it in my IDE). This script does just that.

To run:

1. create a file `~/.github-token` that contains a [GitHub security token][1] (and nothing else).
2. execute this script from within your local git repo, passing along the pull request id:

       loadpr 123

The script will check out the PR's base commit (the branch you're merging into), then `merge --no-ff --no-commit` the PR's head commit (your feature branch), and finally do a `git reset` to unstage the changes (but keep them on your disk).

Requires bash and python.

[1]: https://github.com/settings/applications

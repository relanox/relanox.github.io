# Relanox documentation

[relanox.github.io](https://relanox.github.io/) hosts the documentation built from
[relanox/relanox](https://github.com/relanox/relanox/tree/master/docs).

The source repository sends a `documentation` repository dispatch when its
documentation changes on `master`. This repository then checks out the latest
source commit, builds with its pinned Go version and `go run ./tools/docs`, and
deploys to GitHub Pages. The workflow can also be dispatched manually. There is
no scheduled polling.

The source repository's `DOCS_DISPATCH_TOKEN` Actions secret must authorize
repository dispatch to this repository. A fine-grained token needs access only
to `relanox/relanox.github.io`, with Contents read/write permission.
The deployed `source-commit.txt` identifies the exact published source revision.

The source repository maintains redirects for old `/relanox/` URLs.

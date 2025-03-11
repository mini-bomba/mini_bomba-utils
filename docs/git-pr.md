# [git pr](/bin/git-pr)
## a custom git subcommand for checking out and merging github PRs

### Requirements

* bash
* git
* head

### Installation

Install the requirements, if not already met.

Clone the repo & add it to the PATH, or download the file, put it in a directory on the PATH (such as `/usr/local/bin`, or `~/.local/bin`) and mark it executable.

### Usage
```bash
git pr [merge] <PR ID> [remote repo name]

# examples
git pr 21              # checkout PR #21 from the default remote repo
git pr 37 github       # checkout pr #37 from a remote called "github"
git pr merge 21        # merge PR #21 from the default remote repo into the current branch
git pr merge 37 github # merge pr #37 from a remote called "github" into the current branch
```

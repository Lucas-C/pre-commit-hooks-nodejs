Useful [pre-commit](http://pre-commit.com) hooks based on NodeJS scripts.

Does not require to have NodeJS installed: `pre-commit` will be fetch and install it under the hood.

The test `Dockerfile` in this repo was taken from [here](https://github.com/docker-library/redis/blob/master/3.2/Dockerfile).

## Table of contents

<!-- toc -->

- [Usage](#usage)
    + [markdown-toc](#markdown-toc)

<!-- tocstop -->

## Usage

```
-   repo: https://github.com/Lucas-C/pre-commit-hooks-nodejs
    sha: v1.0.1
    hooks:
    -   id: dockerfile_lint
    -   id: markdown-toc
```

#### markdown-toc

By default, a table of content will be inserted in your repo root `README.md`,
injecting the TOC on lines with: "<&#33;-- toc -->"

When the TOC is added or updated, the hook will fail with `Files were modified by this hook`.
You then just have to `git add` your `README.md` and commit again (or `git commit -a`).

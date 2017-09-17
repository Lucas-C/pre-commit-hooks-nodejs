Useful [pre-commit](http://pre-commit.com) hooks based on NodeJS scripts.

Does not require to have NodeJS installed: `pre-commit` will fetch & install it under the hood.

The test `Dockerfile` in this repo was taken from [here](https://github.com/docker-library/redis/blob/master/3.2/Dockerfile).

## Table of contents

<!-- toc -->

- [Usage](#usage)
    + [htmlhint](#htmlhint)
    + [htmllint](#htmllint)
    + [markdown-toc](#markdown-toc)

<!-- tocstop -->

## Usage

```
-   repo: https://github.com/Lucas-C/pre-commit-hooks-nodejs
    sha: v1.1.0
    hooks:
    -   id: dockerfile_lint
    -   id: markdown-toc
    -   id: htmlhint
        # optional custom config:
        args: [--config, .htmlhintrc]
    -   id: htmllint
```

#### htmlhint

Regex-based linter: https://github.com/yaniswang/HTMLHint

#### htmllint

Uses [htmlparser2](https://github.com/fb55/htmlparser2)-based linter: [htmllint](https://github.com/htmllint/htmllint/wiki/Options).

Requires you to have a config file like [this default `.htmllintrc`](https://github.com/htmllint/htmllint-cli/blob/master/lib/default_cfg.json)).

#### markdown-toc

By default, a table of content will be inserted in your repo root `README.md`,
injecting the TOC on lines with: "<&#33;-- toc -->"

When the TOC is added or updated, the hook will fail with `Files were modified by this hook`.
You then just have to `git add` your `README.md` and commit again (or `git commit -a`).

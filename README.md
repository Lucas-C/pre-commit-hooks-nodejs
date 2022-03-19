[![Build Status](https://travis-ci.org/Lucas-C/pre-commit-hooks-nodejs.svg?branch=master)](https://travis-ci.org/Lucas-C/pre-commit-hooks-nodejs)
[![Known Vulnerabilities](https://snyk.io/test/github/lucas-c/pre-commit-hooks-nodejs/badge.svg)](https://snyk.io/test/github/lucas-c/pre-commit-hooks-nodejs)

Useful [pre-commit](http://pre-commit.com) hooks based on NodeJS scripts.

Does not require to have NodeJS installed: `pre-commit` will fetch & install it under the hood.

The test `Dockerfile` in this repo was taken from [here](https://github.com/docker-library/redis/blob/master/3.2/Dockerfile).

## Table of contents

<!-- toc -->

- [Usage](#usage)
    * [htmlhint](#htmlhint)
    * [htmllint](#htmllint)
    * [markdown-toc](#markdown-toc)
    * [dockerfile_lint](#dockerfile_lint)

<!-- tocstop -->

## Usage

```
repos:
-   repo: https://github.com/Lucas-C/pre-commit-hooks-nodejs
    rev: v1.1.2
    hooks:
    -   id: htmlhint
        # optional custom config:
        args: [--config, .htmlhintrc]
    -   id: htmllint
    -   id: markdown-toc
        # optional custom config:
        args: [--indent, "    ", -i]
    -   id: dockerfile_lint
        # optional custom config:
        args: [--json, --verbose, --dockerfile]
```

### htmlhint

Regex-based linter: https://github.com/yaniswang/HTMLHint

### htmllint

Uses [htmlparser2](https://github.com/fb55/htmlparser2)-based linter: [htmllint](https://github.com/htmllint/htmllint/wiki/Options).

Requires you to have a config file like [this default `.htmllintrc`](https://github.com/htmllint/htmllint-cli/blob/master/lib/default_cfg.json).

### markdown-toc

By default, a table of content will be inserted in your repo root `README.md`,
injecting the TOC on lines containing the HTML comment `<!-- toc -->`.

When the TOC is added or updated, the hook will fail with `Files were modified by this hook`.
You then just have to `git add` your `README.md` and commit again (or `git commit -a`).

### dockerfile_lint

Simply call the latest version of [dockerfile_lint](https://github.com/projectatomic/dockerfile_lint)

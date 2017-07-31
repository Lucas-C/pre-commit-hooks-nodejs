Useful [pre-commit](http://pre-commit.com) hooks based on NodeJS scripts.

Does not require to have NodeJS installed: `pre-commit` will be fetch and install it under the hood.

The test `Dockerfile` in this repo was taken from [here](https://github.com/docker-library/redis/blob/master/3.2/Dockerfile).

## Usage

```
-   repo: https://github.com/Lucas-C/pre-commit-hooks-nodejs
    sha: v1.0.0
    hooks:
    -   id: dockerfile_lint
```

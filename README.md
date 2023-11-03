[![Sourcery](https://img.shields.io/badge/Sourcery-enabled-brightgreen)](https://sourcery.ai)

## Sourcery
Instantly review and improve your Python code to keep your codebase maintainable. 

Get started with our CLI to have Sourcery review all your code locally or star this repo to have our GitHub bot review your most popular Python repo.

## CLI

You can have Sourcery review your entire project and make dozens or hundreds (or thousands) of improvements with a single command from the command line. 

To start `pip install sourcery`, login with `sourcery login`, and then run `sourcery review <some path>` to have Sourcery review and make suggestions on every file in that path.

## CI & Pre-Commit

Keep your entire codebase standardized with Sourcery’s [CI integration](https://docs.sourcery.ai/Guides/Getting-Started/CI/) and [pre-commit hook](https://docs.sourcery.ai/Guides/Getting-Started/Pre-Commit/). 

For CI we recommend using:

```yaml
pip install sourcery
# Store your Sourcery token as a secret in your CI environment.
sourcery login --token $SOURCERY_TOKEN
sourcery review --check --diff "git diff main" .
```

Or if it’s easier you can [check out our GitHub Action](https://github.com/marketplace/actions/sourcery-action)!

To set up your pre-commit hooks use:

```yaml
repos:
  - repo: https://github.com/sourcery-ai/sourcery
    rev: v1.13.0
    hooks:
      - id: sourcery
        # The best way to use Sourcery in a pre-commit hook:
        # * review only changed lines:
        # * omit the summary
        args: [--diff=git diff HEAD, --no-summary]
```

Note: Sourcery is fully free for open-source projects - but you need a [Team plan](https://docs.sourcery.ai/Product/Plans/) to use Sourcery in CI or as a pre-commit hook for private projects.

## IDE Integration

Sourcery integrates into your editor to review and improve your code while you’re writing it.

Find quick installation instructions here:

- [PyCharm](https://docs.sourcery.ai/Guides/Getting-Started/PyCharm/)
- [VS Code](https://docs.sourcery.ai/Guides/Getting-Started/VSCode/)
- [Sublime](https://docs.sourcery.ai/Guides/Getting-Started/Sublime/)
- [Vim](https://docs.sourcery.ai/Guides/Getting-Started/Vim/)

More editor integrations coming soon.

## GitHub Code Reviews

Ensure your code is always at the highest quality. Sourcery reviews and makes suggestions on your whole repo when you install and then checks all new pull requests in the future.

You can get set up and running in 1 minute. Just follow this [link](https://github.com/apps/sourcery-ai/installations/new) and select your repos.

Or to try it out right away, ⭐ this repo, and Sourcery will review your most popular Python repo and send you a pull request. As an added bonus **@sourcery-ai-bot** will ⭐ your repo too.

## Demo

![Sourcery demo](sourcery-demo.gif)

## **Links**

- [Docs](https://docs.sourcery.ai/)
- [Sourcery website](https://sourcery.ai/)
- [VS Code Plugin](https://marketplace.visualstudio.com/items?itemName=sourcery.sourcery&ssr=false#overview)
- [PyCharm Plugin](https://plugins.jetbrains.com/plugin/12631-sourcery)

## Badges
Let the world know your project is using Sourcery to refactor with this badge:

[![Sourcery](https://img.shields.io/badge/Sourcery-enabled-brightgreen)](https://sourcery.ai)

Copy the code below into your README to display your Sourcery badge:

    [![Sourcery](https://img.shields.io/badge/Sourcery-enabled-brightgreen)](https://sourcery.ai)

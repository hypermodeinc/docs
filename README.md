<!-- markdownlint-disable first-line-heading -->

[![GitHub commit activity](https://img.shields.io/github/commit-activity/m/hypermodeinc/docs)](https://github.com/hypermodeinc/docs/commits/main/)

# Docs

This repo contains all of the docs and supporting assets for
[Hypermode Docs](https://docs.hypermode.com). It includes (or soon will)
documentation for the open source projects that Hypermode leads:

- [Modus](https://github.com/hypermodeinc/modus) - serverless framework for
  building functions and APIs, powered by WebAssembly
- [Dgraph](https://github.com/dgraph-io/dgraph) - distributed, transactional
  graph database for real-time use cases
- [Badger](https://github.com/dgraph-io/badger) - embeddable key-value store in
  Go
- [Ristretto](https://github.com/dgraph-io/ristretto) - embeddable memory-bound
  cache in Go

## Suggesting a Change

If you notice something in our documentation that is wrong, misleading, or could
use additional context, the easiest way to make an impact is to create a GitHub
issue or pull request. We do our best to triage and address docs issues as soon
as possible.

## Contributing

We welcome direct contributions to the docs! Our docs are maintained in markdown
files in this repo. All changes are managed through a code-first release flow.

The design and hosting of our docs site is provided by
[Mintlify](https://mintlify.com/). The vast majority of configuration is in code
in `mint.json`.

Changes will be deployed to [production](https://docs.hypermode.com)
automatically after pushing to the `main` branch.

### Development Environment Setup

The following components are useful when developing locally:

#### Mintlify CLI

See live changes as you write and edit.

```bash
npm i -g mintlify
```

#### Trunk CLI

Format and lint changes for easy merging.

```bash
npm i -g @trunkio/launcher
```

### Writing

Mintlify includes a
[number of components](https://mintlify.com/docs/content/components/accordions)
to make it easier to build easy-to-consume documentation.

To spin up a local server, run the following command at the root of the docs
repo:

```bash
mintlify dev
```

#### Style

Consistency is important in any documentation experience. Beyond Markdown’s
opinionated structure, we adhere to a consistent style for Hypermode.

We have adopted
[Google’s Developer Documentation Style Guide](https://developers.google.com/style/)
as a baseline, with Hypermode-specific terms
[stored in a vocabulary file](./styles/config/vocabularies/general/accept.txt).

[Vale](https://vale.sh/) has been implemented in the repo for easy alignment.
Vale is implemented within CI/CD, but also executable locally with through
Trunk.

#### Iconography

When icons are required, select from
[Font Awesome](https://fontawesome.com/icons)’s catalog for easy rendering with
Mintlify.

#### Formatting and Linting

Trunk has been implemented for easy formatting and linting across different file
types. It is implemented within CI/CD, but also executable locally.

Formatting should run automatically on save. To trigger a manual formatting of
the repo, run:

```bash
trunk fmt
```

To run lint checks, run:

```bash
trunk check # appending --all will run checks beyond changes on the current branch
```

Note that Trunk also has a
[VS Code extension](https://marketplace.visualstudio.com/items?itemName=Trunk.io)
you can install.

However, when installing it please be aware of the `trunk.autoInit` setting,
which is `true` (enabled) by default This controls whether to auto-initialize
trunk in non-trunk repositories - meaning _any_ folder you open with VS Code
will get configured with a `.trunk` subfolder, and will start using Trunk. You
should probably set this to `false` in your VS Code user settings, to not
interfere with other projects you may be working on.

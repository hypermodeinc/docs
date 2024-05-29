# Docs

Self-serve documentation is a critical part of any technical product. Beyond current users, docs are an important evaluation tool for prospective users.

## Source Control

Our docs are maintained in markdown files in this repo. All changes are managed through a code-first release flow.

## Hosting

The design and hosting of our site is provided by [Mintlify](https://mintlify.com/). The vast majority of configuration is in code in `mint.json`.

Changes will be deployed to [production](https://docs.hypermode.com) automatically after pushing to the `main` branch.

## Development Environment Setup

The following components are useful when developing locally:

### Mintlify CLI

See live changes as you write and edit.

```bash
npm i -g mintlify
```

### Vale CLI

Validate alignment of changes with style guide.

```bash
npm i -D @ocular-d/vale-bin
```

### Trunk CLI

Format and lint changes for easy merging.

```bash
npm i -D @trunkio/launcher
```

## Writing

Mintlify includes a [number of components](https://mintlify.com/docs/content/components/accordions) to make it easier to build easy-to-consume documentation.

To spin up a local server, run the following command at the root of the docs repo:

```bash
mintlify dev
```

### Style

Consistency is important in any documentation experience. Beyond Markdown’s opinionated structure, we adhere to a consistent style for Hypermode.

We have adopted [Google’s Developer Documentation Style Guide](https://developers.google.com/style/) as a baseline, with Hypermode-specific terms [stored in a vocabulary file](./styles/config/vocabularies/general/accept.txt).

[Vale](https://vale.sh/) has been implemented in the repo for easy alignment. Vale is implemented within CI/CD, but also executable locally with:

```bash
vale --glob='*.{mdx}' *
```

### Iconography

When icons are required, select from [Font Awesome](https://fontawesome.com/icons)’s catalog for easy rendering with Mintlify.

### Formatting and Linting

Trunk has been implemented for easy formatting and linting across different file types. It is implemented within CI/CD, but also executable locally.

To format the repo locally, run:

```bash
trunk fmt
```

To run lint checks, run:

```bash
trunk check # appending --all will run checks beyond changes on the current branch
```

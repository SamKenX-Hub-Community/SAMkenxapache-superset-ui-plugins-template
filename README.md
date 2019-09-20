# @superset-ui/plugins 🔌💡

[![Codecov branch](https://img.shields.io/codecov/c/github/apache-superset/superset-ui-plugins-template/master.svg?style=flat-square)](https://codecov.io/gh/apache-superset/superset-ui-plugins-template/branch/master)
[![Build Status](https://img.shields.io/travis/com/apache-superset/superset-ui-plugins-template/master.svg?style=flat-square
)](https://travis-ci.com/apache-superset/superset-ui-plugins-template)
[![David](https://img.shields.io/david/dev/apache-superset/superset-ui-plugins-template.svg?style=flat-square)](https://david-dm.org/apache-superset/superset-ui-plugins-template?type=dev)
[![Netlify Status](https://api.netlify.com/api/v1/badges/d2c78390-752e-4fc2-abf0-7e6df362b9ff/deploy-status)](https://app.netlify.com/sites/superset-ui-plugins-template/deploys)

`@superset-ui/legacy-*` packages are extracted from the classic [Apache Superset](https://github.com/apache/incubator-superset) and converted into plugins.
These packages are extracted with minimal changes (almost as-is). They also depend on legacy API (`viz.py`) to function.

`@superset-ui/plugin-*` packages are newer and has higher quality in general.
A key difference that they do not depend on `viz.py`
(which contain visualization-specific python code) and interface with
`/api/v1/query/` instead: a new generic endpoint instead meant to
serve all visualizations.

We are not accepting pull requests for new community-contributed plugins to be merged into this repository at the moment.
We will keep it lean for now to improve the standard and reduce operational load on maintenance.
Bug fixes are welcome.

In the future, we plan to have a template for new repository or generator for everybody to setup a single plugin repository easily on his/her own.
This way anybody can create and publish a Superset plugin.

## Demo (Storybook)

Most recent release: https://apache-superset.github.io/superset-ui-plugins-template/

Current master: https://superset-ui-plugins-template.netlify.com

## Packages

| Package | Version | Note |
|--|--|--|
| [@superset-ui/plugin-chart-dummy](https://github.com/apache-superset/superset-ui/tree/master/packages/superset-ui-plugin-chart-dummy) | [![Version](https://img.shields.io/npm/v/@superset-ui/plugin-chart-dummy.svg?style=flat-square)](https://img.shields.io/npm/v/@superset-ui/plugin-chart-dummy.svg?style=flat-square) | |
| [@superset-ui/preset-chart-dummies](https://github.com/apache-superset/superset-ui/tree/master/packages/superset-ui-preset-chart-dummies) | [![Version](https://img.shields.io/npm/v/@superset-ui/preset-chart-dummies.svg?style=flat-square)](https://img.shields.io/npm/v/@superset-ui/preset-chart-dummies.svg?style=flat-square) | experimental |


### Development

[lerna](https://github.com/lerna/lerna/) and [yarn](https://yarnpkg.com) are used to manage versions and dependencies between
packages in this monorepo.

```
superset-ui/
  lerna.json
  package.json
  ...
  packages/
    package1/
      package.json
      ...
      src/
      test/
      ...
      lib/
      esm/
      ...
    ...
```



### Installation

1. clone this repo
2. have yarn install package dependencies and manage the symlinking between packages for you

```sh
git clone ...superset-ui-plugins-template && cd superset-ui-plugins-template
yarn install
yarn build
```

### Builds, linting, and testing

Each package defines its own build config, linting, and testing. You can have lerna run commands
across all packages using the syntax `yarn run test` (or `yarn run test:watch` for watch mode) from the root `@superset-ui-plugins-template` directory.

* [Using Storybook](https://github.com/apache-superset/superset-ui/blob/master/docs/storybook.md) - You can test your components independently from Superset app.
* [Debugging Superset plugins in Superset app](https://github.com/apache-superset/superset-ui/blob/master/docs/debugging.md) - Sometimes something went wrong and you have to do it.

### Committing

This repository follows [conventional commits](https://www.conventionalcommits.org/en/v1.0.0-beta.3/) guideline for commit messages and has a `commitlint` hook which will require you to have the valid commit message before committing. You can use `npm run commit` to help you create a commit message.

### Publishing

**Prerequisite:** You'll need an [npmjs.com](https://npmjs.com) account that is part of the `@superset-ui` organization.

1. Make sure you're logged in to NPM from your shell. Run `npm login` if necessary.
2. To make the release, run `yarn run release` and follow the prompts.

### License

Apache-2.0

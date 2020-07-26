<br />
<p align="center">
  <a>
    <img alt="Monorepo" title="Monorepo" src=".github/images/monorepo.png" width="700">
  </a>
</p>

<p align="center">
  Monorepo structure with Node.js, ReactJS, Yarn Workspaces, TypeScript, ESLint, Prettier, Jest and CI/CD pipeline with GitHub Actions
</p>


## Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Migration Monorepo](#migration-monorepo)
- [Feedback](#feedback)

<br>

## Overview

As applications scale, you’ll inevitably reach a point where you want to write shared reusable components which can be used everywhere. Historically, we’ve had separate repositories for each package. However, this becomes a problem for a few reasons:

* It does not scale well. Before you know it, you have dozens of different package repositories repeating the same build, test, and release process.
* It promotes bundling unnecessary components. Do we need to create a new repo for this button? Let’s put it together with this other package. Now we’ve increased the bundle size for something 95% of consumers won’t use.
* It makes upgrading difficult. If you update a base component, you now have to update its consumers, its consumer’s consumers, etc. This problem gets worse as you scale.

To make our applications as performant as possible, we need to have **small bundle sizes**. This means we should only include the code we’re using in our bundle.

Along with this, when developing shared component libraries, we want to have [semver](https://semver.org) over individual pieces instead of the entire package. This prevents scenarios where:

1. Consumer A only needs the package for one component and is on v1.
2. Consumer B uses the package for all the components. They’ve helped create and modify other components in the package and it’s grown large. It’s now on v8.
3. Consumer A now needs a bug fix for the one component they use. They have to update to v8.

<br>

## Installation

First of all, you may clone this repo

```
  git clone https://github.com/leandrocanabarro/monorepo.git
```

Execute Web

```
  yarn workspace @monorepo/web start
```

Execute Server

```
  yarn workspace @monorepo/server start
```

Install styled-components

```
  yarn workspace @monorepo/web add styled-components
```

Install the dependency for a single workspace.

```
  yarn workspace @monorepo/web add styled-components
```

Using -W instructs Yarn to install the given dependencies for the entire workspace.
These dependencies are usually shared between all packages.

```
  yarn add -DW jest ts-jest @types/jest
```

<br>

## Migration Monorepo

* Tools for building and splitting monolithic repository from existing packages. [Monorepo Tools](https://github.com/shopsys/monorepo-tools)
* A curated list of awesome Monorepo tools, software and architectures. [Awesome Monorepo](https://github.com/korfuri/awesome-monorepo)

<br>

## Feedback

Feel free to send me feedback on [LinkedIn](https://linkedin.com/in/leandrocanabarro) or [file an issue](https://github.com/leandrocanabarro/monorepo/issues/new). Feature requests are always welcome.

# test-postinstall-node-version-check

Tests warning for deprecated Node.js versions in postinstall script.

Node.js version `v8.11.3`

```console
$ npm install test-postinstall-node-version-check

> test-postinstall-node-version-check@0.1.1 postinstall /Users/trivikr/workspace/test-warning/node_modules/test-postinstall-node-version-check
> node check-node-version.js

The Node.js version v8.11.3 is no longer supported.
...
```

```console
$ yarn add test-postinstall-node-version-check
yarn add v1.22.10
info No lockfile found.
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
[3/4] 🔗  Linking dependencies...
[4/4] 🔨  Building fresh packages...
success Saved lockfile.
success Saved 1 new dependency.
info Direct dependencies
└─ test-postinstall-node-version-check@0.1.1
info All dependencies
└─ test-postinstall-node-version-check@0.1.1
✨  Done in 0.49s.
```

yarn doesn't seem to support postinstall script https://github.com/yarnpkg/yarn/issues/5476

```console
$ pnpm add test-postinstall-node-version-check
Already up-to-date
Resolving: total 1, reused 0, downloaded 1, done
node_modules/.registry.npmjs.org/test-postinstall-node-version-check/0.1.1/node_modules/test-postinstall-node-version-check: Running node_modules/.registry.npmjs.org/test-postinstall-node-version-check/0.1.1/node_modules/test-postinstall-node-version-check: Running node_modules/.registry.npmjs.org/test-postinstall-node-version-check/0.1.1/node_modules/test-postinstall-node-version-check: Running postinstall script, done in 64ms

dependencies:
+ test-postinstall-node-version-check 0.1.1
```

pnpm also doesn't seem to print console.warn from postinstall script.

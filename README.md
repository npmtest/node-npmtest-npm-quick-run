# npmtest-npm-quick-run

#### basic test coverage for  [npm-quick-run (v1.16.0)](https://github.com/bahmutov/npm-quick-run#readme)  [![npm package](https://img.shields.io/npm/v/npmtest-npm-quick-run.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-npm-quick-run) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-npm-quick-run.svg)](https://travis-ci.org/npmtest/node-npmtest-npm-quick-run)

#### Quickly run NPM script by prefix without typing the full name

[![NPM](https://nodei.co/npm/npm-quick-run.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/npm-quick-run)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-npm-quick-run/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-npm-quick-run/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-npm-quick-run/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-npm-quick-run/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-npm-quick-run/build/test-report.html)|
| test-server-github : | [![github.com test-server](https://npmtest.github.io/node-npmtest-npm-quick-run/GitHub-Mark-32px.png)](https://npmtest.github.io/node-npmtest-npm-quick-run/build/app/index.html) | | build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-npm-quick-run/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-npm-quick-run/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-npm-quick-run/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-npm-quick-run/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-npm-quick-run/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-npm-quick-run/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-npm-quick-run/build/test-report.html](https://npmtest.github.io/node-npmtest-npm-quick-run/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-npm-quick-run/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-npm-quick-run/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-npm-quick-run/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-npm-quick-run/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-npm-quick-run/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-npm-quick-run/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-npm-quick-run/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-npm-quick-run/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Gleb Bahmutov"
    },
    "bin": {
        "nr": "bin/npm-quick-run.js",
        "nrun": "bin/npm-quick-run.js"
    },
    "bugs": {
        "url": "https://github.com/bahmutov/npm-quick-run/issues"
    },
    "config": {
        "pre-git": {
            "commit-msg": "simple",
            "pre-commit": [
                "npm test",
                "npm run example",
                "node bin/npm-quick-run.js test-foo 'foo bar'"
            ],
            "pre-push": [
                "npm run size"
            ],
            "post-commit": [],
            "post-merge": []
        }
    },
    "dependencies": {
        "bluebird": "3.3.1",
        "chalk": "1.1.3",
        "cross-spawn": "4.0.0",
        "debug": "2.6.1",
        "findup": "0.1.5",
        "fuzzy": "0.1.3",
        "inquirer": "3.0.5",
        "inquirer-autocomplete-prompt": "0.8.0",
        "json-package": "1.1.2",
        "simple-bin-help": "1.6.0"
    },
    "description": "Quickly run NPM script by prefix without typing the full name",
    "devDependencies": {
        "git-issues": "1.3.1",
        "mocha": "3.2.0",
        "pre-git": "3.14.0",
        "semantic-release": "6.3.6",
        "standard": "8.6.0"
    },
    "directories": {},
    "dist": {
        "shasum": "80668a4334752ff8da2b890cb2055ee7cb6d9691",
        "tarball": "https://registry.npmjs.org/npm-quick-run/-/npm-quick-run-1.16.0.tgz"
    },
    "files": [
        "bin",
        "src/*.js",
        "!src/*-spec.js",
        "README.md"
    ],
    "gitHead": "79b63cc2a974737b06019ec60ee4b77ee77abb10",
    "homepage": "https://github.com/bahmutov/npm-quick-run#readme",
    "keywords": [
        "npm",
        "utility",
        "run",
        "script",
        "partial",
        "quick"
    ],
    "license": "MIT",
    "main": "src/quick-run.js",
    "maintainers": [
        {
            "name": "bahmutov"
        }
    ],
    "name": "npm-quick-run",
    "optionalDependencies": {},
    "preferGlobal": true,
    "repository": {
        "type": "git",
        "url": "git+https://github.com/bahmutov/npm-quick-run.git"
    },
    "scripts": {
        "commit": "git-issues && commit-wizard",
        "error": "echo \"an error on purpose\" && exit -1",
        "example": "node bin/npm-quick-run.js li",
        "issues": "git-issues",
        "lint": "standard --verbose --fix bin/*.js src/*.js",
        "pretest": "npm run lint",
        "semantic-release": "semantic-release pre && npm publish && semantic-release post",
        "size": "t=\"$(npm pack .)\"; wc -c \"${t}\"; tar tvf \"${t}\"; rm \"${t}\";",
        "test": "mocha --harmony src/*-spec.js",
        "test-foo": "node -e \"console.assert(process.argv[1] === 'foo bar', process.argv)\""
    },
    "version": "1.16.0"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

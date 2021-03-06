# npmdoc-virtual-dom

#### basic api documentation for  [virtual-dom (v2.1.1)](https://github.com/Matt-Esch/virtual-dom)  [![npm package](https://img.shields.io/npm/v/npmdoc-virtual-dom.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-virtual-dom) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-virtual-dom.svg)](https://travis-ci.org/npmdoc/node-npmdoc-virtual-dom)

#### A batched diff-based DOM rendering strategy

[![NPM](https://nodei.co/npm/virtual-dom.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/virtual-dom)

- [https://npmdoc.github.io/node-npmdoc-virtual-dom/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-virtual-dom/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-virtual-dom/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-virtual-dom/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-virtual-dom/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-virtual-dom/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Matt-Esch"
    },
    "bugs": {
        "url": "https://github.com/Matt-Esch/virtual-dom/issues"
    },
    "contributors": [
        {
            "name": "Matt-Esch"
        }
    ],
    "dependencies": {
        "browser-split": "0.0.1",
        "error": "^4.3.0",
        "ev-store": "^7.0.0",
        "global": "^4.3.0",
        "is-object": "^1.0.1",
        "next-tick": "^0.2.2",
        "x-is-array": "0.1.0",
        "x-is-string": "0.1.0"
    },
    "description": "A batched diff-based DOM rendering strategy",
    "devDependencies": {
        "browserify": "^9.0.7",
        "istanbul": "^0.3.13",
        "min-document": "^2.14.0",
        "opn": "^1.0.1",
        "run-browser": "^2.0.2",
        "tap-dot": "^1.0.0",
        "tap-spec": "^3.0.0",
        "tape": "^4.0.0",
        "zuul": "^2.1.1"
    },
    "directories": {},
    "dist": {
        "shasum": "80eda2d481b9ede0c049118cefcb4a05f21d1375",
        "tarball": "https://registry.npmjs.org/virtual-dom/-/virtual-dom-2.1.1.tgz"
    },
    "gitHead": "b57d21284dab9e96c5d33035c0530e2396d33b41",
    "homepage": "https://github.com/Matt-Esch/virtual-dom",
    "keywords": [
        "virtual",
        "dom",
        "vdom",
        "vtree",
        "diff",
        "patch",
        "browser"
    ],
    "license": "MIT",
    "main": "index",
    "maintainers": [
        {
            "name": "mattesch"
        }
    ],
    "name": "virtual-dom",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git://github.com/Matt-Esch/virtual-dom.git"
    },
    "scripts": {
        "browser": "run-browser test/index.js",
        "cover": "istanbul cover --report html --print detail ./test/index.js",
        "dist": "browserify --standalone virtual-dom index.js > dist/virtual-dom.js",
        "dot": "node ./test/index.js | tap-dot",
        "phantom": "run-browser test/index.js -b | tap-spec",
        "release": "npm run release-patch",
        "release-major": "git checkout master && npm version major && git push origin master --tags && npm publish",
        "release-minor": "git checkout master && npm version minor && git push origin master --tags && npm publish",
        "release-patch": "git checkout master && npm version patch && git push origin master --tags && npm publish",
        "start": "node ./index.js",
        "test": "node ./test/index.js | tap-spec",
        "travis-test": "npm run phantom && npm run cover && istanbul report lcov && ((cat coverage/lcov.info | coveralls) || exit 0)",
        "view-cover": "istanbul report html && opn ./coverage/index.html"
    },
    "testling": {
        "files": "test/*.js",
        "browsers": [
            "ie/8..latest",
            "firefox/17..latest",
            "firefox/nightly",
            "chrome/22..latest",
            "chrome/canary",
            "opera/12..latest",
            "opera/next",
            "safari/5.1..latest",
            "ipad/6.0..latest",
            "iphone/6.0..latest",
            "android-browser/4.2..latest"
        ]
    },
    "version": "2.1.1",
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

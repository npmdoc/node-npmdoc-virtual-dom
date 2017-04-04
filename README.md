# api documentation for  [virtual-dom (v2.1.1)](https://github.com/Matt-Esch/virtual-dom)  [![npm package](https://img.shields.io/npm/v/npmdoc-virtual-dom.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-virtual-dom) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-virtual-dom.svg)](https://travis-ci.org/npmdoc/node-npmdoc-virtual-dom)
#### A batched diff-based DOM rendering strategy

[![NPM](https://nodei.co/npm/virtual-dom.png?downloads=true)](https://www.npmjs.com/package/virtual-dom)

[![apidoc](https://npmdoc.github.io/node-npmdoc-virtual-dom/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-virtual-dom_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-virtual-dom/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-virtual-dom/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-virtual-dom/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Matt-Esch",
        "email": "matt@mattesch.info"
    },
    "bugs": {
        "url": "https://github.com/Matt-Esch/virtual-dom/issues",
        "email": "matt@mattesch.info"
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
            "name": "mattesch",
            "email": "matt@mattesch.info"
        }
    ],
    "name": "virtual-dom",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
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
    "version": "2.1.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module virtual-dom](#apidoc.module.virtual-dom)
1.  [function <span class="apidocSignatureSpan">virtual-dom.</span>VNode (tagName, properties, children, key, namespace)](#apidoc.element.virtual-dom.VNode)
1.  [function <span class="apidocSignatureSpan">virtual-dom.</span>VText (text)](#apidoc.element.virtual-dom.VText)
1.  [function <span class="apidocSignatureSpan">virtual-dom.</span>create (vnode, opts)](#apidoc.element.virtual-dom.create)
1.  [function <span class="apidocSignatureSpan">virtual-dom.</span>diff (a, b)](#apidoc.element.virtual-dom.diff)
1.  [function <span class="apidocSignatureSpan">virtual-dom.</span>h (tagName, properties, children)](#apidoc.element.virtual-dom.h)
1.  [function <span class="apidocSignatureSpan">virtual-dom.</span>patch (rootNode, patches, renderOptions)](#apidoc.element.virtual-dom.patch)



# <a name="apidoc.module.virtual-dom"></a>[module virtual-dom](#apidoc.module.virtual-dom)

#### <a name="apidoc.element.virtual-dom.VNode"></a>[function <span class="apidocSignatureSpan">virtual-dom.</span>VNode (tagName, properties, children, key, namespace)](#apidoc.element.virtual-dom.VNode)
- description and source-code
```javascript
function VirtualNode(tagName, properties, children, key, namespace) {
    this.tagName = tagName
    this.properties = properties || noProperties
    this.children = children || noChildren
    this.key = key != null ? String(key) : undefined
    this.namespace = (typeof namespace === "string") ? namespace : null

    var count = (children && children.length) || 0
    var descendants = 0
    var hasWidgets = false
    var hasThunks = false
    var descendantHooks = false
    var hooks

    for (var propName in properties) {
        if (properties.hasOwnProperty(propName)) {
            var property = properties[propName]
            if (isVHook(property) && property.unhook) {
                if (!hooks) {
                    hooks = {}
                }

                hooks[propName] = property
            }
        }
    }

    for (var i = 0; i < count; i++) {
        var child = children[i]
        if (isVNode(child)) {
            descendants += child.count || 0

            if (!hasWidgets && child.hasWidgets) {
                hasWidgets = true
            }

            if (!hasThunks && child.hasThunks) {
                hasThunks = true
            }

            if (!descendantHooks && (child.hooks || child.descendantHooks)) {
                descendantHooks = true
            }
        } else if (!hasWidgets && isWidget(child)) {
            if (typeof child.destroy === "function") {
                hasWidgets = true
            }
        } else if (!hasThunks && isThunk(child)) {
            hasThunks = true;
        }
    }

    this.count = count + descendants
    this.hasWidgets = hasWidgets
    this.hasThunks = hasThunks
    this.hooks = hooks
    this.descendantHooks = descendantHooks
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.virtual-dom.VText"></a>[function <span class="apidocSignatureSpan">virtual-dom.</span>VText (text)](#apidoc.element.virtual-dom.VText)
- description and source-code
```javascript
function VirtualText(text) {
    this.text = String(text)
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.virtual-dom.create"></a>[function <span class="apidocSignatureSpan">virtual-dom.</span>create (vnode, opts)](#apidoc.element.virtual-dom.create)
- description and source-code
```javascript
function createElement(vnode, opts) {
    var doc = opts ? opts.document || document : document
    var warn = opts ? opts.warn : null

    vnode = handleThunk(vnode).a

    if (isWidget(vnode)) {
        return vnode.init()
    } else if (isVText(vnode)) {
        return doc.createTextNode(vnode.text)
    } else if (!isVNode(vnode)) {
        if (warn) {
            warn("Item is not a valid virtual dom node", vnode)
        }
        return null
    }

    var node = (vnode.namespace === null) ?
        doc.createElement(vnode.tagName) :
        doc.createElementNS(vnode.namespace, vnode.tagName)

    var props = vnode.properties
    applyProperties(node, props)

    var children = vnode.children

    for (var i = 0; i < children.length; i++) {
        var childNode = createElement(children[i], opts)
        if (childNode) {
            node.appendChild(childNode)
        }
    }

    return node
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.virtual-dom.diff"></a>[function <span class="apidocSignatureSpan">virtual-dom.</span>diff (a, b)](#apidoc.element.virtual-dom.diff)
- description and source-code
```javascript
function diff(a, b) {
    var patch = { a: a }
    walk(a, b, patch, 0)
    return patch
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.virtual-dom.h"></a>[function <span class="apidocSignatureSpan">virtual-dom.</span>h (tagName, properties, children)](#apidoc.element.virtual-dom.h)
- description and source-code
```javascript
function h(tagName, properties, children) {
    var childNodes = [];
    var tag, props, key, namespace;

    if (!children && isChildren(properties)) {
        children = properties;
        props = {};
    }

    props = props || properties || {};
    tag = parseTag(tagName, props);

    // support keys
    if (props.hasOwnProperty('key')) {
        key = props.key;
        props.key = undefined;
    }

    // support namespace
    if (props.hasOwnProperty('namespace')) {
        namespace = props.namespace;
        props.namespace = undefined;
    }

    // fix cursor bug
    if (tag === 'INPUT' &&
        !namespace &&
        props.hasOwnProperty('value') &&
        props.value !== undefined &&
        !isHook(props.value)
    ) {
        props.value = softSetHook(props.value);
    }

    transformProperties(props);

    if (children !== undefined && children !== null) {
        addChild(children, childNodes, tag, props);
    }


    return new VNode(tag, props, childNodes, key, namespace);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.virtual-dom.patch"></a>[function <span class="apidocSignatureSpan">virtual-dom.</span>patch (rootNode, patches, renderOptions)](#apidoc.element.virtual-dom.patch)
- description and source-code
```javascript
function patch(rootNode, patches, renderOptions) {
    renderOptions = renderOptions || {}
    renderOptions.patch = renderOptions.patch && renderOptions.patch !== patch
        ? renderOptions.patch
        : patchRecursive
    renderOptions.render = renderOptions.render || render

    return renderOptions.patch(rootNode, patches, renderOptions)
}
```
- example usage
```shell
...
        reorderChildren(domNode, patch)
        return domNode
    case VPatch.PROPS:
        applyProperties(domNode, patch, vNode.properties)
        return domNode
    case VPatch.THUNK:
        return replaceRoot(domNode,
            renderOptions.patch(domNode, patch, renderOptions))
    default:
        return domNode
}
}

function removeNode(domNode, vNode) {
var parentNode = domNode.parentNode
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

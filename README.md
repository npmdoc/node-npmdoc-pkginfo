# api documentation for  [pkginfo (v0.4.0)](https://github.com/indexzero/node-pkginfo#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-pkginfo.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-pkginfo) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-pkginfo.svg)](https://travis-ci.org/npmdoc/node-npmdoc-pkginfo)
#### An easy way to expose properties on a module from a package.json

[![NPM](https://nodei.co/npm/pkginfo.png?downloads=true)](https://www.npmjs.com/package/pkginfo)

[![apidoc](https://npmdoc.github.io/node-npmdoc-pkginfo/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-pkginfo_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-pkginfo/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-pkginfo/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-pkginfo/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Charlie Robbins",
        "email": "charlie.robbins@gmail.com"
    },
    "bugs": {
        "url": "https://github.com/indexzero/node-pkginfo/issues"
    },
    "dependencies": {},
    "description": "An easy way to expose properties on a module from a package.json",
    "devDependencies": {
        "vows": "0.8.0"
    },
    "directories": {},
    "dist": {
        "shasum": "349dbb7ffd38081fcadc0853df687f0c7744cd65",
        "tarball": "https://registry.npmjs.org/pkginfo/-/pkginfo-0.4.0.tgz"
    },
    "engines": {
        "node": ">= 0.4.0"
    },
    "gitHead": "f0cc3fa9d45413bdabd2d160bb0dbe03e2d04870",
    "homepage": "https://github.com/indexzero/node-pkginfo#readme",
    "keywords": [
        "info",
        "tools",
        "package.json"
    ],
    "license": "MIT",
    "main": "./lib/pkginfo.js",
    "maintainers": [
        {
            "name": "indexzero",
            "email": "charlie.robbins@gmail.com"
        }
    ],
    "name": "pkginfo",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+ssh://git@github.com/indexzero/node-pkginfo.git"
    },
    "scripts": {
        "test": "vows test/*-test.js --spec"
    },
    "version": "0.4.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module pkginfo](#apidoc.module.pkginfo)
1.  [function <span class="apidocSignatureSpan">pkginfo.</span>find (pmodule, dir)](#apidoc.element.pkginfo.find)
1.  [function <span class="apidocSignatureSpan">pkginfo.</span>read (pmodule, dir)](#apidoc.element.pkginfo.read)
1.  string <span class="apidocSignatureSpan">pkginfo.</span>version



# <a name="apidoc.module.pkginfo"></a>[module pkginfo](#apidoc.module.pkginfo)

#### <a name="apidoc.element.pkginfo.find"></a>[function <span class="apidocSignatureSpan">pkginfo.</span>find (pmodule, dir)](#apidoc.element.pkginfo.find)
- description and source-code
```javascript
find = function (pmodule, dir) {
  if (! dir) {
    dir = path.dirname(pmodule.filename || pmodule.id);
  }

  if (dir === '/') {
    throw new Error('Could not find package.json up from ' +
                (pmodule.filename || pmodule.id));
  }
  else if (!dir || dir === '.') {
    throw new Error('Cannot find package.json from unspecified directory');
  }

  var contents;
  try {
    contents = require(dir + '/package.json');
  } catch (error) {}

  if (contents) return contents;

  return pkginfo.find(pmodule, path.dirname(dir));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.pkginfo.read"></a>[function <span class="apidocSignatureSpan">pkginfo.</span>read (pmodule, dir)](#apidoc.element.pkginfo.read)
- description and source-code
```javascript
read = function (pmodule, dir) {
  return {
    dir: dir,
    package: pkginfo.find(pmodule, dir),
  };
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

# api documentation for  [grunt-contrib-htmlmin (v2.3.0)](https://github.com/gruntjs/grunt-contrib-htmlmin#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-grunt-contrib-htmlmin.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-grunt-contrib-htmlmin) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-grunt-contrib-htmlmin.svg)](https://travis-ci.org/npmdoc/node-npmdoc-grunt-contrib-htmlmin)
#### Minify HTML

[![NPM](https://nodei.co/npm/grunt-contrib-htmlmin.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/grunt-contrib-htmlmin)

[![apidoc](https://npmdoc.github.io/node-npmdoc-grunt-contrib-htmlmin/build/screenCapture.buildCi.browser.apidoc.html.png)](https://npmdoc.github.io/node-npmdoc-grunt-contrib-htmlmin/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-grunt-contrib-htmlmin/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-grunt-contrib-htmlmin/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "appveyor_id": "sn73i2qggqeolnc2",
    "author": {
        "name": "Grunt Team",
        "url": "http://gruntjs.com/"
    },
    "bugs": {
        "url": "https://github.com/gruntjs/grunt-contrib-htmlmin/issues"
    },
    "contributors": [
        {
            "name": "Sindre Sorhus",
            "url": "http://github.com/sindresorhus"
        }
    ],
    "dependencies": {
        "chalk": "^1.0.0",
        "html-minifier": "~3.4.0",
        "pretty-bytes": "^4.0.2"
    },
    "description": "Minify HTML",
    "devDependencies": {
        "grunt": "^1.0.0",
        "grunt-contrib-clean": "^1.0.0",
        "grunt-contrib-internal": "^1.1.0",
        "grunt-contrib-jshint": "^1.0.0",
        "grunt-contrib-nodeunit": "^1.0.0"
    },
    "directories": {},
    "dist": {
        "shasum": "1c72093e9ed80be2dad8c76f0e657c8184dcc092",
        "tarball": "https://registry.npmjs.org/grunt-contrib-htmlmin/-/grunt-contrib-htmlmin-2.3.0.tgz"
    },
    "engines": {
        "node": ">=4.0"
    },
    "files": [
        "tasks"
    ],
    "gitHead": "ce5d713f781e3383a3073f30824d6d1a975df33c",
    "homepage": "https://github.com/gruntjs/grunt-contrib-htmlmin#readme",
    "keywords": [
        "gruntplugin",
        "html",
        "min",
        "minify",
        "compress",
        "optimize"
    ],
    "license": "MIT",
    "main": "tasks/htmlmin.js",
    "maintainers": [
        {
            "name": "cowboy"
        },
        {
            "name": "jmeas"
        },
        {
            "name": "shama"
        },
        {
            "name": "sindresorhus"
        },
        {
            "name": "tkellen"
        },
        {
            "name": "vladikoff"
        },
        {
            "name": "xhmikosr"
        }
    ],
    "name": "grunt-contrib-htmlmin",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/gruntjs/grunt-contrib-htmlmin.git"
    },
    "scripts": {
        "test": "grunt test"
    },
    "version": "2.3.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module grunt-contrib-htmlmin](#apidoc.module.grunt-contrib-htmlmin)
1.  [function <span class="apidocSignatureSpan"></span>grunt-contrib-htmlmin (grunt)](#apidoc.element.grunt-contrib-htmlmin.grunt-contrib-htmlmin)
1.  [function <span class="apidocSignatureSpan">grunt-contrib-htmlmin.</span>toString ()](#apidoc.element.grunt-contrib-htmlmin.toString)



# <a name="apidoc.module.grunt-contrib-htmlmin"></a>[module grunt-contrib-htmlmin](#apidoc.module.grunt-contrib-htmlmin)

#### <a name="apidoc.element.grunt-contrib-htmlmin.grunt-contrib-htmlmin"></a>[function <span class="apidocSignatureSpan"></span>grunt-contrib-htmlmin (grunt)](#apidoc.element.grunt-contrib-htmlmin.grunt-contrib-htmlmin)
- description and source-code
```javascript
grunt-contrib-htmlmin = function (grunt) {
  grunt.registerMultiTask('htmlmin', 'Minify HTML', function () {
    var options = this.options();
    var count = 0;

    this.files.forEach(function (file) {
      var min;
      var src = file.src[0];

      if (!src) {
        return;
      }

      var max = grunt.file.read(src);

      try {
        min = minify(max, options);
      } catch (err) {
        grunt.warn(src + '\n' + err);
        return;
      }

      count++;

      grunt.file.write(file.dest, min);
      grunt.verbose.writeln('Minified ' + chalk.cyan(file.dest) + ' ' + prettyBytes(max.length) + ' → ' + prettyBytes(min.length
));
    });

    grunt.log.writeln('Minified ' + chalk.cyan(count) + ' files' + (this.files.length !== count ? ' (' + chalk.red(this.files.length
 - count) + ' failed)' : ''));
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.grunt-contrib-htmlmin.toString"></a>[function <span class="apidocSignatureSpan">grunt-contrib-htmlmin.</span>toString ()](#apidoc.element.grunt-contrib-htmlmin.toString)
- description and source-code
```javascript
toString = function () {
    return toString;
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)

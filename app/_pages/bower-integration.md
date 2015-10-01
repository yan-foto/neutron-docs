---
title: Bower Integration
id: bower
---

Surely you want to have all the sweetness that comes with bower but at the same time you don't want to download half of Internet and deliver it with your app. neutron is delivered with [main-bower-files](https://www.npmjs.com/package/main-bower-files) module which allows you to cherry pick only the resources you need from packages.

Suppose you want to use [Bootstrap](http://getbootstrap.com/). After you have already initiated bower in the root folder of your app (e.g. using `bower init`) and added Bootstrap as dependency (e.g. using `bower install --save bootstrap`), you can use `overrides` key in `bower.json` file to select which files you want to copy into your `targetDir` (see [customization](./customization.html)):

```js
{
  "name": "neutron",
  "version": "0.0.0",
  "homepage": "https://github.com/yan-foto/neutron",
  "authors": [
    "Yan Foto <yan.foto@quaintous.com>"
  ],
  "license": "MIT",
  "ignore": [
    "**/.*",
    "node_modules",
    "bower_components",
    "test",
    "tests"
  ],
  "overrides": {
    "bootstrap": {
      "main": [
        "dist/js/bootstrap.min.js",
        "**/*.woff2"
      ]
    }
  },
  "dependencies": {
    "bootstrap": "~3.3.5"
  }
}
```

The example above would copy `bootstrap.min.js` to `css` directory and  `glyphicons-halflings-regular.woff2` to `fonts` directory of `targetDir` (`dist` by default).

**Note that only files with `.js`, `.css`, and those extensions defined as `statics` in configuration file (i.e. `.neutronrc`) are copied**

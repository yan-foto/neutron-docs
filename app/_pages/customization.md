---
title: Customizing neutron
id: custom
---

The starting point of customization is the `.neutronrc` file, which can be divided
in three main parts of **structure**, **build**, and **packaging**.

<nav class="toc">
  <ul>
    <li><a href="#strcuture">Structure</a></li>
    <li><a href="#build">Build</a></li>
    <li><a href="#packaging">Packaging</a></li>
    <li><a href="#example">Example</a></li>
  <ul>
</nav>

#### Structure
Structure properties determine where source files are to be found and where the build
results are to be copied to.

  * **`baseDir`**: path to source directory relative to project root (default: `src`)
  * **`targetDir`**: production directory (default: `dist`)

#### Build
Build properties determine how and which source files are to be compiled and which static
assets should be copied directly to the production directory:

  * **`statics`**: an array of extensions determining which files are to be copied
  directly from `baseDir` to `targetDir` (default: `["eot", "ttf", "woff", "woff2"]`)
  * **`dependencies`**: an object containing all dependencies used to build source files
  (currently only supporting **babel**, **jade**, and **sass**)
  * **`cleanIgnore`**: glob pattern (or an array of) determining files to be ignored
  when cleaning the `targetDir` (default: `[]`)

#### Packaging
Packaging is done using [`electron-packager`](https://www.npmjs.com/package/electron-packager)
module. The object provided under `packager` key is directly passed to this module. Read more about packaging [here](./packaging.html).

#### Example
```js
{
  "baseDir": "src",
  "targetDir": "dist",
  "statics": ["eot", "ttf", "woff", "woff2"],
  "dependencies": {
    "babel": {
      "extensions": ["js", "jsx"]
    },
    "jade": {
      "extensions": ["jade"]
    },
    "sass": {
      "extensions": ["scss", "css"],
      "includePaths": ["src/scss_include"]
    }
  },
  "cleanIgnore": [],
  "packager": {
    "dir": "dist",
    "out": "packages",
    "name": "neutron",
    "platform": "all",
    "arch": "all",
    "version": "0.30.4",
    "overwrite": true
  }
}
```
